---
layout: default
---

<div class="row">
    <div class="medium-8 column">
        <h2>Galería</h2>
    </div>
    <div class="medium-4 column">
        <h2>Recursos</h2>
        <ul>
            <li><a href="/resources/resource_1.txt">Recurso 1</a></li>
            <li><a href="/resources/resource_2.txt">Recurso 2</a></li>
            <li><a href="/resources/resource_3.txt">Recurso 3</a></li>
            <li><a href="/resources/resource_4.txt">Recurso 4</a></li>
        </ul>
    </div>
</div>

## Vídeos
<div class="row medium-up-2">
    <div class="column">
        <div class="responsive-embed">
            <iframe width="560" height="315" src="https://www.youtube.com/embed/l9PxOanFjxQ" frameborder="0" allowfullscreen></iframe>
        </div>
    </div>
    <div class="column">
        <div class="responsive-embed">
            <iframe width="560" height="315" src="https://www.youtube.com/embed/l9PxOanFjxQ" frameborder="0" allowfullscreen></iframe>
        </div>
    </div>
</div>

## Publicaciones

 - [Publicación 1](publicacion_1)
 - [Publicación 2](publicacion_2)
 - [Publicación 3](publicacion_3)
 - [Publicación 4](publicacion_4)
 - [Publicación 5](publicacion_5)

## Prensa

 - [Artículo 1](articulo_1)
 - [Artículo 2](articulo_2)
 - [Artículo 3](articulo_3)
 - [Artículo 4](articulo_4)
 - [Artículo 5](articulo_5)

## Enlaces de interés

 - [Enlace 1](enlace_1)
 - [Enlace 2](enlace_2)
 - [Enlace 3](enlace_3)
 - [Enlace 4](enlace_4)
 - [Enlace 5](enlace_5)

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
