Instrucciones:

Ejecutar el siguiente comando para hacer funcionar el servidor NGINX con Docker usando la página personalizada:

$ docker run -it -d -p 8080:80 -v <UBICACION_DEL_DIRECTORIO>:/usr/share/nginx/html nginx

Nota: La ubicación debe ser la del directorio donde se encuentra el archivo index.html.

Acceder desde el navegador a: localhost:8080

Significado de los parámetros:

- i: modo interactivo
- t: modo terminal
- d: modo detached
- p: mapeo de puertos
- v: montado de volumen
