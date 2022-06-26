# Ejercicio 10

## Instrucciones

Probar el bot desde un contenedor:

`$ docker run -d -it --env TELEGRAM_TOKEN=<A COMPLETAR> nicopaez/telegrambot:0.0.7`

Iniciar el deployment:

`$ kubectl apply -f deployment.yml`

Al listar todos los componentes se puede ver lo siguiente:

```
NAME                               READY   STATUS    RESTARTS       AGE
pod/kubetestbot-5f9b7877b6-npg7h   1/1     Running   0              66s

NAME                          READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/kubetestbot   1/1     1            1           66s

NAME                                     DESIRED   CURRENT   READY   AGE
replicaset.apps/kubetestbot-5f9b7877b6   1         1         1       66s
```

Eliminar todos los componentes:

`$ kubectl delete -f deployment.yml`
