---
layout: default
title: "Blogs"
---

# 📝 Blogs

Explora los blogs disponibles sobre nuestras herramientas y metodologías.

| Blog | Descripción | Enlace |
|------|-------------|--------|
{% assign blogs = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "blogs" %}
{% for blog in blogs %}
| {{ blog.title }} | Blog sobre {{ blog.title }} | [Ver más]({{ blog.url | relative_url }}) |
{% endfor %}
