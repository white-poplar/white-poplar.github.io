<!DOCTYPE html>
<html lang="zh-CN">
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
        <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
        <!--

                            *o$&&&&&&&&&####&&&&&&&&$               
                         $$$$&&&####&###########&&&&&&&&            
                      $&&$$$&$&##&&&##########&&#&&&&&&&&&*         
                    o&&$$$$$&##&$&&####&##&&#&#&&&&&$$&&&&$$;       
                  $&&&&&&&&#&&$$&&&&&&&&&&&&$&&$&&$$&&&&#&&         
                ;&###&&##&#$$*$$$&&&&&&&&&$&$$$&$&&$&&##&#&##o      
               !&######&#&$*o***$$$$$$$&$&$&&$&&&&#&&&&#######&&*   
              !&######&&$*ooooooo***$$$&&&&&&&&&#############&#&&&&&
              $&&&###&$**ooooooooooo*$$&###&###################&&&&&
                $&##&$$ooooo!!oo!!!!!o$$#######################&&&&&
              $$$##&$*oooo!!o!!!!!!!!!!o$&######################&#&&
              &$###$**oooo!oo!!!!!!!!!;!!o*#######################&#
              &&##&&&&$***ooooooooooo!!!!!!o$##################&### 
              *&##$$$$$$$*oooo**$$$$$$*oo*o!o*$###################; 
               &##$&&$&$*$**oo*****o*o!o*oooooo*&&##############!   
                &#$o!o&&#*!;!oo**$&$$&$&$*oooo!oo*$&##########;     
                 ;;;o***oo;!;!!o*****&&o*ooo!!!!!!o$$&###$$$*!      
                 ;;;!!!!!!;;;;;;!oo$$**o!;;;;!!!!!oo$$$$$$*o**      
                 ; ;!!!!;!;;;;;;!!!!!!!;;;;;!!!!!ooo*$$$$$o!oo      
                 ; ;!!o!!;;;!;!!!!!!!!!!;;!!!!!!ooo***o*o*ooo       
                 ;;!ooo !!!;;;;!!!!!!!!!!!!!!!ooooo*oo!oo!o!        
                  !!ooo*oo**o!!ooooooo!oooo!ooooooo*o!!!!!;         
                  ;!oo;;;o$$$$$oooooooooooo*oooooo*$$ooo            
                   ;!**;!!*ooooooo****ooo**oooooo**$##&&;           
                    !*$;o**$$$****$&$$*ooooooo****$$&&$             
                     ;!;;oo**ooooo!oo****ooo****$**                 
                      ;;;!****oooo!!ooo******$$$*o*                 
                       ;;;ooooooooooooo*****$$*ooo*                 
                        ;!oooooooooooo*****$**oooo*                 
                         ;oo***********$$$$**oooooo;                
                             ;;!o$$$$$$$***ooooooooo                
                             ;;;o*$$$****oooo!!!oooo!               
                             ;;;!*****ooooo!!!!!!!!!!!              
                          ;; ;!!!o***oooo!!!!!!!!!!!!!!             
                    ;!;!;;;  ;!o!o*ooo!!!!!!!!!!!!!;;;;!!;          
                 ;o*;;;;;;   ;!oooooo!!!!!!!!!!!!!;;;;;;;!!!;       
           ;;;;;o$*;;;!!;;    !oooo!!!!!!!!!!!!!;;;;;;;;;;;;!!!     
          ;;; o*o;;!!!o!!;;!  !!!!!!!!!!!!!!!!;;;;;;;;;;;;;;;;;!!!  
          ; !*oo; ;;!!!!!!!!; !!!!!!!!!!!;;;;;;;;;;;;;;;;;;;;;;;;;!!
          ;*oo;;;   ;;;;;;;;;;!!;;;!!!;;;;;;;;;;;;;;;;;;;;;;;;;;;;;!
          ooo;;;;     ;;;;;;;!!;;;;!;;!;;;;;;;;;;;;;;;;;;;;o;;;;;;;!
          !!  ;;;;;;  ;;;;;;;;;;!;!!!!!;;;;;;;;;;;;;;;;;;!;;;;*;;$;o
          ;   ;;;;;;;;;;;;;;;;;!!!!!!!!!;;;;;;;;  ;;!;;;; ;;**; ;o!!


        PPPP   OOO  PPPP  L     AA  RRRR      BBBB  L     OOO   GGG  
        P   P O   O P   P L    A  A R   R     B   B L    O   O G     
        PPPP  O   O PPPP  L    AAAA RRRR      BBBB  L    O   O G  GG 
        P     O   O P     L    A  A R R       B   B L    O   O G   G 
        P      OOO  P     LLLL A  A R  RR     BBBB  LLLL  OOO   GGG  
                                                             
        @source: 支付志
        @design: white-poplar.
        @coding: white-poplar.

        @@@@ 与我联系 @@@@

        - QQ: 「1161057790」
        - WeChat: 「1161057790」
        - Gtalk: 「BYH5566@gmail.com」

        好吧，上圖其實是 Lin Chi-ling，console 一下，你就知道

        -->
        <title>{% if page.title %}{{ page.title }} | {% endif %}{{ site.name }}</title>
        <meta name="author" content="{{ site.owner.name }}.">
        <meta name="copyright" content="{{ site.owner.name }}.">
        {% if page.keywords %}<meta name="keywords" content="{{ page.keywords }}">{% else %}{% if site.keywords %}<meta name="keywords" content="{{ site.keywords }}">{% endif %}{% endif %}
        {% if page.description %}<meta name="description" content="{{ page.description }}">{% else %}{% if site.description %}<meta name="description" content="{{ site.description }}">{% endif %}{% endif %}
        <!-- Webpage timer begin -->
        <script type="text/javascript">
            try {
                console.time("Webpage timer");
            } catch (e) {};
        </script>
        <!-- iframe 方式弹广告 参考:http://en.wikipedia.org/wiki/Framekiller -->
        <style> html{display: none;} </style>
        <script>
            if ( self == top ) {
                document.documentElement.style.display = 'block' ; 
            } else {
                top.location = self.location ; 
            }
        </script>
        <link href="//cdn.bootcss.com/twitter-bootstrap/2.3.2/css/bootstrap.min.css" rel="stylesheet" media="screen">
        <link href="//cdn.bootcss.com/twitter-bootstrap/2.3.2/css/bootstrap-responsive.min.css" rel="stylesheet">
        <link href="//cdn.bootcss.com/nprogress/0.1.2/nprogress.min.css" rel="stylesheet">
		<link href="{{ site.fileUrl }}/css/style.css" rel="stylesheet">
        <!-- HTML5 shim, for IE6-8 support of HTML5 elements -->
        <!-- <script src="{{ site.fileUrl }}/js/html5shiv.min.js"></script> -->
        <!--[if lt IE 9]>
            <script src="//cdn.bootcss.com/html5shiv/3.7/html5shiv.min.js"></script>
        <![endif]-->
        <link rel="apple-touch-icon-precomposed" sizes="144x144" href="{{ site.fileUrl }}/ico/apple-touch-icon-144-precomposed.png">
        <link rel="apple-touch-icon-precomposed" sizes="114x114" href="{{ site.fileUrl }}/ico/apple-touch-icon-114-precomposed.png">
        <link rel="apple-touch-icon-precomposed" sizes="72x72" href="{{ site.fileUrl }}/ico/apple-touch-icon-72-precomposed.png">
        <link rel="apple-touch-icon-precomposed" href="{{ site.fileUrl }}/ico/apple-touch-icon-57-precomposed.png">
        <link rel="shortcut icon" href="{{ site.fileUrl }}/ico/favicon.png">
        <script src="//cdn.bootcss.com/jquery/1.11.0/jquery.min.js"></script>
    </head>
    <body>
        <div class="container">
            <div id="QRcode">
                <img src="{{ site.fileUrl }}/img/qrcode.png" alt="Qrcode">
                <br/>
                手机扫描二维码快速访问
            </div>
<!-- header -->
            <header class="header text-center">
                <div class="pb15">
                    <img src="{{ site.fileUrl }}/img/avatar.jpg" alt="avatar">
                    <div class="title"> {{ site.name }} </div>
                    <div class="description">{{ site.description }}</div>
                </div>
                <ul id="nav" class="inline">
                    <li><a href="{{ site.url }}">首页</a></li>
                    <li><a href="{{ site.url }}/pages">目录</a></li>
                    <li><a href="{{ site.url }}/about">关于我</a></li>
                </ul>
                <nav class="main-navigation"> </nav>
            </header>
<!-- /header -->
            <div id="main">