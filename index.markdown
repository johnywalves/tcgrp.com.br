---
layout: home
---

<div class="title">
  <h1>{{ site.title }}</h1>
  <p class="description">{{ site.description }}</p>
</div>

<div class="group games">
  <h2>Trading Card Game</h2>
  <a href="/digimon">
    <img src="/logos/digimon.svg" width="450">
  </a>

  <a href="/gundam">
    <img src="/logos/gundam.png" width="250">
  </a>
</div>

{% assign events = site.posts | where: "layout", "event" %}

{% include next_events.html %}
