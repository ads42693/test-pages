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

📃 Guía Rápida para Administrar el Contenido

Añadir contenido a la documentación es fácil y se hace a través del archivo config/wikis.yml. Sigue estos pasos:

1️⃣ Agregar un nuevo repositorio wiki

Edita config/wikis.yml y añade un nuevo repositorio bajo la clave wikis:

wikis:
  - name: "Mi-Nueva-Wiki"
    url: "https://github.com/mi-org/mi-nueva-wiki.wiki.git"

2️⃣ Ejecutar la acción de GitHub

Cada vez que se actualiza el archivo wikis.yml, el flujo de trabajo en GitHub Actions se encargará de sincronizar la wiki y generar el contenido de manera automática.

3️⃣ Enlaces Dinámicos

Los archivos de las wikis se estructuran de la siguiente manera:

_wikis/
├── <nombre-de-la-wiki>
│   ├── <categoria>-<nombre>.md
│   ├── ...
└── <otra-wiki>
    ├── ...

Por ejemplo, si tienes un archivo llamado tutorial-mi-guia.md, aparecerá en la sección de tutoriales automáticamente.

✨ Importante: Mantén la nomenclatura de los archivos (blog-, articulo-, tutorial-) para que sean categorizados correctamente.

📅 Actualizado el: {{ site.time | date: "%d/%m/%Y" }}