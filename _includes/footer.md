            </div>
<!-- footer -->
            <footer class="clearfix hidden-phone" role="contentinfo">
                <div class="pull-right">
                    &copy; 2013 - <script> document.write(new Date().getFullYear());</script> <a href="{{ site.url }}" title="{{ site.owner.nickname }}" >{{ site.owner.name }}</a>.
                </div>
                <div>
                    Hosted by <a href="http://pages.github.com/" title="GitHub Pages" >GitHub Pages</a> | UI Designed by <a href="{{ site.url }}" title="{{ site.owner.nickname }}">{{ site.owner.name }}</a>. | 托管商：<a href="https://github.com/" title="GitHub">GitHub</a>                    
                </div>
            </footer>
            <footer class="clearfix visible-phone text-center" role="contentinfo">
                <div>
                    Hosted by <a href="http://pages.github.com/" title="GitHub Pages" >GitHub Pages</a> | UI Designed by <a href="{{ site.url }}" title="{{ site.owner.nickname }}">{{ site.owner.name }}</a>. | 托管商：<a href="https://github.com/" title="GitHub">GitHub</a>                    
                </div>
                <div>
                    &copy; 2013 - <script> document.write(new Date().getFullYear());</script> <a href="{{ site.url }}" title="{{ site.owner.nickname }}" >{{ site.owner.name }}</a>.
                </div>
            </footer>
<!-- /footer -->
        </div>
        <!-- <script src="js/jquery-1.9.1.min.js"></script> -->
        <script src="http://cdn.bootcss.com/jquery/1.9.1/jquery.min.js"></script>
        <!-- <script src="js/bootstrap.min.js"></script> -->
        <script src="http://cdn.bootcss.com/twitter-bootstrap/2.3.2/js/bootstrap.min.js"></script>
        <script type="text/javascript" src="{{ site.url }}/plugins/nprogress/nprogress.js"></script>
<!-- Loading Bar -->
        <script>
            NProgress.start();
            document.onreadystatechange=function(){ 
                if(document.readyState=="complete"){ 
                    setTimeout(function() { NProgress.done(); }, 500);
                } 
            }
        </script>
<!-- /Loading Bar -->
    </body>
</html>