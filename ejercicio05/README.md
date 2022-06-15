**Respuestas:**

- **HEALTHCHECK:** Esta instrucción le dice a Docker como testear un contenedor para verificar que todavía se encuentra en funcionamiento. Puede detectar casos como el de un servidor web atascado en un _loop_ infinito sin poder manejar nuevas conexiones, aunque el proceso del servidor siga corriendo.

  Cuenta con dos formatos:

  - `HEALTHCHECK [OPCIONES] CMD <COMANDO>`

    Verifica el contenedor ejecutando el comando dentro del contenedor.
  - `HEALTHCHECK NONE`

    Deshabilita cualquier verificación heredada de la imagen base.

  Solo puede haber un `HEALTHCHECK` por contenedor. En caso de haber más de una, solo la última tendrá efecto.

- **ONBUILD:** Esta instrucción agrega una instrucción _trigger_ a la imagen para que se ejecute posteriormente, cuando la imagen es utilizada como imagen base para la generación de otra imagen. La instrucción se ejecutará en el contecto de la generación, como si hubiese sido insertado inmediatamente despues de la instrucción `FROM` del `Dockerfile`.

  Cualquier instrucción puede ser registrada como _trigger_.

  Uso de la instrucción: `ONBUILD <INSTRUCCION>`

- **VOLUME:** Esta instrucción crea un punto de montaje con el nombre especificado y lo marca indicando que mantiene volúmenes montados externamente desde el _host_ nativo u otros contenedores. El valor puede ser un arreglo JSON, `VOLUME ["/var/log/"]`, o un _string_ con múltiples argumentos, como `VOLUME /var/log` o `VOLUME /var/log /var/db`.

  Uso de la instrucción: `VOLUME ["<UBICACION>"]`
