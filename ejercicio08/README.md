# Ejercicio 8

## Instrucciones

Iniciar los contenedores:

`$ docker-compose up`

Accediendo a _localhost:8080/health_ se puede ver el cambio desde el navegador:

```
{"host":"6c247d4634a3","loadavg":[0.63720703125,0.4423828125,0.318359375],"freemem":7905550336,"appversion":"1.0.0"}
{"host":"46b932d4ec68","loadavg":[0.14794921875,0.29736328125,0.2734375],"freemem":7907905536,"appversion":"1.0.0"}
```

También es posible agregar un argumento para aumentar la cantidad de replicas:

`$ docker-compose up --scale passwordapi=2`
