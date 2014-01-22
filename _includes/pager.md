<!-- pager -->
                <nav class="nav-single">
                    <ul class="pager">
                        {% if page.previous %}
                        <li class="previous">
                            <a href="{{ site.url }}{{ page.previous.url }}">&larr; {{ page.previous.title }}</a>
                        </li>
                        {% else %}
                        <li class="previous disabled">
                            <a href="#">&larr; None</a>
                        </li>
                        {% endif %}
                        {% if page.next %}
                        <li class="next">
                            <a href="{{ site.url }}{{ page.next.url }}" >{{ page.next.title }} &rarr;</a>
                        </li>
                        {% else %}
                        <li class="next disabled">
                            <a href="#">None &rarr;</a>
                        </li>
                        {% endif %}
                    </ul>
                </nav>
                <script type="text/javascript">
                $(function () {
                    $(document).keydown(function(e) {
                        var url = false;
                        if (e.which == 37 || e.which == 74) {  // Left arrow and J
                            {% if page.previous %}
                            url = '{{ site.url }}{{ page.previous.url }}';
                            {% endif %}
                        }
                        else if (e.which == 39 || e.which == 75) {  // Right arrow and K
                            {% if page.next %}
                            url = '{{ site.url }}{{ page.next.url }}';
                            {% endif %}
                        }
                        if (url) {
                            window.location = url;
                        }
                    });
                });
                </script>
<!-- /pager -->