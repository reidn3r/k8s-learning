# Desafios K8s - Aprendizado

Este repositório registra meu aprendizado em Kubernetes, seguindo uma trilha prática.
Cada nível contém um conjunto de desafios, resolvidos com manifests YAML organizados em diretórios separados.
O objetivo é construir domínio sobre Deployments, Services, ConfigMaps, Volumes, Networking, Health Checks, Jobs, RBAC e outros conceitos.

---

# Estrutura do Repositório

```
.
├── base/                Arquivos fundamentais: deployments, pods, replicasets, services
└── challenges/
    ├── 01/              Nível 1 — Fundamentos
    ├── 02/              Nível 2 — ConfigMaps & Secrets
    ├── 03/              Nível 3 — Volumes
    └── 04/              Nível 4 — Networking
    └── ...
```

---

# Progresso dos Desafios

| Nível | Título               | Status           | Diretório                            |
| ----- | -------------------- | ---------------- | ------------------------------------ |
| 1     | Fundamentos          | **Concluído**    | [`./challenges/01`](./challenges/01) |
| 2     | ConfigMaps e Secrets | **Concluído**    | [`./challenges/02`](./challenges/02) |
| 3     | Volumes              | **Concluído**    | [`./challenges/03`](./challenges/03) |
| 4     | Networking           | **Concluído**    | [`./challenges/04`](./challenges/04) |
| 5     | Health Checks        | **Não iniciado** | —                                    |
| 6     | Jobs e CronJobs      | **Não iniciado** | —                                    |
| 7     | Resources e Limits   | **Não iniciado** | —                                    |
| 8     | Namespaces e RBAC    | **Não iniciado** | —                                    |
| 9     | Real World           | **Não iniciado** | —                                    |
| Final | Projeto Completo     | **Não iniciado** | —                                    |


# Resumo dos Níveis

## Nível 1 — Fundamentos

Status: Concluído

Diretório: [`./challenges/01`](./challenges/01)

Resumo: Deployment com réplicas, NodePort, escala e update da imagem.


## Nível 2 — ConfigMaps e Secrets

Status: Concluído

Diretório: [`./challenges/02`](./challenges/02)

Resumo: ConfigMap, Secret e variáveis de ambiente montadas em pod.


## Nível 3 — Volumes

Status: Concluído

Diretório: [`./challenges/03`](./challenges/03)

Resumo: PVC persistente, recriação de pod verificando dados.


## Nível 4 — Networking


Status: Concluído

Diretório: [`./challenges/04`](./challenges/04)

Resumo: 2 Deployments, NodePort, ClusterIP, DNS interno, comunicação entre frontend e backend.


## Nível 5 — Health Checks

Status: Concluído

Diretório: [`./challenges/05`](./challenges/05)

Resumo: livenessProbe e readinessProbe para verificação de saúde do app em Pod e startupProbe para proteger apps que demorar para iniciar 


## Nível 6 — Jobs e CronJobs

Status: Concluído

Diretório: [`./challenges/06`](./challenges/06)

Resumo: Jobs e CronJobs são usados para execução de tarefas pontuais. Jobs executam uma única vez, CronJobs executam em períodos. Cada Job a ser executado cria um novo Pod, executa e termina o Pod


## Nível 7 — Resources e Limits

Status: Não iniciado


## Nível 8 — Namespaces e RBAC

Status: Não iniciado


## Nível 9 — Real World

Status: Não iniciado


## Desafio Final — Projeto Completo

Status: Não iniciado


