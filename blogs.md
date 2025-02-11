---
layout: default
title: "Blogs"
---

# 📖 Blogs

[⬅ Volver al inicio]({{ site.baseurl }}/)

Explora los blogs disponibles sobre nuestras herramientas y metodologías.

<table>
  <thead>
    <tr>
      <th>📄 Nombre</th>
      <th>🔗 Enlace</th>
    </tr>
  </thead>
  <tbody>
    {% assign blogs = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "blogs" %}
    {% for page in blogs %}
      {% assign title_lower = page.title | downcase %}
      {% assign without_prefix = title_lower | remove_first: "blog-" %}
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
