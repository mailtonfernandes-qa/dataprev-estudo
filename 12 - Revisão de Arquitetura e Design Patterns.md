# Revisão Completa de Arquitetura e Design Patterns — Concurso Dataprev (Desenvolvimento de Software)

Material de estudo focado em: Arquitetura de Software, SOLID, Design Patterns GoF, MVC, Clean Architecture e Boas Práticas de Desenvolvimento.

## Sumário

- Fundamentos de Arquitetura de Software
- Princípios SOLID
- Design Patterns GoF
- MVC
- Clean Architecture
- Acoplamento e Coesão
- Injeção de Dependência
- Arquiteturas Modernas
- Boas Práticas
- Exercícios de Fixação
- Referências

---

# 1. Fundamentos de Arquitetura de Software

Arquitetura de Software define a estrutura de alto nível de um sistema, seus componentes, relacionamentos e princípios de evolução.

Objetivos:

- Escalabilidade
- Manutenibilidade
- Reutilização
- Testabilidade
- Segurança

---

# 2. Princípios SOLID

## S – Single Responsibility Principle

Uma classe deve possuir apenas um motivo para mudar.

## O – Open/Closed Principle

Aberta para extensão e fechada para modificação.

## L – Liskov Substitution Principle

Subtipos devem substituir seus tipos base sem alterar comportamento esperado.

## I – Interface Segregation Principle

Prefira interfaces específicas ao invés de interfaces genéricas.

## D – Dependency Inversion Principle

Depender de abstrações e não de implementações.

Benefícios do SOLID:

- Baixo acoplamento
- Alta coesão
- Facilidade de testes
- Facilidade de manutenção

---

# 3. Design Patterns GoF

## O que são?

Soluções reutilizáveis para problemas recorrentes de projeto de software.

## Padrões Criacionais

- Singleton
- Factory Method
- Abstract Factory
- Builder
- Prototype

## Padrões Estruturais

- Adapter
- Bridge
- Composite
- Decorator
- Facade
- Proxy

## Padrões Comportamentais

- Strategy
- Observer
- Command
- Chain of Responsibility
- State
- Template Method

---

# 4. MVC (Model View Controller)

## Model

Representa regras de negócio e dados.

## View

Responsável pela apresentação.

## Controller

Coordena requisições entre View e Model.

Fluxo:

Usuário → Controller → Model → View

Benefícios:

- Separação de responsabilidades
- Facilidade de manutenção
- Reutilização de código

---

# 5. Clean Architecture

Criada por Robert C. Martin (Uncle Bob).

Objetivo: independência de frameworks, banco de dados e interface.

## Camadas

### Entities

Regras de negócio corporativas.

### Use Cases

Casos de uso da aplicação.

### Interface Adapters

Controllers, Presenters e Gateways.

### Frameworks & Drivers

Banco de dados, APIs, UI e frameworks.

## Regra da Dependência

Dependências sempre apontam para dentro.

Benefícios:

- Testabilidade
- Flexibilidade
- Baixo acoplamento

---

# 6. Acoplamento e Coesão

## Acoplamento

Grau de dependência entre componentes.

Boa prática: baixo acoplamento.

## Coesão

Relacionamento entre responsabilidades de uma classe.

Boa prática: alta coesão.

---

# 7. Injeção de Dependência

Técnica para fornecer dependências externamente.

Benefícios:

- Facilita mocks
- Facilita testes unitários
- Reduz acoplamento

Exemplo comum:

- Spring Framework
- .NET Dependency Injection

---

# 8. Arquiteturas Modernas

## Monolítica

Aplicação única implantada como um bloco.

## Microsserviços

Serviços independentes com deploy próprio.

## Arquitetura Hexagonal

Ports and Adapters.

## Arquitetura em Camadas

- Apresentação
- Negócio
- Persistência

---

# 9. Boas Práticas

- Aplicar SOLID
- Utilizar padrões quando necessário
- Evitar complexidade excessiva
- Favorecer composição ao invés de herança
- Utilizar injeção de dependência
- Criar código testável

---

# 10. Exercícios de Fixação

1. O que é arquitetura de software?
2. Explique cada princípio SOLID.
3. Qual objetivo do padrão Strategy?
4. Diferencie Factory e Builder.
5. Explique MVC.
6. O que é Clean Architecture?
7. O que significa baixo acoplamento?
8. O que é alta coesão?
9. Explique Inversão de Dependência.
10. Compare arquitetura monolítica e microsserviços.

---

# 11. Referências

- Clean Architecture — Robert C. Martin
- Clean Code — Robert C. Martin
- Design Patterns — GoF
- Refactoring Guru
- Martin Fowler

## Dicas para Prova

✅ SOLID
✅ Design Patterns GoF
✅ Singleton
✅ Factory Method
✅ Strategy
✅ Observer
✅ MVC
✅ Clean Architecture
✅ Acoplamento e Coesão
✅ Injeção de Dependência
✅ Arquitetura Hexagonal
✅ Microsserviços
