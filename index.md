---
layout: default
---
<ul class="post-list">
    {% for post in site.posts %}

    {% capture i18n_date_post %}
    {{ post.date | date: "%-d" }}
    {% assign m = post.date | date: "%-m" | minus: 1 %}
    {{ site.data.es.months[m] }}
    {{ post.date | date: "%Y" }}
    {% endcapture %}
    <li>
        <span class="post-meta">{{ i18n_date_post }}</span>

        <h2>
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h2>
    </li>
    {% endfor %}
</ul>
