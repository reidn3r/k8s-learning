# **Nível 2 — ConfigMaps e Secrets**
* **6. Criar um ConfigMap com variáveis (DB_HOST, DB_PORT)**
* **7. Criar um Secret com senha de banco (DB_PASSWORD)**
* **8. Montar ambos em um Pod e verificar as variáveis dentro do container**

### **1. Apply ConfigMap**

### ✔ Criar o ConfigMap

```bash
k apply -f ./env/configmap.yml
```

### ✔ Criar o Secret a partir de um arquivo `.env`

```bash
k create secret generic nome-da-secret \
  --from-env-file=./foo/bar/dir/.env.example
```

### ✔ Listar Secrets

```bash
k get secret
```

### ✔ Ver o conteúdo do Secret (YAML)

```bash
k get secret nome-da-secret -o yaml
```

Exemplo de resultado:

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: pgsql-secret
  namespace: default
data:
  PASSWORD: Y29yaW50aGlhbnM=
  PORT: NjM3OQ==
type: Opaque
```

---

### **2. Apply Secrets**

```bash
k apply -f ./env/secret.yml
```


### **3. Apply Deployment**

```bash
k apply -f pgsql-deployment.yml
```

---
### **4. Verificar ConfigMap**

```bash
k describe configmap pgsql-config
```

* Resultado
```
Name:         pgsql-config
Namespace:    default
Labels:       <none>
Annotations:  <none>

Data
====
POSTGRES_DB:
----
pgsql_k8s

POSTGRES_PASSWORD:
----
corinthians

POSTGRES_USER:
----
pgsql


BinaryData
====
```