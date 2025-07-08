### Activa el addon de Minikube:

```bash
minikube addons enable metrics-server
```

### Verifica que esté corriendo:

Linux
```bash
kubectl get pods -n kube-system | grep metrics-server
```
Windows
```sh
kubectl get pods -n kube-system | Select-String metrics-server
```

Cuando ya esté en `Running`, espera unos 10–20 segundos y prueba:

```bash
kubectl top nodes
kubectl top pods
```

