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
    {% for page in site.wiki | where: "wiki_source", "local-wiki" | where: "categories", "blogs" %}
      <tr>
        <td>{{ page.title | remove_first: "Blog-" | remove_first: "Articulo-" | remove_first: "Tutorial-" }}</td>
        <td>Blog relacionado con nuestras herramientas</td>
        <td><a class="btn btn-primary" href="{{ page.url | relative_url }}">Ver más</a></td>
      </tr>
    {% endfor %}
  </tbody>
</table>
