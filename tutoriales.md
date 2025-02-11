---
layout: default
title: "Tutoriales"
---

# 🎓 Tutoriales

Encuentra tutoriales detallados sobre nuestras herramientas y procesos.

| Tutorial | Descripción | Enlace |
|----------|-------------|--------|
{% assign tutoriales = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "tutoriales" %}
{% for tutorial in tutoriales %}
| {{ tutorial.title }} | Tutorial sobre {{ tutorial.title }} | [Ver más]({{ tutorial.url | relative_url }}) |
{% endfor %}
