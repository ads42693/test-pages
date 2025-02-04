# 🌐 Documentación Transformación Digital

Bienvenido al repositorio de documentación para el área de Transformación Digital. Aquí encontrarás guías, tutoriales, blogs y más para ayudarte en tu viaje digital.

## 📁 Estructura del Proyecto

La estructura del proyecto es la siguiente:

```plaintext
nsp-tfd-docs-uti-portal/
├── _config.yml
├── _config_dev.yml
├── Dockerfile
├── Gemfile
├── Gemfile.lock
├── README.md
├── _posts/
│   ├── 2023-01-01-welcome-to-jekyll.markdown
│   └── ...
├── _layouts/
│   ├── default.html
│   └── post.html
└── ...
```

- **_config.yml**: Configuración principal de Jekyll.
- **_config_dev.yml**: Configuración adicional para el entorno de desarrollo.
- **Dockerfile**: Archivo para construir la imagen Docker.
- **Gemfile**: Lista de dependencias Ruby.
- **Gemfile.lock**: Archivo de bloqueo de dependencias.
- **README.md**: Este archivo de documentación.
- **_posts/**: Directorio que contiene las publicaciones del blog.
- **_layouts/**: Plantillas HTML para el sitio.

## 📋 Requisitos Previos

- Docker 🐳
- Ruby y Bundler 💎
- GitHub Pages 📄

## 💻 Desarrollo Local

Para desarrollar y probar el sitio localmente, puedes usar Docker para crear un entorno consistente.

### 🐳 Usando Docker

1. Construir la imagen Docker:

    ```sh
    docker build -t my-jekyll-site .
    ```

2. Ejecutar el contenedor Docker:

    ```sh
    docker run -p 4000:4000 my-jekyll-site
    ```

Esto servirá tu sitio en `http://localhost:4000`.

### 🚀 Sin Docker

1. Instalar las dependencias:

    ```sh
    bundle install
    ```

2. Ejecutar Jekyll:

    ```sh
    bundle exec jekyll serve --config _config.yml,_config_dev.yml
    ```

Esto también servirá tu sitio en `http://localhost:4000`.

## 🚀 Despliegue en GitHub Pages

El despliegue en GitHub Pages se maneja automáticamente mediante GitHub Actions. Los archivos de configuración para los workflows se encuentran en `.github/workflows`.

### ⚙️ Workflows

- **deploy-pages.yml**: Despliega el sitio en GitHub Pages cada vez que hay un push a la rama `develop`.
- **deploy.yml**: Despliega la documentación usando MkDocs.
- **sync-wikis.yml**: Sincroniza las wikis de los proyectos cada lunes a las 8 AM (UTC).

## 🛠️ Buenas Prácticas

1. **Versionar el Dockerfile**: Mantén tu Dockerfile en el control de versiones junto con tu código fuente.
2. **Usar Imágenes Base Estables**: Selecciona imágenes base estables y específicas (por ejemplo, `ruby:3.0`).
3. **Minimizar el Tamaño de la Imagen**: Elimina archivos temporales y cachés después de la instalación de dependencias.
4. **Seguridad**: No incluyas credenciales sensibles en el Dockerfile. Usa variables de entorno y secretos gestionados por el sistema de despliegue.
5. **Documentación**: Mantén este README actualizado con instrucciones claras para el desarrollo y despliegue del proyecto.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Por favor, sigue los siguientes pasos:

1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz commit (`git commit -am 'Agrega nueva funcionalidad'`).
4. Haz push a la rama (`git push origin feature/nueva-funcionalidad`).
5. Abre un Pull Request.

## 📜 Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

## 📞 Contacto

Para cualquier consulta o soporte, por favor contacta a [adrian.arellano@sanna.pe](adrian.arellano@sanna.pe).