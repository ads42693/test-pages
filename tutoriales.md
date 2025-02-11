---
layout: default
title: "Tutoriales"
---

# 🎓 Tutoriales

[🏠 Volver al inicio]({{ site.baseurl }}/) | [📖 Blogs]({{ site.baseurl }}/blogs/) | [📑 Artículos]({{ site.baseurl }}/articulos/) | [🎓 Tutoriales]({{ site.baseurl }}/tutoriales/)

Explora los tutoriales detallados disponibles.

<table>
  <thead>
    <tr>
      <th>📄 Nombre</th>
      <th>🔗 Enlace</th>
    </tr>
  </thead>
  <tbody>
    {% assign tutoriales = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "tutoriales" %}
    {% for page in tutoriales %}
      {% assign title_lower = page.title | downcase %}
      {% assign without_prefix = title_lower | remove_first: "tutorial-" %}
      {% assign clean_name = without_prefix | strip | capitalize %}
      <tr>
        <td>{{ clean_name }}</td>
        <td>
          <a class="btn btn-primary text-dark" 
             href="{{ page.url | relative_url }}" 
             style="color: #007bff; text-decoration: underline;">
            Ver más
          </a>
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>
