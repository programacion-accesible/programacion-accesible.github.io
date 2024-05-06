---
layout: page
title: programación
permalink: /programacion/
---

Post sobre programación y lenguajes:

{% capture category_name %}programacion{% endcapture %}

<div>
<h2 class="category-head">{{ category_name }}</h2>

    <ul>
    {% for post in site.categories[category_name] %}
      <li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>
    {% endfor %}
    </ul>

  </div>
