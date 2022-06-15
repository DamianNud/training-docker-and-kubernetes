**Respuestas:**

- Tanto desde el archivo `docker-compose-jobvacancy.yml` como con el comando `docker ps` se puede ver que se están ejecutando dos contenedores.

- Los contenedores están basados en las siguientes imágenes:

  - **nicopaez/jobvacancy-ruby:1.3.0**
  - **postgres**


- Explicación del archivo:

  - `version` indica el número de versión de la especificación.
  - `services` indica la lista de servicios a iniciar.
  - `web` es el nombre del primer servicio.
  - `image` indica el nombre de la imagen a utilizar.
  - `links` indica con que otros servicios está enlazado el servicio.
  - `ports` mapea los puertos indicados en el contenedor.
  - `environment` define las variables de entorno del contenedor.
  - `depends_on` indica que el servicio se debe iniciar luego de haber iniciado los servicios especificados.
  - `db` es nombre del segundo servicio.


- Los contenedores se pueden ver entre si porque se definió un enlace de red entre los servicios por medio de la definición de `link` desde el servicio `web` a `db`.
