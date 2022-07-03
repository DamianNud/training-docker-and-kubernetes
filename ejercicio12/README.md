# Ejercicio 12

## Instrucciones

Iniciar el deployment de Postgres:

`$ kubectl apply -f postgres_deployment.yml`

Verificar que Postgres funciona correctamente:

`$ kubectl exec -it deploy/postgres -- bash`

```
root@postgres-99df78d45-r248j:/# psql -U postgres
psql (10.4 (Debian 10.4-2.pgdg90+1))
Type "help" for help.

postgres=#
```

Iniciar el servicio de Postgres:

`$ kubectl apply -f postgres_service.yml`

Iniciar los configmaps y los secrets:

`$ kubectl apply -f jobvacancyconfig.yml`

`$ kubectl apply -f jobvacancysecret.yml`

Iniciar el deployment de JobVacancy:

`$ kubectl apply -f web_deployment.yml`
