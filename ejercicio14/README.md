# Ejercicio 14

## Instrucciones

Iniciar los deployments:

`$ kubectl apply -f passwordapi_deployment.yml`

`$ kubectl apply -f pingapp_deployment.yml`

Iniciar el servicio:

`$ kubectl apply -f service.yml`

Verificar que el servicio fue iniciado:

`$ kubectl get ingress`

```
NAME      CLASS   HOSTS             ADDRESS        PORTS   AGE
service   nginx   tallerk8s.local   192.168.49.2   80      2m35s
```
