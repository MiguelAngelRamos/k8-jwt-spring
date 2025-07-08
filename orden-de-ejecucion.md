```sh
kubectl apply -f namespace.yaml
```

```sh
kubectl apply -f 01-pv-pvc-postgres.yaml
```

```sh
kubectl apply -f configmap.yaml
```

```sh
kubectl apply -f secret.yaml
```

```sh
kubectl apply -f 02-postgres-deployment.yaml
```

```sh
kubectl apply -f 03-postgres-service.yaml
```

```sh
kubectl apply -f 04-api-deployment.yaml
```

```sh
kubectl apply -f 05-api-service.yaml
```

```sh
kubectl apply -f 06-api-hpa.yaml
```


## todos los comandos juntos

```sh
kubectl apply -f namespace.yaml
kubectl apply -f 01-pv-pvc-postgres.yaml
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
kubectl apply -f 02-postgres-deployment.yaml
kubectl apply -f 03-postgres-service.yaml
kubectl apply -f 04-api-deployment.yaml
kubectl apply -f 05-api-service.yaml
kubectl apply -f 06-api-hpa.yaml
```