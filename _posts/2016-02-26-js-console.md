---
layout: posts
title: "js console 命令"
category: tech
tags: [JavaScript]
---

**Console** 控制台，是高版本浏览器带的一个调试JS命令、记录日志的功能。Firefox下安装**Firebug**插件，第一个面板就是。Chrome下打开开发者工具，选择Console面板。IE下打开开发人员工具，选择控制台，要求版本是 IE8+。（PS:快捷键打开按 **F12**）

<!--break-->

Console对象好像是浏览器内置的一个对象，不是js的，所以有的浏览器对Console对象的一些方法不支持，举个栗子，IE。

Console对象提供了5种方法用来显示信息。


	console.log("这是log");      //记录日志
	console.info("这是info");    //一般信息
	console.debug("这是debug");  //除错信息
	console.warn("这是warn");    //警告提示
	console.error("这是error");  //错误提示

> `console.debug("");` 在IE下不支持，所以调试或记录日志信息一般使用 `console.log("这是log");`就ok了，可以把过于强势的**alert**抛弃了。


下面是[百度](http://www.baidu.com/)首页的console招聘代码。

	try {
		if (window.console && window.console.log) {
			console.log("一张网页，要经历怎样的过程，才能抵达用户面前？\n一位新人，要经历怎样的成长，才能站在技术之巅？\n探寻这里的秘密；\n体验这里的挑战；\n成为这里的主人；\n加入百度，加入网页搜索，你，可以影响世界。\n");
			console.log("请将简历发送至 %c ps_recruiter@baidu.com（ 邮件标题请以“姓名-应聘XX职位-来自console”命名）", "color:red");
			console.log("职位介绍：http://dwz.cn/hr2013")
		}
	} catch (e) {};


下面是我博客的console代码，主要把基本的显示 文字 换行 段落 链接 图片 颜色 使用了下，以后有机会再看下其他的功能。

	console.log("\n%c白楊的博客\n%c真、\n","color:#333333;font-size: 16px;font-weight: bold;","color:#686868;padding-left: 60px;");
	console.log("等待永遠不能改變");
	console.log("Gtalk: %cBYH5566[#]gmail.com", "color:red");
	console.log("个人网站: http://white-poplar.github.io/");
	console.log("%c", "padding:218px 150px;line-height:460px;background:url('http://white-poplar.github.io/img/Lin+Chi-ling.jpg') no-repeat;");

**文字颜色在IE下无效，图片只有Chrome浏览器能显示**

PS:这里只是介绍了下console对象的一些方法的使用，在Console控制台内是可以直接运行JS代码操作网页元素什么的。

测试 [**GitHub**](https://github.com/) 网站内使用的 **MarkDown** ~~~

~~~ js
$(document).on('page:fetch',   function() { NProgress.start(); });
$(document).on('page:change',  function() { NProgress.done(); });
$(document).on('page:restore', function() { NProgress.remove(); });
~~~
