---
layout: post
title: ".Net Framework  设置"
category: programming
tags: [.Net]
---

在使用 `VS2010` 开发的项目中，引用了 `dll`，也写了 `using` ,使用时可以正常使用，但编译却提示**未能找到类型或命名空间名称**。

<!--break-->

今天使用 [动软代码生成器](http://www.maticsoft.com/download.aspx#5) 生成.Net简单三层结构时，因为需要写 **WPF** 项目，所以就把生成的 **Web** 层项目删掉了，之后自己新建了个 **WPF** 项目，在项目中引用业务层 `dll` 后，在代码中使用时是ok的，但每次编译时就提示**未能找到类型或命名空间名称**。

百度了一下好像没有找到什么解决办法，之后还是 google 了一下才找到问题原因。

在使用 [动软代码生成器](http://www.maticsoft.com/download.aspx#5) 生成代码时，生成项目的目标框架是 `.NET Framework 3.5` ，而用 `VS2010` 打开，新建项目时默认目标框架是 `.NET Framework 4`，所以出现了问题。只需要把需要用到的项目的目标框架改为相同的就OK，右键项目 -> 选择属性 -> 选择应用程序 -> 修改目标框架 -> 完成。 