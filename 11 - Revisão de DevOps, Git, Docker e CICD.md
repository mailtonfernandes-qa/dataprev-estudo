# Revisão Completa de DevOps, Git, Docker e CI/CD — Concurso Dataprev (Desenvolvimento de Software)

Material de estudo focado em: DevOps, Git, GitFlow, Docker, Kubernetes, CI/CD e Infrastructure as Code (IaC).

## Sumário

- Fundamentos de DevOps
- Versionamento com Git
- GitFlow e Estratégias de Branch
- Docker
- Containers
- Kubernetes
- CI/CD
- Pipelines de Entrega
- Infrastructure as Code (IaC)
- Monitoramento e Observabilidade
- Segurança DevSecOps
- Ferramentas do Ecossistema
- Exercícios de Fixação
- Referências

---

# 1. Fundamentos de DevOps

## O que é DevOps?

DevOps é uma cultura que integra Desenvolvimento (Dev) e Operações (Ops), visando entrega contínua, automação e colaboração.

### Benefícios

- Entregas mais rápidas
- Redução de erros
- Automação de processos
- Melhor qualidade de software
- Maior confiabilidade operacional

### Princípios

- Colaboração
- Automação
- Feedback contínuo
- Melhoria contínua
- Monitoramento

---

# 2. Versionamento com Git

## Conceitos Fundamentais

- Repository
- Commit
- Branch
- Merge
- Tag
- Remote

## Comandos Principais

```bash
git clone
git status
git add .
git commit -m "mensagem"
git push
git pull
git fetch
git merge
```

## Estados dos Arquivos

- Untracked
- Modified
- Staged
- Committed

---

# 3. GitFlow e Estratégias de Branch

## Branches Principais

### Main
Produção.

### Develop
Integração contínua.

### Feature
Novas funcionalidades.

### Release
Preparação para produção.

### Hotfix
Correções urgentes.

Fluxo:

Feature → Develop → Release → Main

---

# 4. Docker

## O que é Docker?

Plataforma para criação e execução de containers.

## Conceitos

- Image
- Container
- Dockerfile
- Volume
- Network
- Registry

## Dockerfile

```dockerfile
FROM eclipse-temurin:21
COPY app.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]
```

## Comandos Principais

```bash
docker build
docker run
docker ps
docker logs
docker stop
docker rm
docker images
```

---

# 5. Containers

## Características

- Isolamento
- Portabilidade
- Leveza
- Escalabilidade

## VM x Container

### Máquina Virtual

- Sistema operacional completo
- Mais consumo de recursos

### Container

- Compartilha kernel
- Inicialização rápida
- Menor consumo

---

# 6. Kubernetes

## O que é Kubernetes?

Plataforma de orquestração de containers.

## Componentes Principais

### Pod
Menor unidade executável.

### Deployment
Gerencia réplicas e atualizações.

### Service
Exposição de aplicações.

### ConfigMap
Configurações.

### Secret
Informações sensíveis.

## Benefícios

- Alta disponibilidade
- Auto Healing
- Escalabilidade automática
- Balanceamento de carga

---

# 7. CI/CD

## Continuous Integration (CI)

Integra alterações frequentemente ao repositório principal.

Etapas comuns:

- Build
- Testes unitários
- Análise estática
- Empacotamento

## Continuous Delivery (CD)

Artefatos ficam prontos para implantação.

## Continuous Deployment

Implantação automática em produção.

---

# 8. Pipelines de Entrega

## Pipeline Típico

1. Commit
2. Build
3. Testes
4. Quality Gate
5. Empacotamento
6. Deploy Homologação
7. Aprovação
8. Deploy Produção

## Benefícios

- Padronização
- Rastreabilidade
- Automação
- Qualidade

---

# 9. Infrastructure as Code (IaC)

## Conceito

Gerenciamento da infraestrutura através de código.

## Benefícios

- Reprodutibilidade
- Versionamento
- Automação
- Auditoria

## Ferramentas

### Terraform

Provisionamento de infraestrutura.

### Ansible

Automação de configuração.

### CloudFormation

Infraestrutura AWS.

---

# 10. Monitoramento e Observabilidade

## Monitoramento

Acompanha métricas do sistema.

## Observabilidade

Permite compreender comportamento interno.

### Pilares

- Métricas
- Logs
- Traces

### Ferramentas

- Prometheus
- Grafana
- ELK Stack
- Jaeger

---

# 11. Segurança DevSecOps

## Conceito

Integra segurança ao ciclo DevOps.

## Práticas

- SAST
- DAST
- Scan de dependências
- Scan de containers
- Gestão de segredos

## Benefícios

- Redução de vulnerabilidades
- Correção antecipada
- Compliance

---

# 12. Ferramentas do Ecossistema

## Controle de Versão

- Git
- GitHub
- GitLab
- Azure Repos

## CI/CD

- GitHub Actions
- GitLab CI
- Azure DevOps
- Jenkins

## Containers

- Docker
- Podman

## Orquestração

- Kubernetes
- OpenShift

## Monitoramento

- Prometheus
- Grafana

---

# 13. Exercícios de Fixação

1. O que é DevOps?
2. Diferencie CI, Continuous Delivery e Continuous Deployment.
3. Qual a função do Git?
4. O que é um commit?
5. Diferencie imagem e container.
6. Qual função do Kubernetes?
7. O que é Infrastructure as Code?
8. Cite ferramentas de IaC.
9. O que é GitFlow?
10. Explique observabilidade.

---

# 14. Referências

- Git Documentation
- Docker Documentation
- Kubernetes Documentation
- Terraform Documentation
- Azure DevOps Documentation
- GitHub Actions Documentation
- The DevOps Handbook
- Continuous Delivery (Jez Humble)

## Dicas para Prova

✅ DevOps

✅ Git e GitFlow

✅ Docker

✅ Containers

✅ Kubernetes

✅ CI/CD

✅ Pipelines

✅ Infrastructure as Code

✅ Terraform

✅ Observabilidade

✅ DevSecOps
