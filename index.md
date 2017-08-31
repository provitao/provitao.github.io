---
layout: default
---

<div class="row">
    <div class="medium-8 column">
        <h2>Galería</h2>

        <div class="orbit" role="region" aria-label="Fotos del proyecto" data-orbit>
            <div class="orbit-wrapper">
                <div class="orbit-controls">
                    <button class="orbit-previous"><span class="show-for-sr">Siguiente</span>&#9664;&#xFE0E;</button>
                    <button class="orbit-next"><span class="show-for-sr">Anterior</span>&#9654;&#xFE0E;</button>
                </div>
                <ul class="orbit-container">
                    {% for slide in site.data.slides %}
                    {% if forloop.first %}
                    <li class="is-active orbit-slide">
                    {% else %}
                    <li class="orbit-slide">
                    {% endif %}
                        <figure class="orbit-figure">
                            <img class="orbit-image" src="{{ slide.src }}" alt="{{ slide.alt }}">
                            <figcaption class="orbit-caption">{{ slide.caption }}</figcaption>
                        </figure>
                    </li>
                    {% endfor %}
                </ul>
            </div>
            <nav class="orbit-bullets">
                {% for slide in site.data.slides %}
                {% if forloop.first %}
                <button class="is-active" data-slide="{{ forloop.index0 }}"><span class="show-for-sr">{{ slide.details }}</span><span class="show-for-sr"> Current Slide</span></button>
                {% else %}
                <button data-slide="{{ forloop.index0 }}"><span class="show-for-sr">{{ slide.details }}</span></button>
                {% endif %}
                {% endfor %}
            </nav>
        </div>

    </div>
    <div class="medium-4 column">
        <h2>Recursos</h2>
        <ul>
            {% for resource in site.data.resources %}
            <li><a href="{{ resource.href }}">{{ resource.label }}</a></li>
            {% endfor %}
        </ul>
    </div>
</div>

## Vídeos
<div class="row medium-up-2">
    {% for video in site.data.videos %}
    <div class="column">
        <div class="responsive-embed">
            <iframe width="560" height="315" src="{{ video.src }}" frameborder="0" allowfullscreen></iframe>
        </div>
    </div>
    {% endfor %}
</div>

## Publicaciones

    {% for publication in site.data.publications %}
    <li><a href="{{ publication.href }}">{{ publication.label }}</a></li>
    {% endfor %}

## Prensa

    {% for article in site.data.articles %}
    <li><a href="{{ article.href }}">{{ article.label }}</a></li>
    {% endfor %}

## Enlaces de interés

    {% for link in site.data.links %}
    <li><a href="{{ link.href }}">{{ link.label }}</a></li>
    {% endfor %}

## Blog
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
