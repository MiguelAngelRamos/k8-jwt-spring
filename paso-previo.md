### Activa el addon de Minikube:

```bash
minikube addons enable metrics-server
```

### Verifica que esté corriendo:

```bash
kubectl get pods -n kube-system | grep metrics-server
```

Cuando ya esté en `Running`, espera unos 10–20 segundos y prueba:

```bash
kubectl top nodes
kubectl top pods
```

