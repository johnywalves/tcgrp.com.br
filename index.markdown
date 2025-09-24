---
layout: home
---

{% assign events = site.posts | where: "layout", "event" %}
{% assign stores = site.posts | where: "layout", "store" %}

<h2>Próximos Eventos</h2>
<ul>
  {% for post in events %}
    {% assign store = stores | where: "slug", post.store %}
    <li>
      <h3>{{ post.date }}</h3>
      <p>{{ post.slug }}</p>
      <p>{{ post.store }}</p>
    </li>
  {% endfor %}
</ul>

<h2>Lojas</h2>
<ul>
  {% for post in stores %}
    <li>
      <a href="{{ post.slug | append: ".html" }}"><h3>{{ post.title }}</h3></a>
    </li>
  {% endfor %}
</ul>
