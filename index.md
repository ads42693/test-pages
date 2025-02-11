---
layout: default
title: "Bienvenido a la Documentación de Transformación Digital"
---

📚 **Secciones**:  
- [📑 Guías Rápidas]({{ site.baseurl }}/guias/inicio-rapido/)  
- [🚀 Proyectos]({{ site.baseurl }}/docs/proyectos/proyecto-a/)
- [📂 Repositorios]({{ site.baseurl }}/repositorios/)
- [📘 Tutoriales]({{ site.baseurl }}/tutoriales/)
- [📝 Blogs]({{ site.baseurl }}/blogs/)
- [📖 Wiki Colaborativa]({{ site.baseurl }}/wiki/)

---

## 📚 Wikis Integradas

### 📌 Contenido del Repositorio Local

- **📖 Blogs**
  {% assign blogs = site.wiki | where: "wiki_source", "local-wiki" %}
  {% assign blogs = blogs | where: "categories", "blogs" %}
  {% if blogs.size > 0 %}
    <ul>
    {% for page in blogs %}
      <li><a href="{{ page.url | relative_url }}">{{ page.title | replace: '---', '-' | replace: '--', '-' }}</a></li>
    {% endfor %}
    </ul>
  {% else %}
    <p>⚠️ No hay blogs disponibles.</p>
  {% endif %}

- **📑 Artículos**
  {% assign articulos = site.wiki | where: "wiki_source", "local-wiki" %}
  {% assign articulos = articulos | where: "categories", "articulos" %}
  {% if articulos.size > 0 %}
    <ul>
    {% for page in articulos %}
      <li><a href="{{ page.url | relative_url }}">{{ page.title | replace: '---', '-' | replace: '--', '-' }}</a></li>
    {% endfor %}
    </ul>
  {% else %}
    <p>⚠️ No hay artículos disponibles.</p>
  {% endif %}

- **🎓 Tutoriales**
  {% assign tutoriales = site.wiki | where: "wiki_source", "local-wiki" %}
  {% assign tutoriales = tutoriales | where: "categories", "tutoriales" %}
  {% if tutoriales.size > 0 %}
    <ul>
    {% for page in tutoriales %}
      <li><a href="{{ page.url | relative_url }}">{{ page.title | replace: '---', '-' | replace: '--', '-' }}</a></li>
    {% endfor %}
    </ul>
  {% else %}
    <p>⚠️ No hay tutoriales disponibles.</p>
  {% endif %}

---

## 🌍 Wikis Externas

Las siguientes wikis provienen de otros repositorios y se organizan de forma independiente.

{% assign external_wikis = site.wiki | where_exp: "wiki", "wiki.wiki_source != 'local-wiki'" %}
{% assign grouped_external_wikis = external_wikis | group_by: "wiki_source" %}

{% if grouped_external_wikis.size > 0 %}
  {% for wiki_group in grouped_external_wikis %}
  ### 🔹 {{ wiki_group.name }}
  {% if wiki_group.items.size > 0 %}
    <ul>
    {% for page in wiki_group.items %}
      <li><a href="{{ page.url | relative_url }}">{{ page.title | replace: '---', '-' | replace: '--', '-' }}</a></li>
    {% endfor %}
    </ul>
  {% else %}
    <p>⚠️ No hay páginas disponibles en esta wiki.</p>
  {% endif %}
  {% endfor %}
{% else %}
  <p>⚠️ No hay wikis externas disponibles.</p>
{% endif %}

---

## 🔥 Últimos Proyectos

| Proyecto | Descripción | Enlace |
|----------|-------------|--------|
| Proyecto A | Descripción breve del Proyecto A | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-a/) |
| Proyecto B | Descripción breve del Proyecto B | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-b/) |

---

> 📅 Actualizado el: {{ site.time | date: "%d/%m/%Y" }}