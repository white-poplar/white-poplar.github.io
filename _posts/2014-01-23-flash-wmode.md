---
layout: posts
title: "网页下拉菜单被flash动画遮住"
category: programming
tags: [html]
---

我们在网页中插入flash时，通常使用下面的代码：

	<object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,29,0" width="960" height="258">
		<param name="movie" value="banner.swf">
		<param name="quality" value="high">
		<param name="menu" value="false">
		<embed src="banner.swf" width="960" height="258" quality="high" pluginspage="http://www.macromedia.com/go/getflashplayer" type="application/x-shockwave-flash" menu="false" wmode="transparent"></embed>
	</object>
	
<!--break-->

但是如果有下拉菜单或漂浮层在其区域时会被flash遮住，设置`z-index`不起作用，解决的办法是：

IE：添加 `<param name="wmode" value="transparent">` 语句；

FF: 火狐里FLASH是用EMBED实现的，所以在 `<embed>` 里加 wmode="transparent" 即 `<embed wmode="transparent" 其他参数\>` 

最终代码：

	<object classid="clsid:D27CDB6E-AE6D-11cf-96B8-444553540000" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,29,0" width="960" height="258">
		<param name="movie" value="banner.swf">
		<param name="quality" value="high">
		<param name="menu" value="false">
		<param name="wmode" value="transparent">
		<embed src="banner.swf" wmode="transparent" width="960" height="258" quality="high" pluginspage="http://www.macromedia.com/go/getflashplayer" type="application/x-shockwave-flash" menu="false"></embed>
	</object>