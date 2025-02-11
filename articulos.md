---
layout: default
title: "Artículos"
---

# 📑 Artículos

Encuentra artículos detallados sobre nuestras prácticas y tecnología.

| Artículo | Descripción | Enlace |
|----------|-------------|--------|
{% assign articulos = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "articulos" %}
{% for articulo in articulos %}
| {{ articulo.title }} | Artículo sobre {{ articulo.title }} | [Ver más]({{ articulo.url | relative_url }}) |
{% endfor %}
