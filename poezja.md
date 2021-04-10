---
layout: default
---

### poezja

<div class="posts_plain">
  {% for post in site.categories.liryka %}
    <article class="post_plain">

      &nbsp;&nbsp;&nbsp;
      <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>

    </article>
  {% endfor %}
</div>

### napisz

[aleksandra.horubala@gmail.com](mailto:aleksandra.horubala@gmail.com)
