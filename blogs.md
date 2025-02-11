---
layout: default
title: "Blogs"
---

# 📖 Blogs

[⬅ Volver al inicio]({{ site.baseurl }}/)

Explora los blogs disponibles sobre nuestras herramientas y metodologías.

{% assign blogs = site.wiki | where: "wiki_source", "local-wiki" %}
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
      {% if page.categories contains "blogs" %}
        {% assign clean_name = page.title | replace: "Blog-", "" | replace: "Articulo-", "" | replace: "Tutorial-", "" %}
        <tr>
          <td>{{ clean_name }}</td>
          <td>Blog relacionado con nuestras herramientas</td>
          <td><a class="btn btn-primary text-dark" href="{{ page.url | relative_url }}">Ver más</a></td>
        </tr>
      {% endif %}
    {% endfor %}
  </tbody>
</table>

