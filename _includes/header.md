<!DOCTYPE html>
<html lang="zh-CN">
    <head>
        <meta charset="utf-8" />
        <title>{{ page.title }} | {{ site.title }}</title>
        <meta name="author" content="{{ site.owner.name }}." />
        <meta name="copyright" content="{{ site.owner.name }}." />
        {% if page.keywords %}<meta name="keywords" content="{{ page.keywords }}">{% else %}{% if site.keywords %}<meta name="keywords" content="{{ site.keywords }}" />{% endif %}{% endif %}
        {% if page.description %}<meta name="description" content="{{ page.description }}">{% else %}{% if site.description %}<meta name="description" content="{{ site.description }}" />{% endif %}{% endif %}
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <!-- iframe 方式弹广告 参考:http://en.wikipedia.org/wiki/Framekiller -->
        <style> html{display: none;} </style>
        <script>
           if( self == top ) {
               document.documentElement.style.display = 'block' ; 
           } else {
               top.location = self.location ; 
           }
        </script>
        <!-- <link href="css/bootstrap.min.css" rel="stylesheet" media="screen" /> -->
        <link href="http://cdn.bootcss.com/twitter-bootstrap/2.3.2/css/bootstrap.min.css" rel="stylesheet" media="screen" />
        <!-- <link href="css/bootstrap-responsive.min.css" rel="stylesheet" /> -->
        <link href="http://cdn.bootcss.com/twitter-bootstrap/2.3.2/css/bootstrap-responsive.min.css" rel="stylesheet" />
        <link href="{{ site.url }}/css/style.css" rel="stylesheet" />
        <!-- HTML5 shim, for IE6-8 support of HTML5 elements -->
        <!-- <script src="js/html5shiv.min.js"></script> -->
        <!--[if lt IE 9]>
            <script src="http://cdn.bootcss.com/html5shiv/3.7/html5shiv.min.js"></script>
        <![endif]-->
        <link rel="apple-touch-icon-precomposed" sizes="144x144" href="ico/apple-touch-icon-144-precomposed.png">
        <link rel="apple-touch-icon-precomposed" sizes="114x114" href="ico/apple-touch-icon-114-precomposed.png">
          <link rel="apple-touch-icon-precomposed" sizes="72x72" href="ico/apple-touch-icon-72-precomposed.png">
                        <link rel="apple-touch-icon-precomposed" href="ico/apple-touch-icon-57-precomposed.png">
                                       <link rel="shortcut icon" href="ico/favicon.png">
    </head>
    <body>
        <div class="container">
<!-- header -->
            <header class="text-center" role="banner">
                <hgroup class="pb15">
                    <img src="img/avatar.jpg" alter="avatar" />
                    <div class="title"> {{ site.title }} </div>
                    <div class="description">{{ site.description }}</div>
                </hgroup>
                <ul id="nav" class="inline">
                    <li><a href="{{ site.url }}/">首页</a></li>
                    <li><a href="{{ site.url }}/page.html">目录</a></li>
                    <li><a href="{{ site.url }}/about.html">关于我</a></li>
                </ul>
                <nav class="main-navigation"> </nav>
            </header>
<!-- /header -->
            <div id="main" role="content">
