---
layout: default
title: "Blogs"
---

# 📖 Blogs

[⬅ Volver al inicio]({{ site.baseurl }}/)

Explora los blogs disponibles sobre nuestras herramientas y metodologías.

{% assign blogs = site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "blogs" %}

<table>
  <thead>
    <tr>
      <th>📄 Nombre</th>
      <th>📌 Descripción</th>
      <th>🔗 Enlace</th>
    </tr>
  </thead>
  <tbody>
    {% for page in blogs %}
      {% assign clean_name = page.title | downcase | regex_replace: "^(blog|articulo|tutorial)-", "" | strip | capitalize %}
      <tr>
        <td>{{ clean_name }}</td>
        <td>Blog relacionado con nuestras herramientas</td>
        <td><a class="btn btn-primary text-dark" href="{{ page.url | relative_url }}" style="color: #007bff; text-decoration: underline;">Ver más</a></td>
      </tr>
    {% endfor %}
  </tbody>
</table>
