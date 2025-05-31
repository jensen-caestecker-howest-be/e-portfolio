---
layout: default
title: Welkom
---

# Welkom op mijn e-portfolio

<div style="display: flex; align-items: center; justify-content: space-between; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 250px;">
    <h2>Over mij</h2>
    <p>
      Als een gepassioneerde techenthousiast met een sterke focus op AI en algoritmes wil ik
      meebouwen aan innovatieve oplossingen die de wereld van morgen helpen vormgeven.
    </p>
  </div>
  <div style="flex-shrink: 0;">
    <img src="assets/img/20230913_124810.jpg" alt="Jensen Caestecker" style="width: 180px; border-radius: 10px;">
  </div>
</div>

---

## 📚 Posts

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: flex-start;">
{% for post in site.posts limit:6 %}
  <div style="flex: 0 1 calc(33% - 20px); background: #f9f9f9; border-radius: 10px; padding: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
    <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: inherit;">
      {% if post.image %}
        <img src="{{ post.image }}" alt="Post afbeelding" style="width: 100%; border-radius: 8px;" />
      {% endif %}
      <h3 style="margin-top: 10px;">{{ post.title }}</h3>
      <p style="color: #666;">{{ post.description }}</p>
    </a>
  </div>
{% endfor %}
</div>

---

## 📄 Over

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: flex-start;">

{% assign about_pages = site.pages | where_exp: "p", "p.url contains '/wie-ben-ik' or p.url contains '/how-i-built-this'" %}
{% for page in about_pages %}
  <div style="flex: 0 1 calc(33% - 20px); background: #f9f9f9; border-radius: 10px; padding: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
    <a href="{{ page.url | relative_url }}" style="text-decoration: none; color: inherit;">
      {% if page.image %}
        <img src="{{ page.image }}" alt="Afbeelding {{ page.title }}" style="width: 100%; border-radius: 8px;"/>
      {% endif %}
      <h3 style="margin-top: 10px;">{{ page.title }}</h3>
      <p style="color: #666;">{{ page.description }}</p>
    </a>
  </div>
{% endfor %}

</div>
