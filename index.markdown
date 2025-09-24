---
layout: home
---

{% assign events = site.posts | where: "layout", "event" %}
{% assign stores = site.posts | where: "layout", "store" %}

<div class="group">
  <h2>Próximos Eventos</h2>
  <ul>
    {% for post in events reversed %}
      {% assign store = stores | where: "slug", post.store %}

      {% assign week_day = post.date | date: "%u" %}
      {% if week_day == '1' %}
          {% assign week = 'Seg' %}
      {% elsif week_day == '2' %}
          {% assign week = 'Ter' %}
      {% elsif week_day == '3' %}
          {% assign week = 'Qua' %}
      {% elsif week_day == '4' %}
          {% assign week = 'Qui' %}
      {% elsif week_day == '5' %}
          {% assign week = 'Sex' %}
      {% elsif week_day == '6' %}
          {% assign week = 'Sab' %}
      {% elsif week_day == '7' %}
          {% assign week = 'Dom' %}
      {% endif %}

      <li data-date="{{ post.date | date: "%y-%m-%d" }}">
        <h3>{{ post.date | date: "%d/%m (" }}{{ week }}{{ post.date | date: ") • %H:%M" }}</h3>
        <p>{{ post.store }}</p>
      </li>
    {% endfor %}

  </ul>
</div>

<div class="group">
  <h2>Lojas</h2>
  <ul>
    {% for post in stores reversed %}
      <li>
        <a href="{{ post.url | relative_url }}">
          <h3>{{ post.title }}</h3>
        </a>
      </li>
    {% endfor %}
  </ul>
</div>
