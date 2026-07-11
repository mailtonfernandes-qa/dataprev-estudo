# Revisão Completa de Testes de Software — Concurso Dataprev (Desenvolvimento de Software)

Material de estudo focado em: Fundamentos de Testes, Tipos de Testes, Níveis de Testes, Automação, TDD, BDD e Boas Práticas.

## Sumário

- Fundamentos de Testes de Software
- Princípios de Teste
- Processo de Teste
- Tipos de Teste
- Níveis de Teste
- Técnicas de Projeto de Testes
- Testes Funcionais e Não Funcionais
- Automação de Testes
- Test Driven Development (TDD)
- Behavior Driven Development (BDD)
- Ferramentas de Mercado
- Métricas e Indicadores
- Exercícios de Fixação
- Referências

---

# 1. Fundamentos de Testes de Software

## O que é Teste de Software?

Teste é o processo utilizado para verificar e validar se um sistema atende aos requisitos especificados e se funciona conforme esperado.

Objetivos:

- Encontrar defeitos
- Reduzir riscos
- Aumentar a qualidade
- Garantir conformidade com requisitos
- Melhorar a confiabilidade do sistema

---

# 2. Princípios de Teste

Os 7 princípios ISTQB:

## 2.1 Testes mostram a presença de defeitos

Os testes demonstram defeitos existentes, mas não provam a ausência deles.

## 2.2 Teste exaustivo é impossível

Não é viável testar todas as combinações possíveis.

## 2.3 Teste antecipado

Os testes devem começar o mais cedo possível.

## 2.4 Agrupamento de defeitos

A maioria dos defeitos concentra-se em poucas áreas.

## 2.5 Paradoxo do pesticida

Casos de teste devem ser revisados periodicamente.

## 2.6 Teste depende do contexto

Cada sistema exige abordagens diferentes.

## 2.7 Ausência de erros é uma falácia

Um software sem defeitos pode ainda não atender às necessidades do usuário.

---

# 3. Processo de Teste

Fases principais:

1. Planejamento
2. Análise
3. Projeto
4. Implementação
5. Execução
6. Encerramento

Artefatos comuns:

- Plano de Teste
- Casos de Teste
- Evidências
- Relatório de Execução
- Relatório de Defeitos

---

# 4. Tipos de Teste

## Teste Funcional

Valida funcionalidades do sistema.

Exemplo:

- Login
- Cadastro
- Consulta
- Exclusão

## Teste Não Funcional

Avalia características de qualidade.

Exemplos:

- Performance
- Segurança
- Usabilidade
- Escalabilidade

## Teste de Regressão

Verifica se alterações não impactaram funcionalidades existentes.

## Teste Exploratório

Execução simultânea de aprendizado, criação e execução dos testes.

## Teste de Aceitação

Valida se o sistema atende às necessidades do negócio.

---

# 5. Níveis de Teste

## 5.1 Teste Unitário

Valida pequenas unidades de código.

Características:

- Rápido
- Isolado
- Executado por desenvolvedores

Ferramentas:

- JUnit
- NUnit
- MSTest

## 5.2 Teste de Integração

Valida comunicação entre componentes.

Exemplos:

- API + Banco
- Microsserviços
- Sistemas externos

## 5.3 Teste de Sistema

Avalia o sistema completo.

## 5.4 Teste de Aceitação

Executado sob a ótica do usuário ou negócio.

---

# 6. Técnicas de Projeto de Testes

## Particionamento de Equivalência

Divide entradas em classes válidas e inválidas.

## Análise de Valor Limite

Foco nos extremos dos dados.

Exemplo:

Campo idade: 18 a 65

Testes:

- 17
- 18
- 19
- 64
- 65
- 66

## Tabela de Decisão

Utilizada quando existem múltiplas regras de negócio.

## Transição de Estados

Avalia mudanças de estados do sistema.

---

# 7. Testes Funcionais e Não Funcionais

## Performance

Avalia tempo de resposta e consumo de recursos.

Tipos:

- Carga
- Estresse
- Volume
- Resistência

## Segurança

Avalia vulnerabilidades.

Exemplos:

- SQL Injection
- XSS
- Autenticação
- Autorização

## Usabilidade

Avalia experiência do usuário.

---

# 8. Automação de Testes

## Objetivos

- Reduzir esforço manual
- Aumentar cobertura
- Executar regressão rapidamente

## Pirâmide de Testes

Base:

- Testes Unitários

Meio:

- Testes de Integração

Topo:

- Testes End-to-End

## Benefícios

- Velocidade
- Repetibilidade
- Confiabilidade

## Limitações

- Custo inicial
- Manutenção dos scripts

---

# 9. Test Driven Development (TDD)

Metodologia baseada na escrita dos testes antes da implementação.

## Ciclo Red-Green-Refactor

### Red

Criar teste falhando.

### Green

Implementar o mínimo para passar.

### Refactor

Melhorar o código sem alterar comportamento.

Benefícios:

- Código mais limpo
- Baixo acoplamento
- Maior cobertura

---

# 10. Behavior Driven Development (BDD)

Extensão do TDD focada em comportamento de negócio.

Utiliza linguagem próxima ao negócio.

## Estrutura Gherkin

Feature
Scenario
Given
When
Then

Exemplo:

Scenario: Login válido

Given que o usuário possui cadastro
When informar usuário e senha válidos
Then o sistema deve permitir acesso

## Vantagens

- Comunicação entre negócio e TI
- Rastreabilidade
- Documentação viva

Ferramentas:

- Cucumber
- SpecFlow
- Behave

---

# 11. Ferramentas de Mercado

## Automação Web

- Selenium
- Playwright
- Cypress

## Automação API

- Postman
- Rest Assured
- Karate

## Gestão de Testes

- Azure DevOps
- Jira
- TestRail

## Performance

- JMeter
- Gatling

---

# 12. Métricas e Indicadores

## Cobertura de Testes

Percentual de código validado.

## Taxa de Defeitos

Quantidade de defeitos encontrados.

## Densidade de Defeitos

Defeitos por tamanho do software.

## Taxa de Sucesso

Casos aprovados versus executados.

---

# 13. Exercícios de Fixação

1. Diferencie verificação e validação.
2. Explique os níveis de teste.
3. O que é regressão?
4. Qual a diferença entre TDD e BDD?
5. Quando utilizar automação?
6. Explique a pirâmide de testes.
7. O que é particionamento de equivalência?
8. O que são valores limites?
9. Cite tipos de testes não funcionais.
10. Quais benefícios do BDD?

---

# 14. Referências

- ISTQB Foundation Level
- ISO/IEC 25010
- Agile Testing – Lisa Crispin
- Selenium Documentation
- Playwright Documentation
- Cucumber Documentation
- Microsoft Testing Practices

## Dicas para Prova

✅ Princípios ISTQB

✅ Níveis de Teste

✅ Tipos de Teste

✅ Técnicas de Projeto de Teste

✅ Automação

✅ TDD

✅ BDD

✅ Pirâmide de Testes

✅ Métricas de Qualidade

✅ Ferramentas de Mercado
