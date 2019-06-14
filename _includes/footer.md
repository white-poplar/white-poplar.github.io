            </div>
<!-- footer -->
            <footer class="clearfix visible-desktop">
                <div class="pull-right">
                    &copy; 2013 - <script> document.write(new Date().getFullYear());</script> <a href="{{ site.url }}" title="{{ site.owner.nickname }}" >{{ site.owner.name }}</a>.
                </div>
                <div>
                    Hosted by <a href="//pages.github.com" title="GitHub Pages" >GitHub Pages</a> | UI Designed by <a href="{{ site.url }}" title="{{ site.owner.nickname }}">{{ site.owner.name }}</a>. | 托管商：<a href="//github.com" title="GitHub">GitHub</a> | 图片存储：<a href="//www.qiniu.com" title="七牛云存储">七牛云</a>
                </div>
            </footer>
            <footer class="clearfix hidden-desktop text-center">
                <div>
                    Hosted by <a href="//pages.github.com" title="GitHub Pages" >GitHub Pages</a> | UI Designed by <a href="{{ site.url }}" title="{{ site.owner.nickname }}">{{ site.owner.name }}</a>. | 托管商：<a href="//github.com" title="GitHub">GitHub</a> | 图片存储：<a href="//www.qiniu.com" title="七牛云存储">七牛云</a>
                </div>
                <div>
                    &copy; 2014 - <script> document.write(new Date().getFullYear());</script> <a href="{{ site.url }}" title="{{ site.owner.nickname }}" >{{ site.owner.name }}</a>.
                </div>
            </footer>
<!-- /footer -->
        </div>
        <script src="//cdn.bootcss.com/twitter-bootstrap/2.3.2/js/bootstrap.min.js"></script>
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
                console.log("\n%c{{ site.name }}\n%c真、\n","color:#333333;font-size: 16px;font-weight: bold;","color:#686868;padding-left: 72px;");
                console.log("等待永遠不能改變");
                console.log("Gtalk: %cBYH5566[#]gmail.com", "color:red");
                console.log("个人网站: {{ site.url }}");
                console.log("%c ", "padding:450px 300px 0 0;background:url('{{ site.fileUrl }}/img/Lin+Chi-ling.jpg') no-repeat;");
            } catch (e) {};
        </script>
<!-- /console -->
        <!-- Google Analytics -->
                
        <!-- /Google Analytics -->
        <!-- 百度统计 -->
        <script>
        var _hmt = _hmt || [];
        (function() {
          var hm = document.createElement("script");
          hm.src = "https://hm.baidu.com/hm.js?075c2a63127a4ee79b1592a9eca6f391";
          var s = document.getElementsByTagName("script")[0]; 
          s.parentNode.insertBefore(hm, s);
        })();
        </script>
        <!-- /百度统计 -->
        <script type="text/javascript">
            try {
                console.timeEnd("Webpage timer");
            } catch (e) {};
        </script>
        <!-- Webpage timer end -->
    </body>
</html>
