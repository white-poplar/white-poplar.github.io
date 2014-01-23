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
<!-- /pager -->