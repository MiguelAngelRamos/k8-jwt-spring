```sh
kubectl apply -f k8s/namespace.yaml
```
```sh
kubectl apply -f k8s/01-pv-pvc-postgres.yaml

```
```sh
kubectl apply -f k8s/configmap.yaml
```
```sh

kubectl apply -f k8s/secret.yaml

```
```sh

kubectl apply -f k8s/02-postgres-deployment.yaml

```
```sh

kubectl apply -f k8s/03-postgres-service.yaml

```
```sh

kubectl apply -f k8s/04-api-deployment.yaml

```
```sh

kubectl apply -f k8s/05-api-service.yaml

``````sh

kubectl apply -f k8s/06-api-hpa.yaml
```


## todos los comandos juntos

```sh
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/01-pv-pvc-postgres.yaml
kubectl apply -f k8s/configmap.yaml
kubectl apply -f k8s/secret.yaml
kubectl apply -f k8s/02-postgres-deployment.yaml
kubectl apply -f k8s/03-postgres-service.yaml
kubectl apply -f k8s/04-api-deployment.yaml
kubectl apply -f k8s/05-api-service.yaml
kubectl apply -f k8s/06-api-hpa.yaml
```