---
layout: posts
title: "Tencent 前端突击队 （第二季）"
category: programming
tags: [CSS3]
---

![Tencent 前端突击队]({{ site.url }}/img/posts/tencent2-fix.jpg)

周六晚上，浏览信息时看到腾讯 [前端突击队](http://codestar.alloyteam.com/ "前端突击队") 第二季出了,觉得挺有意思的，就完了会，一发不可收拾，玩到了凌晨3点。

游戏开始时提示通关会有福利的，最后通关后发现就是上图的漂亮妹子的`等我找你~`(⊙o⊙)…

图片丢了 o(╥﹏╥)o
<!--break-->
游戏里面的题目感觉还是挺难的，唉，前端水很深，路还很长啊！

下面记录下自己感觉比较实用的题目里面出现的知识点：

 **水平&垂直居中** [DEMO](/demo/absolute-centering/ "水平&垂直居中")

	------ 负外边距 ------
	#wrapper { 
		width:800px;
		height:400px;
		position:absolute;
		top:50%;
		left:50%;
		margin:-200px 0 0 -400px;
	}
	.is-Negative {  
		width: 300px;  
		height: 200px;  
		padding: 20px;  
		position: absolute;  
		top: 50%; left: 50%;  
		margin-left: -170px; /* (width + padding)/2 */  
		margin-top: -120px; /* (height + padding)/2 */  
	}
	------ 绝对定位居中 (IE8+) ------
	.Absolute-Center {  
		margin: auto;  
		position: absolute;  
		top: 0; 
		left: 0; 
		bottom: 0; 
		right: 0;  
		overflow: auto; /*建议设置overflow:auto来防止内容越界溢出*/
	}
	------ 表格单元格（Table-Cell） ------
	HTML:
    <div class="Center-Container is-Table">
        <div class="Table-Cell">
            <div class="Center-Block">表格单元格（Table-Cell）</div>
        </div>
    </div>
	CSS:
	.Center-Container.is-Table { 
	    display: table; 
	    width: 100%;
	    height: 100%;
	}
	.is-Table .Table-Cell {  
		display: table-cell;  
		vertical-align: middle;  
	}  
	.is-Table .Center-Block {  
	    width: 50%;  
	    height: 50%;
	    margin: 0 auto;
	    background-color: #040;
	} 

 **CSS3 @keyframes** [DEMO](/demo/keyframes/ "CSS3 @keyframes")

	#box {
	    width:100px;
	    height:100px;
	    background-color: #040;
	    position:relative;
	    animation:Dmove 8s infinite;
	    -moz-animation:Dmove 8s infinite; /* Firefox */
	    -webkit-animation:Dmove 8s infinite; /* Safari and Chrome */
	    -o-animation:Dmove 8s infinite; /* Opera */
	}
	@keyframes Dmove {
	    0% {top:0px;}
	    50% {top:200px; background-color: #f00;}
	    100% {top:0px;}
	}
	@-moz-keyframes Dmove { /* Firefox */
	    0% {top:0px;}
	    50% {top:200px; background-color: #f00;}
	    100% {top:0px;}
	}
	@-webkit-keyframes Dmove { /* Safari and Chrome */
	    0% {top:0px;}
	    50% {top:200px; background-color: #f00;}
	    100% {top:0px;}
	}
	@-o-keyframes Dmove { /* Opera */
	    0% {top:0px;}
	    50% {top:200px; background-color: #f00;}
	    100% {top:0px;}
	}

**Css3-flexbox** [http://www.w3.org/html/ig/zh/wiki/Css3-flexbox/zh-hans](http://www.w3.org/html/ig/zh/wiki/Css3-flexbox/zh-hans)

	display: flex; 
	flex: 1;

	水有些深，mark 下地址

>配图来源 [Tencent 前端突击队](http://codestar.alloyteam.com/q2/ "Tencent 前端突击队") 

***

音悦台 [高桥优 - 少年であれ](http://v.yinyuetai.com/video/174322 "高桥优 - 少年であれ")

	成为在这个星球上
	谁都不由自主
	爱上的那个少年吧