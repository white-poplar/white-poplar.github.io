---
layout: posts
title: "MS-SQL Server 表值类型"
category: tech
tags: [Web, 数据库]
---

MS-SQL Server 存储过程参数可以传 table ？

<!--break-->

经常遇到 excel 数据导入的功能，之前要么是 `TRUNCATE TABLE` 重置表后程序遍历一条一条插入(数据库连接 N+1 次)，要么就是程序遍历数据库查重后插入(数据库连接 N*2 次)，遇到 excel 中数据较多时比较影响性能和速度。

网上浏览资料时，发现 MS-SQL Server表值类型(额，好多不知道的...)可以实现连接一次数据库完成上述功能。

1.创建表值类型

	CREATE TYPE [dbo].[_InfoType] AS TABLE(
		[_Name] [NVARCHAR](1000) NULL,
		[_Price] [MONEY] NULL
	)
	GO
*数据库 -> 可编程性 -> 类型 -> 用户定义表类型*

2.创建存储过程

	ALTER PROCEDURE proc_material_import (
		@uuid			UNIQUEIDENTIFIER,
		@paratable as   InfoType READONLY
	)
	AS 
	BEGIN
		SET NOCOUNT ON;

		--查询出重复/空的记录
		SELECT * FROM @paratable t1 WHERE EXISTS (SELECT t3._Name FROM _Info t3 WHERE t3._Name=t1._Name) OR (t1._Name IS NULL OR t1._Name = '')

		--导入数据库中不存在的记录
		INSERT INTO dbo._Info
				( _Name ,
				  _Price,
				  CreatUUID
				)
		SELECT t1._Name ,
			   ISNULL(t1._Price,0) ,
			   @uuid from @paratable t1 
		WHERE NOT EXISTS(SELECT t3._Name FROM _Info t3 WHERE t3._Name=t1._Name) AND (t1._Name IS NOT NULL AND t1._Name <> '')

	END
	GO
*返回重复/空的记录*

3.程序调用存储过程(.Net)

	SqlParameter[] parameters = {
								 new SqlParameter("@uuid",'00000000-0000-0000-0000-000000000000'),
								 new SqlParameter("@paratable",dt),
	};
	parameters[1].SqlDbType = SqlDbType.Structured;
	parameters[1].TypeName = "_InfoType";
	DataTable repeatDt = DbHelperSQL.ExecuteDataSet("proc_material_import", parameters).GetFirstDataTable();
*TypeName 为创建的表值类型*

- 定义表值类型时最好全部设为可空，因为 excel 内容不可控（多么痛的领悟）
- 最好一次创建好表值类型，因为修改表值类型敲麻烦
- excel 转 table 时最好判断下是否有重新记录，可使用 `Linq Group By` 判断
- excel 转为 table 后需与表值类型一致，可使用 `dt.Columns["名称"].ColumnName = "_Name"` 替换列名

OK，搞定！
