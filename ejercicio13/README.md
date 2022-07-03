# Ejercicio 13

## Instrucciones

Iniciar el deployment:

`$ kubectl apply -f deployment.yml`

Verificar que el pod está corriendo:


`$ kubectl get pods`

```
NAME                           READY   STATUS    RESTARTS   AGE
passwordapi-67775998f6-h6dcf   1/1     Running   0          3m6s
```

`$ kubectl describe pod/passwordapi-67775998f6-h6dcf`

```
Events:
  Type    Reason     Age    From               Message
  ----    ------     ----   ----               -------
  Normal  Scheduled  4m34s  default-scheduler  Successfully assigned default/passwordapi-67775998f6-h6dcf to minikube
  Normal  Pulled     4m34s  kubelet            Container image "nicopaez/password-api:1.5.0-java" already present on machine
  Normal  Created    4m34s  kubelet            Created container passwordapi
  Normal  Started    4m34s  kubelet            Started container passwordapi
```

Verificar que el endpoint funciona:

`$ kubectl exec -it deploy/passwordapi -- sh`

```
$ curl localhost:8080/actuator/health
{"status":"UP"}
```
