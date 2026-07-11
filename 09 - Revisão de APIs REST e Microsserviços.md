# Revisão Completa de APIs REST e Microsserviços — Concurso Dataprev (Desenvolvimento de Software)

## Sumário

- APIs REST
- HTTP e Métodos REST
- JSON
- Web Services
- Desenvolvimento de APIs com Spring Boot
- Arquitetura de Microsserviços
- Arquitetura Hexagonal
- Spring Cloud
- API Gateway
- Containers e Docker
- Orquestração de Serviços
- Transações Distribuídas
- Boas Práticas para APIs REST
- Exercícios de Fixação
- Referências

---

## 1. APIs REST

### O que é REST?
REST (Representational State Transfer) é um estilo arquitetural para construção de sistemas distribuídos baseado em recursos acessados via HTTP.

### Restrições REST
- Cliente-Servidor
- Stateless
- Cache
- Interface Uniforme
- Sistema em Camadas

---

## 2. HTTP e Métodos REST

| Método | Operação |
|----------|----------|
| GET | Consulta |
| POST | Criação |
| PUT | Atualização completa |
| PATCH | Atualização parcial |
| DELETE | Exclusão |

### Principais códigos HTTP
- 200 OK
- 201 Created
- 204 No Content
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 500 Internal Server Error

---

## 3. JSON

JSON (JavaScript Object Notation) é o formato mais utilizado para troca de dados entre APIs.

Exemplo:

```json
{
  "id": 1,
  "nome": "João",
  "ativo": true
}
```

---

## 4. Web Services

### Modelos principais
- SOAP
- REST

### SOAP x REST
- SOAP utiliza XML.
- REST utiliza JSON ou XML.
- REST possui menor complexidade e melhor desempenho.

---

## 5. Desenvolvimento de APIs com Spring Boot

### Principais Anotações
- @SpringBootApplication
- @RestController
- @Service
- @Repository
- @GetMapping
- @PostMapping
- @PutMapping
- @DeleteMapping

---

## 6. Arquitetura de Microsserviços

### Características
- Serviços independentes
- Deploy independente
- Banco de dados próprio
- Escalabilidade individual

### Vantagens
- Menor acoplamento
- Melhor escalabilidade
- Evolução independente

### Desvantagens
- Maior complexidade operacional
- Monitoramento distribuído
- Transações mais complexas

---

## 7. Arquitetura Hexagonal

Também conhecida como Ports and Adapters.

Objetivos:
- Isolar regras de negócio
- Facilitar testes
- Reduzir acoplamento

---

## 8. Spring Cloud

Principais componentes:
- Config Server
- Eureka Service Discovery
- OpenFeign
- Circuit Breaker (Resilience4j)

---

## 9. API Gateway

Responsável por:
- Roteamento
- Autenticação
- Monitoramento
- Rate Limiting

Exemplos:
- Spring Cloud Gateway
- Kong
- NGINX

---

## 10. Containers e Docker

Benefícios:
- Portabilidade
- Isolamento
- Escalabilidade
- Agilidade de Deploy

---

## 11. Orquestração de Serviços

Principal ferramenta:
- Kubernetes (K8s)

Principais recursos:
- Pods
- Deployments
- Services
- ConfigMaps
- Secrets

---

## 12. Transações Distribuídas

### 2PC (Two Phase Commit)
- Prepare
- Commit

### Saga Pattern
- Coreografia
- Orquestração
- Transações compensatórias

---

## 13. Boas Práticas para APIs REST

- Utilizar substantivos nas URLs
- Versionar APIs
- Retornar códigos HTTP adequados
- Utilizar HTTPS
- Implementar autenticação JWT/OAuth2
- Paginação de consultas
- Padronização de erros

---

## 14. Exercícios de Fixação

1. Qual a diferença entre PUT e PATCH?
2. O que significa Stateless?
3. Qual a função de um API Gateway?
4. O que é Service Discovery?
5. Como funciona o padrão Saga?
6. Quais vantagens dos microsserviços?

---

## 15. Referências

- Spring Boot Documentation
- Spring Cloud Documentation
- Docker Documentation
- Kubernetes Documentation
- Microservices Patterns — Chris Richardson
- Martin Fowler — Microservices
