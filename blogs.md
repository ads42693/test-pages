---
layout: default
title: "Blogs"
---

# 📖 Blogs

Explora los blogs disponibles sobre nuestras herramientas y metodologías.

| Blog | Descripción | Enlace |
|------|------------|--------|
{% assign blogs = site.wiki | where: "categories", "blogs" %}
{% for page in blogs %}
| {{ page.title }} | Blog relacionado con nuestras herramientas | [Ver más]({{ page.url | relative_url }}) |
{% endfor %}
