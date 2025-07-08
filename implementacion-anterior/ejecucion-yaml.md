```sh
kubectl apply -f 01-pv-pvc-postgres.yaml
kubectl apply -f 02-postgres-deployment.yaml
kubectl apply -f 03-postgres-service.yaml

kubectl apply -f 04-api-deployment.yaml
kubectl apply -f 05-api-service.yaml
kubectl apply -f 06-api-hpa.yaml

```

## Generar un forward
```sh
kubectl port-forward service/api-service 8080:80
```