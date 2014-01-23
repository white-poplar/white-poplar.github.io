---
layout: post
title: "ASP按英文单词截取字符串"
category: programming
tags: [ASP]
---

	'函数名：engotTopic
	'作  用：按单词截英文字符串
	'参  数：words   ----原字符串
	'       position ----截取长度、位置
	'返回值：截取后的字符串
	
<!--break-->

	function engotTopic(ByVal words,ByVal position)    
	dim flag,length
		if words="" then
			engotTopic=""
			exit function
		end if
	words=replace(replace(replace(replace(words,"&nbsp;"," "),"&quot;",chr(34)),"&gt;",">"),"&lt;","<")    
	flag = false
	length=len(words)
			if length>position then
				do while flag=false
				dim str,c
				str=mid(words,position+1,1)
				c=asc(str)
				if (c<65 and c<>39) or (c>90 and c<97) or c>122 then
				flag = true
				engotTopic=left(words,position)&"…"
				else
				position=position-1
				 if position=0 then exit do
				end if
				loop
			else
				engotTopic=words
			end if
	engotTopic=replace(replace(replace(engotTopic,chr(34),"&quot;"),">","&gt;"),"<","&lt;")        
	end function
	
使用方法：
	<%=engotTopic("Your job won't take care of you when you are sick. Your friends and parents will. Stay in touch.",17)%>
输出：Your job won't…