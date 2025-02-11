---
layout: default
title: "Artículos"
---

# 📑 Artículos

[🏠 Volver al inicio]({{ site.baseurl }}/) | [📖 Blogs]({{ site.baseurl }}/blogs/) | [📑 Artículos]({{ site.baseurl }}/articulos/) | [🎓 Tutoriales]({{ site.baseurl }}/tutoriales/)

Explora los artículos publicados sobre metodologías y mejores prácticas.

<table>
  <thead>
    <tr>
      <th>📄 Nombre</th>
      <th>🔗 Enlace</th>
    </tr>
  </thead>
  <tbody>
    {% assign articulos = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "articulos" %}
    {% for page in articulos %}
      {% assign title_lower = page.title | downcase %}
      {% assign without_prefix = title_lower | remove_first: "articulo-" %}
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
