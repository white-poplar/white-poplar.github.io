<!-- pagination -->
                <div class="pagination">
                    <ul>
                        {% if paginator.previous_page %}
                            {% if paginator.previous_page == 1 %}
                        <li><a href="{{ site.url }}/" title="前一页">&laquo;</a></li>
                            {% else %}
                        <li><a href="{{{ site.url }}/page{{paginator.previous_page}}" title="前一页">&laquo;</a></li>
                            {% endif %}
                        {% else %}
                        {% if paginator.page == 1 %}
                        <li class="disabled"><a href="#">1</a></li>
                        {% else %}
                        <li><a href="{{ site.url }}/">1</a></li>
                        {% endif %}
                        {% pagelen  = (site.pagelen % 2) ? site.pagelen : site.pagelen + 1 #页码个数 %}
                        {% pageoffset = (pagelen -1 )/2 #页码个数左右偏移量  %}
                        {% if paginator.total_pages > site.pagelen # 总页数大于 页码个数 %}
                            {% if paginator.page <= pageoffset # 如果当前页小于等于左偏移 %}
                                {% if paginator.page == 1 %}
                                <li class="disabled"><a href="#">1</a></li>
                                {% else %}
                                <li><a href="{{ site.url }}/">1</a></li>
                                {% endif %}
                                {% for count in (2..paginator.total_pages) limit:pagelen %}
                                    {% if count == paginator.page %}
                                <li class="disabled"><a href="#">{{count}}</a></li>
                                    {% else %}
                                <li><a href="{{{ site.url }}/page{{count}}">{{count}}</a></li>
                                    {% endif %}
                                {% endfor %}
                            {% else #如果当前页大于左偏移 %}
                                {% if paginator.page + pageoffset >= paginator.total_pages + 1 #如果当前页码右偏移超出最大分页数 %}
                                    {% for count in (paginator.page - pagelen + 1 ..paginator.total_pages) limit:site.pagelen %}
                                        {% if count == paginator.page %}
                                    <li class="disabled"><a href="#">{{count}}</a></li>
                                        {% else %}
                                    <li><a href="{{{ site.url }}/page{{count}}">{{count}}</a></li>
                                        {% endif %}
                                    {% endfor %}
                                {% else %}
                                    {% for count in (paginator.page - pageoffset..paginator.total_pages) limit:site.pagelen %}
                                        {% if count == paginator.page %}
                                    <li class="disabled"><a href="#">{{count}}</a></li>
                                        {% else %}
                                    <li><a href="{{{ site.url }}/page{{count}}">{{count}}</a></li>
                                        {% endif %}
                                    {% endfor %}
                                {% endif %}
                            {% endif %}
                        {% else %}
                            {% if paginator.page == 1 %}
                            <li class="disabled"><a href="#">1</a></li>
                            {% else %}
                            <li><a href="{{ site.url }}/">1</a></li>
                            {% endif %}
                            {% for count in (2..paginator.total_pages) %}
                                {% if count == paginator.page %}
                            <li class="disabled"><a href="#">{{count}}</a></li>
                                {% else %}
                            <li><a href="{{{ site.url }}/page{{count}}">{{count}}</a></li>
                                {% endif %}
                            {% endfor %}
                        {% endif %}
                        {% if paginator.next_page %}
                        <li><a href="{{{ site.url }}/page{{paginator.next_page}}" title="后一页">&raquo;</a></li>
                        {% else %}
                        <li class="disabled"><a href="#" title="后一页">&raquo;</a></li>
                        {% endif %}
                    </ul>
                </div>
<!-- /pagination -->