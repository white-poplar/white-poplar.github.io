<!-- pagination -->
                <div class="pagination">
                    <ul>
                        {% if paginator.previous_page %}
                        <li><a href="{{paginator.previous_page_path}}" title="前一页">&laquo;</a></li>
                        {% else %}
                        <li class="disabled"><a href="#" title="前一页">&laquo;</a></li>
                        {% endif %}
                        {% for page in (1..paginator.total_pages) %}
                            {% if page == paginator.page %}
                              <li class="disabled"><a href="#">{{page}}</a></li>
                            {% elsif page == 1 %}
                              <li><a href="{{ '/pages/' | prepend: site.url | replace: '//', '/' }}">{{page}}</a></li>
                            {% else %}
                              <li><a href="{{ site.paginate_path | prepend: site.url | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a></li>
                            {% endif %}
                        {% endfor %}
                        {% if paginator.next_page %}
                        <li><a href="{{paginator.next_page_path}}" title="后一页">&raquo;</a></li>
                        {% else %}
                        <li class="disabled"><a href="#" title="后一页">&raquo;</a></li>
                        {% endif %}
                    </ul>
                </div>
<!-- /pagination -->
<!-- 第{{paginator.page}}页/共{{paginator.total_pages}}页 -->