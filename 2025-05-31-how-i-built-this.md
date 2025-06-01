---
layout: default
title: "Hoe ik deze website bouwde"
description: "Uitleg over de technische setup van mijn e-portfolio."
image: /assets/img/site-workflow.png
permalink: /how-i-built-this/
---

# Hoe ik deze site heb gebouwd

Deze e-portfolio is gebouwd met behulp van **GitHub Pages** en **Jekyll**, een statische site generator. Het doel was om een snelle, eenvoudige en onderhoudsvriendelijke site op te zetten zonder afhankelijk te zijn van externe CMS-systemen zoals WordPress.

## 📁 Structuur

- `_posts/` bevat alle blogposts in Markdown-formaat. Ze worden automatisch opgepikt door Jekyll op basis van de bestandsnaam (`YYYY-MM-DD-title.md`).
- `index.md` bevat de hoofdpagina, met een korte intro, de laatste blogposts in een grid, en een "Over" sectie.
- `assets/img/` bevat alle afbeeldingen die gebruikt worden in de posts en pagina's.
- `about.md` en deze pagina bevinden zich in de root van de repository.

## 🎨 Thema en layout

- Het gebruikte theme is **Cayman** via `remote_theme: pages-themes/cayman@v0.2.0` in de `_config.yml`.
- CSS wordt enkel inline gebruikt om te vermijden dat het standaardtheme overschreven wordt.
- De layout is volledig responsive, met behulp van flexbox (inline styles).

## ⚙️ GitHub Pages & Jekyll

- De site wordt automatisch gegenereerd en gehost via **GitHub Pages**.
- De posts en pagina's gebruiken YAML front matter (`---`) om metadata zoals layout, title, image en description toe te voegen.
- Alle links gebruiken `{{ ... | relative_url }}` voor compatibiliteit met GitHub Pages.

## 🧠 Waarom deze aanpak?
Ik koos voor GitHub Pages omdat het:
- Gratis is
- Open source en professioneel oogt
- Volledig onder mijn controle staat

## 📌 Wat ik geleerd heb

- Hoe Jekyll posts en pagina's rendert op basis van front matter en mappenstructuur.
- Het verschil tussen `site.pages` en `site.posts`.
- Hoe CSS de standaard layout kan beïnvloeden, en hoe ik dat gecontroleerd kan inzetten.
- Het gebruik van Liquid templates `(`{% raw %}{% for post in site.posts %}{% endraw %}`)`
---
Nieuwe blogposts toevoegen doe ik eenvoudig door een `.md`-bestand aan te maken in de `/posts`-map en die te linken op de homepage.
