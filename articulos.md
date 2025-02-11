---
layout: default
title: "Artículos"
---

# 📑 Artículos

Explora los artículos publicados sobre metodologías y mejores prácticas.

| Artículo | Descripción | Enlace |
|----------|-------------|--------|
{% assign articulos = site.wiki | where: "categories", "articulos" %}
{% for page in articulos %}
| {{ page.title }} | Artículo técnico relevante | [Ver más]({{ page.url | relative_url }}) |
{% endfor %}
