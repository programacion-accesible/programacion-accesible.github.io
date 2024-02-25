---
layout: page
title: Noticias sobre la comunidad de programación accesible
permalink: /comunidad/
---

Nuestras novedades:

{% capture category_name %}comunidad{% endcapture %}
<div>
<h2 class="category-head">{{ category_name }}</h2>

    <ul>
    {% for post in site.categories[category_name] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>
    {% endfor %}
    </ul>
  </div>