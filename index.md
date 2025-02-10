---
layout: default
title: "Inicio"
---

# Bienvenido a la Documentación de Transformación Digital

📚 **Secciones**:  
- [Guías Rápidas]({{ site.baseurl }}/guias/inicio-rapido/)  
- [Proyectos]({{ site.baseurl }}/docs/proyectos/proyecto-a/)
- [Repositorios]({{ site.baseurl }}/repositorios/)
- [Tutoriales]({{ site.baseurl }}/tutoriales/)
- [Blogs]({{ site.baseurl }}/blogs/)
- [Wiki Colaborativa]({{ site.baseurl }}/wiki/)  <!-- Nuevo enlace -->

---

## 📚 Wikis Integradas

### Wiki Principal
{% assign main_pages = site.wikis | where: "wiki_source", "main" %}
{% for page in main_pages %}
- [{{ page.title }}]({{ page.url }})
{% endfor %}

### Skills Wiki
{% assign skills_pages = site.wikis | where: "wiki_source", "skills-wiki" %}
{% for page in skills_pages %}
- [{{ page.title }}]({{ page.url }})
{% endfor %}

---

## Últimos Proyectos

| Proyecto | Descripción | Enlace |
|----------|-------------|--------|
| Proyecto A | Descripción breve del Proyecto A | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-a/) |
| Proyecto B | Descripción breve del Proyecto B | [Ver más]({{ site.baseurl }}/docs/proyectos/proyecto-b/) |

---

> Actualizado el: {{ site.time | date: "%d/%m/%Y" }}