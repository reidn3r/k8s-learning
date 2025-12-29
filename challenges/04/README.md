# **Nível 4 - Networking**

12. Crie 2 deployments: frontend (nginx) e backend (httpd)
13. Configure um Service tipo ClusterIP para o backend
14. Faça o frontend acessar o backend via DNS interno (nome-do-service.namespace.svc.cluster.local)
15. Configure um Service para expor o frontend externamente


### **1. Deployments definidos em**

* **Frontend:** NGINX → [`./services/nginx-service.yml`](./services/nginx-service.yml)
* **Backend:** Servidor HTTP Apache → [`./services/backend-service.yml`](./services/backend-service.yml)

---

### **2. Foram definidos 2 services**

### - **Service para expor o NGINX:**

* type: NodePort
* Necessário configurar o NGINX via arquivo [`nginx.conf`](./config/nginx.conf)

  * Requests em `/backend` serão redirecionadas ao servidor Apache
  * O domínio do backend:

    * `http://nome-service.default.svc.cluster.local`
    * Portanto: `http://httpd-service.default.svc.cluster.local`
* Arquivo localizado em [`./config/nginx.conf`](./config/nginx.conf)
* Para criar ConfigMap baseado no nginx.conf:

  * `kubectl create configmap nome-configmap --from-file=nginx.conf`
  * Referenciar o ConfigMap no deployment

### - **Service para expor o backend:**

* type: ClusterIP
* Expõe pod internamente, apenas

---

### **3. Acessar o backend via front**

* `http://ip_node:node_port/backend`

