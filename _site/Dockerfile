# Define argumentos para versiones con valores por defecto
ARG RUBY_VERSION=3.0
ARG BUNDLER_VERSION=2.3.5

# Usa la imagen de Ruby basada en el argumento RUBY_VERSION
FROM ruby:${RUBY_VERSION}

# Instala dependencias del sistema
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

# Configura las variables de entorno para Bundler
ENV BUNDLE_PATH=/usr/local/bundle \
    BUNDLE_BIN=/usr/local/bundle/bin \
    PATH=/usr/local/bundle/bin:$PATH

# Establece el directorio de trabajo
WORKDIR /usr/src/app

# Copia el Gemfile y Gemfile.lock para aprovechar la caché de Docker
COPY Gemfile Gemfile.lock ./

# Actualiza Bundler a la versión especificada (usando -v)
RUN gem install bundler -v "${BUNDLER_VERSION}"

# Instala las gemas (se usa --jobs y --retry para robustecer la instalación)
RUN bundle install --jobs=4 --retry 3

# Copia el resto del código de la aplicación
COPY . .

# Expone el puerto en el que Jekyll servirá el sitio
EXPOSE 4000

# Comando para iniciar Jekyll
CMD ["bundle", "exec", "jekyll", "serve", "--host", "0.0.0.0", "--config", "_config.yml,_config_dev.yml"]
