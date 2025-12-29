## Desafios Kubernetes: Aprendizado 

**Nível 1 - Fundamentos**
1. Crie um deployment do nginx com 3 réplicas
2. Exponha esse deployment com um Service tipo NodePort
3. Acesse o nginx pelo navegador
4. Escale para 5 réplicas sem recriar o deployment
5. Faça update da imagem para nginx:alpine

**Nível 2 - ConfigMaps e Secrets**

6. Crie um ConfigMap com variáveis de ambiente (DB_HOST, DB_PORT)
7. Crie um Secret com senha de banco (DB_PASSWORD)
8. Monte ambos em um pod e verifique as variáveis dentro do container

**Nível 3 - Volumes**

9. Crie um pod com volume persistente (PVC) de 1GB
10. Escreva um arquivo dentro do pod no volume
11. Delete o pod e crie outro montando o mesmo PVC - o arquivo deve estar lá

**Nível 4 - Networking**

12. Crie 2 deployments: frontend (nginx) e backend (httpd)
13. Configure um Service tipo ClusterIP para o backend
14. Faça o frontend acessar o backend via DNS interno (nome-do-service.namespace.svc.cluster.local)
15. Configure um Ingress para expor o frontend externamente

**Nível 5 - Health Checks**

16. Crie um deployment com livenessProbe e readinessProbe
17. Faça o pod "falhar" propositalmente e observe o K8s reiniciá-lo
18. Configure startupProbe para apps que demoram a iniciar

**Nível 6 - Jobs e CronJobs**

19. Crie um Job que executa um script e termina
20. Crie um CronJob que roda a cada 2 minutos

**Nível 7 - Resources e Limits**

21. Configure requests e limits de CPU/memória em um pod
22. Crie um pod que exceda o limite de memória e veja o OOMKilled

**Nível 8 - Namespaces e RBAC**

23. Crie 2 namespaces: dev e prod
24. Implante a mesma app nos dois com configurações diferentes
25. Crie um ServiceAccount com permissões limitadas

**Nível 9 - Real World**

26. Deploy completo: PostgreSQL (StatefulSet) + Backend API + Frontend
27. Configure horizontal pod autoscaler (HPA) baseado em CPU
28. Simule falha de um node e veja o K8s realocar os pods

**Desafio Final - Projeto Completo**

29. Crie uma aplicação com:
   - 3-tier (frontend, backend, database)
   - ConfigMaps e Secrets
   - Volumes persistentes
   - Health checks
   - Resource limits
   - Ingress configurado
   - Tudo em manifests YAML versionados
