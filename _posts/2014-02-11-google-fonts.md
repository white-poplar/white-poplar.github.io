---
layout: posts
title: "Google Web Fonts"
category: tech
tags: [Web, CSS]
---

Google Fonts API 是 Google 推出的一项免费的字体服务，有600多种（2014.02）字体，只需引用一串 link 样式，之后就和定义普通的网页字体一样，font-family、font-weight、font-style、line-height 等进行定义字体。  
这是我做的一个 [DEMO](/demo/google-fonts/ "Google Fonts API")

<!--break-->

** Google Font API **


1.进入 Google Web Fonts 主页 [https://www.google.com/fonts/](https://www.google.com/fonts/)，选择字体，我选了Arbutus、Over the Rainbow、Mystery Quest 字体。  
2.选择 `Use`，进入 `Almost done!` 页面，选择完成。  
3.将字体使用到自己网站中，有三种方法：

	方法一：
	<link href='http://fonts.googleapis.com/css?family=Arbutus|Over+the+Rainbow|Mystery+Quest' rel='stylesheet' type='text/css'>
	方法二：
	@import url(http://fonts.googleapis.com/css?family=Arbutus|Over+the+Rainbow|Mystery+Quest);
	方法三：
	<script type="text/javascript">
	  WebFontConfig = {
		google: { families: [ 'Arbutus::latin', 'Over+the+Rainbow::latin', 'Mystery+Quest::latin' ] }
	  };
	  (function() {
		var wf = document.createElement('script');
		wf.src = ('https:' == document.location.protocol ? 'https' : 'http') +
		  '://ajax.googleapis.com/ajax/libs/webfont/1/webfont.js';
		wf.type = 'text/javascript';
		wf.async = 'true';
		var s = document.getElementsByTagName('script')[0];
		s.parentNode.insertBefore(wf, s);
	  })(); 
	</script>

4.使用时和普通的网页字体一样。

[DEMO](/demo/google-fonts/ "Google Fonts API")