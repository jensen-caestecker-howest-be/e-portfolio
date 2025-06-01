---
layout: default
title: Welkom
---

# Welkom op mijn e-portfolio

<div style="display: flex; align-items: center; justify-content: space-between; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1 1 300px;">
    <h2>Over mij</h2>
    <p>Als een gepassioneerde techenthousiast met een sterke focus op AI en algoritmes wil ik meebouwen aan innovatieve oplossingen die de wereld van morgen helpen vormgeven.</p>
  </div>
  <img src="assets/img/20230913_124810.jpg" alt="Jensen Caestecker" style="width: 180px; border-radius: 10px;">
</div>

---

## 📚 Posts

<div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: flex-start;">
  {% for post in site.posts %}
  <div style="flex: 0 1 calc(33% - 20px); background: #f9f9f9; padding: 15px; margin-bottom: 20px; border-radius: 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.1);">
    <a href="{{ post.url }}" style="text-decoration: none; color: inherit;">
      {% if post.image %}
        <img src="{{ post.image }}" alt="{{ post.title }}" style="width: 100%; border-radius: 8px;"/>
      {% endif %}
      <h3>{{ post.title }}</h3>
      <p>{{ post.description }}</p>
    </a>
  </div>
  {% endfor %}
</div>

---

## 📄 Over

<div style="display: flex; flex-wrap: wrap; gap: 20px;">
  <div style="flex: 0 1 45%; background: #f9f9f9; padding: 15px; border-radius: 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); margin-bottom: 20px;">
    <a href="{{ '/about.html' | relative_url }}" style="text-decoration: none; color: inherit;">
      <h3>Wie ben ik</h3>
      <p>Leer meer over mijn achtergrond, interesses en motivatie.</p>
    </a>
  </div>

  <div style="flex: 0 1 45%; background: #f9f9f9; padding: 15px; border-radius: 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); margin-bottom: 20px;">
    <a href="{{ '/2025-05-31-how-i-built-this.html' | relative_url }}" style="text-decoration: none; color: inherit;">
      <h3>Hoe ik deze site heb gebouwd</h3>
      <p>Een overzicht van de tools en technologieën die ik gebruikt heb om deze site op te bouwen.</p>
    </a>
  </div>
</div>
