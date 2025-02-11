# 🌐 Documentación de Transformación Digital

Bienvenido al repositorio de documentación para el área de **Transformación Digital**. Aquí encontrarás **blogs, artículos, tutoriales y documentación técnica** organizada de manera eficiente.

---

## 📁 **Estructura del Proyecto**

El proyecto está estructurado de la siguiente manera:

```
.
├── Dockerfile
├── Gemfile
├── Gemfile.lock
├── README.md
├── _config.yml
├── _config_dev.yml
├── articulos.md
├── blogs.md
├── config
│   └── wikis.yml
├── docker-compose.yml
├── index.md
└── tutoriales.md
```

- **`config/wikis.yml`**: Archivo donde se configuran las wikis externas.
- **`index.md`**: Página principal con enlaces a todas las secciones.
- **`articulos.md`**, **`blogs.md`**, **`tutoriales.md`**: Secciones dinámicas generadas con Jekyll.
- **`Dockerfile`**, **`docker-compose.yml`**: Configuración para ejecución en contenedores.
- **`Gemfile`**, **`_config.yml`**: Dependencias y configuración de Jekyll.

---

## 🔄 **Wikis Dinámicas**

Las wikis externas se gestionan automáticamente a través del archivo **`config/wikis.yml`**, permitiendo sincronizar documentación desde otros repositorios.

**Ejemplo de configuración en `config/wikis.yml`:**
```yaml
wikis:
  - name: "Mi-Nueva-Wiki"
    url: "https://github.com/mi-org/mi-nueva-wiki.wiki.git"

  - name: "Otra-Wiki"
    url: "https://github.com/mi-org/otra-wiki.wiki.git"
```

Cuando se edita este archivo y se sube un cambio a la rama `develop`, el workflow de GitHub Actions ejecuta un proceso automático que **clona, categoriza y enlaza** las wikis dinámicamente.

**Estructura generada en `_wikis/` en tiempo de ejecución:**
```
_wikis/
├── <nombre-de-la-wiki>
│   ├── blog-nombre.md
│   ├── articulo-nombre.md
│   ├── tutorial-nombre.md
│   ├── ...
└── <otra-wiki>
    ├── ...
```
✨ **Importante**: Para que los archivos sean correctamente categorizados, deben tener un prefijo como `blog-`, `articulo-`, `tutorial-`.

---

## 🚀 **Cómo Ejecutar el Proyecto Localmente**

Puedes correr el sitio de documentación de dos formas:

### 🐳 **Usando Docker**
1. Construir la imagen:
   ```sh
   docker build -t jekyll-docs .
   ```
2. Ejecutar el contenedor:
   ```sh
   docker run -p 4000:4000 jekyll-docs
   ```
   Esto servirá el sitio en `http://localhost:4000`.

### ⚡ **Ejecutar Jekyll sin Docker**
1. Instalar dependencias:
   ```sh
   bundle install
   ```
2. Iniciar el servidor Jekyll:
   ```sh
   bundle exec jekyll serve --config _config.yml,_config_dev.yml
   ```
   También se servirá en `http://localhost:4000`.

---

## 🔄 **Automatización con GitHub Actions**
El despliegue del sitio está automatizado con **GitHub Actions**. Cada cambio en la rama `develop` genera una actualización en **GitHub Pages**.

### ⚙️ **Workflows principales**
- **`deploy.yml`**: Genera y despliega la documentación.
- **`sync-wikis.yml`**: Sincroniza las wikis cada vez que se edita `config/wikis.yml`.
- **`build.yml`**: Compila y prueba el sitio en cada push.

---

## 🤝 **Contribuciones**
¡Las contribuciones son bienvenidas! Sigue estos pasos:

1. **Haz un fork** del repositorio.
2. **Crea una rama** (`git checkout -b feature/nueva-funcionalidad`).
3. **Realiza cambios** y haz commit (`git commit -am "Nueva funcionalidad"`).
4. **Haz push** a la rama (`git push origin feature/nueva-funcionalidad`).
5. **Abre un Pull Request** 🚀.

---

## 📜 **Licencia**
Este proyecto está licenciado bajo la **Licencia MIT**.

📅 **Última actualización:** {{ site.time | date: "%d/%m/%Y" }}
