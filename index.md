---
layout: default
title: "Bienvenido a la Documentación de Transformación Digital"
---

## 📚 Secciones

### 📌 Contenido del Repositorio Local

- **📖 Blogs**  
  📂 [Explora todos los blogs aquí]({{ site.baseurl }}/blogs/)

- **📑 Artículos**  
  📂 [Explora todos los artículos aquí]({{ site.baseurl }}/articulos/)

- **🎓 Tutoriales**  
  📂 [Explora todos los tutoriales aquí]({{ site.baseurl }}/tutoriales/)

---

## 🌍 Wikis Externas

Las siguientes wikis provienen de otros repositorios y se organizan de forma independiente.

{% assign external_wikis = site.wiki | where_exp: "wiki", "wiki.wiki_source != 'local-wiki'" %}
{% assign grouped_external_wikis = external_wikis | group_by: "wiki_source" %}

{% for wiki_group in grouped_external_wikis %}
### 🔹 {{ wiki_group.name }}
<ul>
  {% for page in wiki_group.items %}
  <li><a href="{{ page.url | relative_url }}">{{ page.title }}</a></li>
  {% endfor %}
</ul>
{% endfor %}

---

## 🔥 Últimos Proyectos (Repositorios Externos)

A continuación, se listan los repositorios externos disponibles.

<table>
  <thead>
    <tr>
      <th>📂 Nombre</th>
      <th>🔗 Enlace</th>
    </tr>
  </thead>
  <tbody>
    {% assign repos = site.wiki | where_exp: "wiki", "wiki.wiki_source != 'local-wiki'" %}
    {% for repo in repos %}
      {% assign clean_name = repo.title | remove_first: "skills-" | strip | capitalize %}
      {% assign repo_url = repo.url | replace: ".wiki.git", "" %}  <!-- 🔹 Transformamos la URL -->
      <tr>
        <td>{{ clean_name }}</td>
        <td>
          <a class="btn btn-primary text-dark" 
             href="{{ repo_url }}" 
             target="_blank"
             style="color: #007bff; text-decoration: underline;">
            Ver en GitHub
          </a>
        </td>
      </tr>
    {% endfor %}
  </tbody>
</table>

---

> 📅 Actualizado el: {{ site.time | date: "%d/%m/%Y" }}
