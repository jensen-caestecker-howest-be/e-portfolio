---
layout: default
title: Welkom
---

# Welkom op mijn e-portfolio

<div class="intro-flex">
  <div class="intro-text">
    <h2>Over mij</h2>
    <p>Als een gepassioneerde techenthousiast met een sterke focus op AI en algoritmes wil ik meebouwen aan innovatieve oplossingen die de wereld van morgen helpen vormgeven.</p>
  </div>
  <img src="assets/img/20230913_124810.jpg" alt="Jensen Caestecker" style="width: 180px; border-radius: 10px;" />
</div>

## 📚 Posts
<div class="card-grid">
{% for post in site.posts limit:6 %}
  <div class="card">
    {% if post.image %}
      <img src="{{ post.image }}" alt="Post afbeelding" />
    {% endif %}
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <p>{{ post.description }}</p>
  </div>
{% endfor %}
</div>

## 📄 Over

<div class="about-grid">
{% assign about_pages = site.pages | where_exp: "p", "p.permalink contains '/over'" or "p.url contains 'how-i-built'" %}
{% for page in about_pages %}
  <div class="about-card">
    <a href="{{ page.url | relative_url }}" style="text-decoration: none; color: inherit;">
      {% if page.image %}
        <img src="{{ page.image }}" alt="Afbeelding {{ page.title }}" />
      {% endif %}
      <h3>{{ page.title }}</h3>
      <p>{{ page.description }}</p>
    </a>
  </div>
{% endfor %}
</div>
