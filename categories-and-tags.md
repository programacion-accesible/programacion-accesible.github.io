---
layout: page
title: categorías y etiquetas
permalink: /data
---

Es importante seleccionar bien la categoría y la etiquetas de tu post en este sitio. Seguiremos las normativas que suelen llevar los blogs como 
[wordpress](https://neliosoftware.com/es/blog/categorias-y-etiquetas-en-wordpress/){:target="_blank"}  
Selecciona bien la categoría de tu post, no se pueden crear nuevas.  
elije las etiquetas para tu blog, cual es el tema mas importante de tu post.  
  
Nuestro criterio a seguir será:  
* Cada post podrá pertenecer a una sola categoría existente.
* Cada post podrá tener   varias etiquetas.

## categorías:

<ul id="categorias" style="list-style-type: none;">
{% for category in site.categories %}
  {% capture category_name %}{{ category | first }}{% endcapture %}
  <li><a href="{{ site.baseurl }}/{{ category_name }}">{{ category_name }}</a></li>
{% endfor %}
</ul>

## etiquetas:

<ul id="tags" style="list-style-type: none;">
{% for tag in site.tags %}
  {% capture tag_name %}{{ tag | first }}{% endcapture %}
  <li><a href="{{ site.baseurl }}/tag/{{ tag_name }}">{{ tag_name }}</a></li>
{% endfor %}
</ul>