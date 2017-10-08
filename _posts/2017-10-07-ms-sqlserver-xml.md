---
layout: posts
title: "MS-SQL Server XML 类型"
category: tech
tags: [Web, 数据库]
---

最近遇到需要根据批量选择的数据（N个字段）进行数据操作的问题，最初是通过字符串拼接（A字段1,A字段2,A字段3#B字段1,B字段2,B字段3#C字段1,C字段2,C字段3）传入，存储过程进行分割实现。偶然听到同事说 MS-SQL Server XML 类型可以更方便处理此需求，于是进行了 XML 的初使用...

<!--break-->

网上搜了下 MS-SQL Server XML，大部分文章都有些繁琐，而只需要用到其中的几个点就可以完成这个需求，所以只记录了下简单的操作，以后遇到复杂的需求再研究其他的用法。

1.测试 XML 查询
	
	DECLARE @xml XML = N'<Root>   
		<Item>
			<MaterialId>1</MaterialId>
			<Number>20</Number>
			<WareHouseId>5</WareHouseId>
		</Item>
		<Item>
			<MaterialId>3</MaterialId>
			<Number>1</Number>
			<WareHouseId>1</WareHouseId>
		</Item>
	</Root> '

	--查询 XML 数据
	SELECT TOP 5
	S.value('(MaterialId)[1]','int') MaterialId, 
	S.value('(Number)[1]','int') Number,
	S.value('(WareHouseId)[1]','int') WareHouseId 
	FROM  @xml.nodes('/Root/Item') T(S)
	
	--方便的条件查询 XML 数据
	SELECT TOP 5 * FROM (
	SELECT
	S.value('(MaterialId)[1]','int') MaterialId, 
	S.value('(Number)[1]','int') Number,
	S.value('(WareHouseId)[1]','int') WareHouseId 
	FROM  @xml.nodes('/Root/Item') T(S)
	) t WHERE t.WareHouseId = 1

*和数据库中表的操作几乎一样*

2.创建存储过程

	ALTER PROCEDURE proc_use_material(
		@MaterialData	XML,	--物品Id,数量,仓库Id
		@UUID			UNIQUEIDENTIFIER
	)
	AS 
	BEGIN
		SET NOCOUNT ON;

		IF(CONVERT(NVARCHAR(MAX),@MaterialData) = '')
			RETURN 0;

		BEGIN TRY
			BEGIN TRANSACTION
				
				--GO
				INSERT INTO dbo.UseMaterial
						( 
						  MaterialId ,
						  Number ,
						  WareHouseId ,
						  CreatTime ,
						  CreatUUID 
						)
				SELECT 
				S.value('(MaterialId)[1]','bigint') MaterialId, 
				S.value('(Number)[1]','int') Number,
				S.value('(WareHouseId)[1]','bigint') WareHouseId,
				GETDATE(),@UUID
				FROM  @MaterialData.nodes('/Root/Item') T(S)
				
			COMMIT TRANSACTION
			RETURN 1;
		END TRY
		BEGIN CATCH
			ROLLBACK TRANSACTION

			--ProcError

			RETURN -9;
		END CATCH
	END
	GO

*定义存储过程包含 XML 参数*
*加了事务和异常处理*
*如果有多步数据操作，可查询 XML 后转为表变量 `DECLARE @temp_MaterialData TABLE`（会出现什么问题吗？）进行操作*

3.程序调用存储过程(.Net)

	#region XML
	string strMaterialData = @"
		<Root>   
			<Item>
				<MaterialId>1</MaterialId>
				<Number>20</Number>
				<WareHouseId>5</WareHouseId>
			</Item>
			<Item>
				<MaterialId>3</MaterialId>
				<Number>1</Number>
				<WareHouseId>1</WareHouseId>
			</Item>
		</Root> ";
	#endregion

	SqlParameter[] parameters = {
		new SqlParameter("@MaterialData", strMaterialData),
		new SqlParameter("@UUID", '00000000-0000-0000-0000-000000000000')
	};
	int tempI = DbHelperSQL.RunProc("proc_enrol_give_material", parameters);

*传入字符串类型（程序遍历拼接 ^-^）*

- 应该是 MS-SQL Server XML 最基础的操作（雾

>  --
> 附字符串拼接实现，可忽略（逃：
> --

	ALTER PROCEDURE proc_use_material(
		@strMaterialData	NVARCHAR(MAX) = '',
		@UUID				UNIQUEIDENTIFIER
	)
	AS
	BEGIN
		SET NOCOUNT ON;

		IF @strMaterialData <= ''
			RETURN 0;

		--分隔符
		IF @strMaterialData <> ''
			SET  @strMaterialData = @strMaterialData + '&' --物品Id,数量,仓库Id&物品Id,数量,仓库Id&

		BEGIN TRY
			BEGIN TRANSACTION

				-- @strMaterialData
				DECLARE @split VARCHAR(1) = '&';
				DECLARE @strMaterialDataItem NVARCHAR(200); --物品Id,数量,仓库Id

				DECLARE @MaterialId BIGINT,@Number INT,@WareHouseId BIGINT;

				WHILE(CHARINDEX(@split,@strMaterialData)<>0)
				BEGIN
					SET @strMaterialDataItem = SUBSTRING(@strMaterialData,1,CHARINDEX(@split,@strMaterialData)-1);
					
					SET @MaterialId = CONVERT(BIGINT,LEFT(@strMaterialDataItem,charindex(',',@strMaterialDataItem,1)-1));
					SET @Number = CONVERT(BIGINT,LEFT(SUBSTRING(@strMaterialDataItem,charindex(',',@strMaterialDataItem,1)+1,len(@strMaterialDataItem)),CHARINDEX(',',SUBSTRING(@strMaterialDataItem,charindex(',',@strMaterialDataItem,1)+1,len(@strMaterialDataItem)),1)-1));
					SET @WareHouseId = CONVERT(INT,SUBSTRING(SUBSTRING(@strMaterialDataItem,charindex(',',@strMaterialDataItem,1)+1,len(@strMaterialDataItem)),charindex(',',SUBSTRING(@strMaterialDataItem,charindex(',',@strMaterialDataItem,1)+1,len(@strMaterialDataItem)),1)+1,len(@strMaterialDataItem)));
					
					BEGIN
						--GO
					END
					
					SET @strMaterialData = STUFF(@strMaterialData,1,CHARINDEX(@split,@strMaterialData),'');
				END

			COMMIT TRANSACTION
			RETURN 1;
		END TRY
		--CATCH
		BEGIN CATCH
			ROLLBACK TRANSACTION

			--ProcError

			RETURN -9;
		END CATCH
	END
	GO
	
*具体参数分隔可自行网上查找，这里的简直不忍直视*

> --
> 字符串拼接结束，可忽略（逃：
> --
