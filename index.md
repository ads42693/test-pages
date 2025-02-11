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

## 🔥 Últimos Proyectos

| Proyecto | Descripción | Enlace |
|----------|-------------|--------|
| Proyecto A | Descripción breve del Proyecto A | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-a/) |
| Proyecto B | Descripción breve del Proyecto B | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-b/) |

---

> 📅 Actualizado el: {{ site.time | date: "%d/%m/%Y" }}