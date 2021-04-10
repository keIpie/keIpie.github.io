---
layout: default
---

### poezja

<div class="posts">
  {% for post in site.categories.liryka %}
    <article class="post">

      <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>

    </article>
  {% endfor %}
</div>

### napisz

[aleksandra.horubala@gmail.com](mailto:aleksandra.horubala@gmail.com)
