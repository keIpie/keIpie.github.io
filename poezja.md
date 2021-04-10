---
layout: default
---

### poezja

<div class="posts_plain">
  {% for post in site.categories.liryka %}
    <article class="post_plain">

    	<h3><a href="{{ site.baseurl }}{{ post.url }}"> &nbsp;&nbsp;&nbsp; {{ post.title }}</a></h3>

    </article>
  {% endfor %}
</div>

### napisz

[aleksandra.horubala@gmail.com](mailto:aleksandra.horubala@gmail.com)
