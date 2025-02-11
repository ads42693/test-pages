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

## 📖 Guía Rápida para Administrar el Contenido  

Para administrar la documentación, se utiliza el archivo `config/wikis.yml`. Sigue estos pasos para agregar contenido nuevo.

```yaml
wikis:
  - name: "Mi-Nueva-Wiki"
    url: "https://github.com/mi-org/mi-nueva-wiki.wiki.git"
```

### 1️⃣ Agregar un nuevo repositorio wiki  
Edita `config/wikis.yml` y añade un nuevo repositorio bajo la clave `wikis` como se muestra arriba.

### 2️⃣ Ejecutar la acción de GitHub  
Cada vez que se actualiza el archivo `wikis.yml`, el flujo de trabajo en **GitHub Actions** sincronizará la wiki y generará el contenido de manera automática.

### 3️⃣ Enlaces Dinámicos  
Los archivos de las wikis se estructuran de la siguiente manera:

```plaintext
_wikis/
├── <nombre-de-la-wiki>/
│   ├── <categoria>-<nombre>.md
│   ├── ...
└── <otra-wiki>/
    ├── ...
```

📌 **Ejemplo:**  
Si tienes un archivo llamado `tutorial-mi-guia.md`, aparecerá automáticamente en la sección de **Tutoriales**.

---

💡 **Importante:**  
```plaintext
Para que los archivos sean categorizados correctamente, deben seguir la nomenclatura:
- blog-<nombre>.md → Sección de Blogs  
- articulo-<nombre>.md → Sección de Artículos  
- tutorial-<nombre>.md → Sección de Tutoriales  
```

---

📅 **Actualizado el:** {{ site.time | date: "%d/%m/%Y" }}
