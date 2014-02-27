---
layout: post
title: "jQuery 中ajax、post 、get的同步"
category: programming
tags: [JavaScript, jQuery]
---

sync默认的设置值为true，这种情况为异步方式，就是说当ajax发送请求后，在等待server端返回的这个过程中，前台会继续执行ajax块后面的脚本，直到server端返回正确的结果才会去执行success，也就是说这时候执行的是两个线程，ajax块发出请求后一个线程和ajax块后面的脚本（另一个线程）；

### 解决办法一：

**1.全局设置：**  

	$.ajaxSetup({   
		async : false  
	});  

**2.使用post或get方法;**	

<!--break-->

### 解决办法二：

直接使用`$.ajax`  

	$.ajax({   
		async : false;
	});  
	