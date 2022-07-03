# Ejercicio 11

## Instrucciones

Iniciar los configmaps y los secrets:

`$ kubectl apply -f configmap1.yml`

`$ kubectl apply -f configmap2.yml`

`$ kubectl apply -f secret1.yml`

Iniciar el deployment:

`$ kubectl apply -f deployment.yml`

Verificar que las variables funcionan correctamente:

`$ kubectl exec -it deploy/pingapp -- bash`

```
appuser@pingapp-9bb95c769-fkj2d:/apps/pingapp$ env | grep LOCATION
CONFIG_LOCATION=/mydata/config.json
SECRETS_LOCATION=/mysecrets/secret.json

appuser@pingapp-9bb95c769-fkj2d:/apps/pingapp$ curl localhost:4567/config
{"key1":"value1"}

appuser@pingapp-9bb95c769-fkj2d:/apps/pingapp$ curl localhost:4567/secrets
{"mypass":"password!"}
```

Verificar usando port-forward:

`$ kubectl port-forward deploy/pingapp 34567:4567`

```
$ curl localhost:34567/config
{"key1":"value1"}

$ curl localhost:34567/secrets
{"mypass":"password!"}
```

Iniciar el servicio:

`$ kubectl apply -f service.yml`

Verificar el funcionamiento del servicio:

`$ kubectl exec -it deploy/pingapp -- bash`

```
appuser@pingapp-9bb95c769-9kjv2:/apps/pingapp$ curl pingapp:8080
{"version":"2.1.0","ping":"2022-07-03T22:25:57+00:00","config_location":"/mydata/config.json","secrets_location":"/mysecrets/secret.json","host":"pingapp-9bb95c769-svgrs"}
```
