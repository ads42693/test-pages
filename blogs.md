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
      <th>📌 Descripción</th>
      <th>🔗 Enlace</th>
    </tr>
  </thead>
  <tbody>
    {% assign blogs = site.wiki | where_exp: "page", "page.wiki_source == 'local-wiki' and page.categories contains 'blogs'" %}
    {% for page in blogs %}
      <tr>
        <td>{{ page.title | remove_first: "Blog-" | remove_first: "Articulo-" | remove_first: "Tutorial-" }}</td>
        <td>Blog relacionado con nuestras herramientas</td>
        <td><a class="btn btn-primary" href="{{ page.url | relative_url }}">Ver más</a></td>
      </tr>
    {% endfor %}
  </tbody>
</table>

