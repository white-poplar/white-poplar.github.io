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
                        <li class="disabled"><a href="#" title="前一页">&laquo;</a></li>
                        {% endif %}
                        {% for count in (1..paginator.total_pages) limit:2 %}
                            {% if count == paginator.page %}
                        <li class="disabled"><a href="#">{{count}}</a></li>
                            {% else %}
                        <li><a href="{{{ site.url }}/page{{count}}">{{count}}</a></li>
                            {% endif %}
                        {% endfor %}
                        {% if paginator.next_page %}
                        <li><a href="{{{ site.url }}/page{{paginator.next_page}}" title="后一页">&raquo;</a></li>
                        {% else %}
                        <li class="disabled"><a href="#" title="后一页">&raquo;</a></li>
                        {% endif %}
                    </ul>
                </div>
<!-- /pagination -->
<!-- 第{{paginator.page}}页/共{{paginator.total_pages}}页 -->