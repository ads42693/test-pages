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
  {% for page in site.blogs %}
    - [{{ page.title }}]({{ page.url | relative_url }})
  {% endfor %}

- **📑 Artículos**
  {% for page in site.articulos %}
    - [{{ page.title }}]({{ page.url | relative_url }})
  {% endfor %}

- **🎓 Tutoriales**
  {% for page in site.tutoriales %}
    - [{{ page.title }}]({{ page.url | relative_url }})
  {% endfor %}

---

## 🌍 Wikis Externas

Las siguientes wikis provienen de otros repositorios y se organizan de forma independiente.

{% assign grouped_wikis = site.wiki | group_by: "wiki_source" %}

{% for wiki_group in grouped_wikis %}
### 🔹 {{ wiki_group.name }}
{% for page in wiki_group.items %}
- [{{ page.title }}]({{ page.url | relative_url }})
{% endfor %}
{% endfor %}

---

## 🔥 Últimos Proyectos

| Proyecto | Descripción | Enlace |
|----------|-------------|--------|
| Proyecto A | Descripción breve del Proyecto A | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-a/) |
| Proyecto B | Descripción breve del Proyecto B | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-b/) |

---

> 📅 Actualizado el: {{ site.time | date: "%d/%m/%Y" }}