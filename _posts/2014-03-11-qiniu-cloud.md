---
layout: post
title: "网页图片加速 => 云存储"
category: tech
tags: [云存储, 图片加速]
---

![云存储](http://white-poplar.qiniudn.com/posts/img/Cloud-Storage-Services.jpg?watermark/1/image/aHR0cDovL3doaXRlLXBvcGxhci5xaW5pdWRuLmNvbS93YXRlcm1hcmsucG5n/dissolve/50/gravity/SouthEast/dx/5/dy/5)

之前就听到过云存储什么东东的，但自己也没去深入去了解这些。前两天突然想在博客的文章上配张图，而如果继续在 [GitHub](https://github.com/ "GitHub") 上添加图片，先不说速度问题，而是 [GitHub](https://github.com/ "GitHub") 已经是免费的了，再在其上面添加大量的图片，真的大丈夫吗？

所以搜了下图片存储相关方面的内容，发现在云存储方面比较好的有 [七牛云](http://www.qiniu.com/ "七牛云") 和 [又拍云](https://www.upyun.com/index.html "又拍云")。
<!--break-->
之后分别注册了两个网站的账号， [七牛云](http://www.qiniu.com/ "七牛云") 每月有10Gb流量 + 10Gb存储的免费套餐，而 [又拍云](https://www.upyun.com/index.html "又拍云") 好像没有什么免费的套餐，搜了下资料说是主要是面向公司的，服务定位就是收费的服务，这样在经济上才能不断的完善和优化我们的服务，给客户更棒的使用体验。

对于几乎没什么流量的博客来说（全是泪啊），选择 [七牛云](http://www.qiniu.com/ "七牛云") 是毋庸置疑的了。（别说我占什么便宜啊！）

在七牛云上注册验证号账号后，就可以使用了。（七牛云的网站操作还挺好的，这就是传说中的用户体验吧！）

新建个空间，由于要在博客文章中使用，选择公开空间，之后在内容管理栏目上传图片。点击上传的图片就可以看到外链地址，对就是他了。

在数据处理栏目，可以设置图片处理什么的信息，但功能不是很强大，功能强大的则要使用他们提供的 `API` 了。  
具体参考：

* [图片处理（imageView2）](http://developer.qiniu.com/docs/v6/api/reference/fop/image/imageview2.html "图片处理（imageView2）")
* [高级图像处理（imageMogr2）](http://developer.qiniu.com/docs/v6/api/reference/fop/image/imagemogr2.html "高级图像处理（imageMogr2）")
* [水印（watermark）](http://developer.qiniu.com/docs/v6/api/reference/fop/image/watermark.html "水印（watermark）")

我主要使用了水印和缩略图的功能：

	* 水印
		1. 上传一张水印源图片 http://white-poplar.qiniudn.com/watermark.png
		2. 将路径经过Base64编码 (请百度) aHR0cDovL3doaXRlLXBvcGxhci5xaW5pdWRuLmNvbS93YXRlcm1hcmsucG5n
		3. 效果 http://white-poplar.qiniudn.com/img/5cm.jpg?watermark/1/image/aHR0cDovL3doaXRlLXBvcGxhci5xaW5pdWRuLmNvbS93YXRlcm1hcmsucG5n/dissolve/50/gravity/SouthEast/dx/5/dy/5
	* 缩略图
		http://white-poplar.qiniudn.com/img/5cm.jpg?imageView2/1/w/200/h/200

PS：参数什么的 `API` 好像给的挺详细的，多看！好像没提到图片加速啊，⊙﹏⊙b汗，反正他们使用的是什么CDN加速什么的。（好吧，确实不是很清楚什么CDN）

另：如果有童鞋要注册的话，请使用 [https://portal.qiniu.com/signup?code=3ljldv1wzuwcy](https://portal.qiniu.com/signup?code=3ljldv1wzuwcy) ，没什么不同，只是通过这个链接注册七牛云那边会送我5Gb的下载流量，么么哒！

>配图来源 [Google 图片](https://www.google.com.hk/imghp?hl=zh-CN "Google 图片") 