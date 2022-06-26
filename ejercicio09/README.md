# Ejercicio 9

## Instrucciones

Iniciar el deployment:

`$ kubectl apply -f deployment.yml`

Al listar todos los componentes se puede ver lo siguiente:

```
NAME                           READY   STATUS    RESTARTS       AGE
passwordapi-5dd5f46c96-2lvr4   1/1     Running   0              78m
passwordapi-5dd5f46c96-8qgl4   1/1     Running   0              78m
passwordapi-5dd5f46c96-xgfwg   1/1     Running   0              78m

NAME                          READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/passwordapi   3/3     3            3           78m

NAME                                     DESIRED   CURRENT   READY   AGE
replicaset.apps/passwordapi-5dd5f46c96   3         3         3       78m
```

Acceder a un pod del deployment:

`$ kubectl exec -it deploy/passwordapi -- bash`

Verificar que la aplicación está corriendo:

`$ curl localhost:3000/password`

La respuesta tiene el siguiente formato:

```
{"password":"!240UuNn==>>"}
```

Eliminar todos los componentes:

`$ kubectl delete -f deployment.yml`
