# Documentación: Uso de Namespace, ConfigMap y Secret en Kubernetes

## ¿Qué es un Namespace?
Un **Namespace** en Kubernetes es un recurso que permite aislar y organizar los recursos dentro de un clúster. Es como una "carpeta" donde agrupas tus servicios, deployments, configmaps, etc. 

**¿Para qué sirve?**
- Separar ambientes (dev, test, prod), equipos o proyectos dentro del mismo clúster.
- Evitar conflictos de nombres y mejorar la administración.

**Ejemplo:**
```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: apirest-ns
```

---

## ¿Qué es un ConfigMap?
Un **ConfigMap** es un recurso de Kubernetes que permite almacenar datos de configuración no sensibles (por ejemplo, URLs, nombres de app, parámetros de entorno) en forma de pares clave-valor.

**¿Para qué sirve?**
- Separar la configuración del código de la aplicación.
- Cambiar la configuración sin tener que reconstruir la imagen Docker.

**Ejemplo:**
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: apirest-config
  namespace: apirest-ns
data:
  SPRING_DATASOURCE_URL: jdbc:postgresql://postgres-service:5432/newapirestfull
  SPRING_PROFILES_ACTIVE: prod
  APP_NAME: api-rest-jwt-spring
```

---

## ¿Qué es un Secret?
Un **Secret** es un recurso de Kubernetes para almacenar información sensible (contraseñas, claves, tokens) de forma codificada en base64.

**¿Para qué sirve?**
- Mantener seguras las credenciales y datos privados, evitando que estén en el código o en archivos visibles.

**Ejemplo:**
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: apirest-secret
  namespace: apirest-ns
type: Opaque
data:
  SPRING_DATASOURCE_USERNAME: cG9zdGdyZXM=  # postgres (base64)
  SPRING_DATASOURCE_PASSWORD: cGFzc3dvcmQ=  # password (base64)
  JWT_SECRET: c2VjcmV0S2V5  # secretKey (base64)
```

---

## ¿Cómo se usan en la aplicación?

En el archivo de deployment de la API, se referencian así:
```yaml
      envFrom:
        - configMapRef:
            name: apirest-config
        - secretRef:
            name: apirest-secret
```
Esto hace que todas las variables definidas en el ConfigMap y Secret estén disponibles como variables de entorno dentro del contenedor, y la aplicación Spring Boot las puede usar automáticamente.

---

## Resumen visual
1. **Namespace:** Agrupa todos los recursos de tu app.
2. **ConfigMap:** Guarda configuración no sensible.
3. **Secret:** Guarda datos sensibles.
4. **Deployment:** Usa ambos para inyectar variables de entorno a los contenedores.

---

> **Recomendación:** Nunca guardes información sensible en un ConfigMap. Usa siempre Secret para contraseñas, claves y tokens.
