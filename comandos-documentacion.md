## Comandos

## Información del Cluster

```sh
kubectl get all 
```

## Para eliminar un deployment

```sh
kubectl delete deployment <nombre-deployment>
```

```sh
kubectl delete deployment postgres
```

## Para eliminar un servicio

```sh
kubectl delete service <nombre-servicio>
```
```sh
kubectl delete service postgres-service
```
## Para los logs de un pod 

```sh
kubectl logs -f <nombre-del-pod>
```
Ejemplo: 
```sh
kubectl logs -f springboot-api-855bfb9985-wxhdt
```