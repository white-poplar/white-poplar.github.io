            </div>
<!-- footer -->
            <footer class="clearfix visible-desktop">
                <div class="pull-right">
                    &copy; 2013 - <script> document.write(new Date().getFullYear());</script> <a href="{{ site.url }}" title="{{ site.owner.nickname }}" >{{ site.owner.name }}</a>.
                </div>
                <div>
                    Hosted by <a href="pages.github.com" title="GitHub Pages" >GitHub Pages</a> | UI Designed by <a href="{{ site.url }}" title="{{ site.owner.nickname }}">{{ site.owner.name }}</a>. | 托管商：<a href="github.com" title="GitHub">GitHub</a> | 图片存储：<a href="www.qiniu.com" title="七牛云存储">七牛云</a>
                </div>
            </footer>
            <footer class="clearfix hidden-desktop text-center">
                <div>
                    Hosted by <a href="pages.github.com" title="GitHub Pages" >GitHub Pages</a> | UI Designed by <a href="{{ site.url }}" title="{{ site.owner.nickname }}">{{ site.owner.name }}</a>. | 托管商：<a href="github.com" title="GitHub">GitHub</a> | 图片存储：<a href="www.qiniu.com" title="七牛云存储">七牛云</a>
                </div>
                <div>
                    &copy; 2013 - <script> document.write(new Date().getFullYear());</script> <a href="{{ site.url }}" title="{{ site.owner.nickname }}" >{{ site.owner.name }}</a>.
                </div>
            </footer>
<!-- /footer -->
        </div>
        <!-- <script src="js/bootstrap.min.js"></script> -->
        <script src="//cdn.bootcss.com/twitter-bootstrap/2.3.2/js/bootstrap.min.js"></script>
        <!-- <script type="text/javascript" src="{{ site.url }}/plugins/nprogress/nprogress.js"></script> -->
        <script src="//cdn.bootcss.com/nprogress/0.1.2/nprogress.min.js"></script>
<!-- Loading Bar -->
        <script type="text/javascript">
            NProgress.start();
            document.onreadystatechange=function () { 
                if ( document.readyState=="complete" ) { 
                    setTimeout(function () { NProgress.done(); }, 500);
                }
            }
        </script>
<!-- /Loading Bar -->
<!-- console -->
        <script type="text/javascript">
            try {
                console.log("\n%c{{ site.name }}\n%c真、\n","color:#333333;font-size: 16px;font-weight: bold;","color:#686868;padding-left: 60px;");
                console.log("等待永遠不能改變");
                console.log("Gtalk: %cBYH5566[#]gmail.com", "color:red");
                console.log("个人网站: https://white-poplar.github.io/");
                console.log("%c", "padding:218px 150px;line-height:460px;background:url('//white-poplar.qiniudn.com/img/Lin+Chi-ling.jpg') no-repeat;");
            } catch (e) {};
        </script>
<!-- /console -->
<!-- Google Analytics -->
        <script>
            (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
            (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
            m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
            })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

            ga('create', 'UA-50979340-1', 'white-poplar.github.io');
            ga('send', 'pageview');

        </script>
<!-- /Google Analytics -->
        <script type="text/javascript">
            try {
                console.timeEnd("Webpage timer");
            } catch (e) {};
        </script>
        <!-- Webpage timer end -->
    </body>
</html>