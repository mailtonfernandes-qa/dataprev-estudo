# Revisão de Engenharia de Software — Concurso Dataprev

> Material de estudo focado em: SDLC, Scrum, Kanban, UML e Engenharia de Requisitos.

---

## Sumário

1. [Ciclo de Vida de Desenvolvimento de Software (SDLC)](#1-ciclo-de-vida-de-desenvolvimento-de-software-sdlc)
2. [Metodologias Ágeis vs Tradicionais](#2-metodologias-ágeis-vs-tradicionais)
3. [Scrum](#3-scrum)
4. [Kanban](#4-kanban)
5. [Scrum vs Kanban](#5-scrum-vs-kanban)
6. [UML (Unified Modeling Language)](#6-uml-unified-modeling-language)
7. [Engenharia de Requisitos](#7-engenharia-de-requisitos)
8. [Qualidade de Software](#8-qualidade-de-software)
9. [Exercícios de Fixação](#9-exercícios-de-fixação)
10. [Referências](#10-referências)

---

## 1. Ciclo de Vida de Desenvolvimento de Software (SDLC)

O **SDLC (Software Development Life Cycle)** define as fases pelas quais um software passa, do planejamento à manutenção.

### 1.1 Fases clássicas

1. **Levantamento/Análise de Requisitos**
2. **Projeto (Design)** — arquitetura, modelagem
3. **Implementação (Codificação)**
4. **Testes**
5. **Implantação (Deploy)**
6. **Manutenção**

### 1.2 Modelos de processo

| Modelo | Características |
|---|---|
| **Cascata (Waterfall)** | Sequencial, fases não se sobrepõem, pouca flexibilidade a mudanças |
| **Incremental** | Divide o sistema em incrementos entregues progressivamente |
| **Iterativo** | Repete ciclos refinando o produto a cada iteração |
| **Espiral (Boehm)** | Combina iteração com análise de riscos em cada ciclo |
| **V-Model** | Extensão do cascata; cada fase de desenvolvimento tem uma fase de teste correspondente |
| **Ágil (Scrum, XP, Kanban)** | Iterativo-incremental, entregas frequentes, alta adaptação a mudanças |

### 1.3 Modelo Cascata — detalhamento

```
Requisitos → Projeto → Implementação → Testes → Implantação → Manutenção
```
- **Vantagens**: simples, documentação extensa, bom para requisitos estáveis.
- **Desvantagens**: rígido, problemas só aparecem tarde (nos testes), difícil lidar com mudanças.

### 1.4 Modelo Espiral

Cada volta da espiral contém 4 quadrantes:
1. Definir objetivos
2. Analisar e mitigar riscos
3. Desenvolver e validar
4. Planejar a próxima iteração

> Muito cobrado: o Espiral é orientado a **riscos**.

---

## 2. Metodologias Ágeis vs Tradicionais

| Aspecto | Tradicional (Cascata) | Ágil |
|---|---|---|
| Planejamento | Completo no início | Adaptativo, contínuo |
| Entregas | Uma entrega final | Incrementos frequentes |
| Mudanças | Custosas e evitadas | Bem-vindas, esperadas |
| Documentação | Extensa e formal | Suficiente ("just enough") |
| Cliente | Envolvido no início e fim | Envolvido continuamente |
| Equipe | Hierárquica | Auto-organizável |

### 2.1 Manifesto Ágil (4 valores)

1. **Indivíduos e interações** mais que processos e ferramentas
2. **Software em funcionamento** mais que documentação abrangente
3. **Colaboração com o cliente** mais que negociação de contratos
4. **Responder a mudanças** mais que seguir um plano

> Importante: o manifesto valoriza os itens da **esquerda mais que** os da direita — não descarta os da direita.

### 2.2 12 Princípios Ágeis (resumo dos mais cobrados)

- Satisfazer o cliente através de entrega contínua e adiantada de software com valor.
- Aceitar mudanças de requisitos, mesmo tardias no desenvolvimento.
- Entregar software funcionando frequentemente (semanas, não meses).
- Times auto-organizáveis geram as melhores arquiteturas e designs.
- Simplicidade — maximizar a quantidade de trabalho **não realizado** — é essencial.

---

## 3. Scrum

Framework ágil para gestão de projetos, baseado em **Sprints**.

### 3.1 Papéis (Scrum Team)

| Papel | Responsabilidade |
|---|---|
| **Product Owner (PO)** | Maximiza o valor do produto; gerencia o Product Backlog |
| **Scrum Master** | Facilita o processo, remove impedimentos, garante aderência ao framework |
| **Developers (Time de Desenvolvimento)** | Constroem o incremento do produto |

> Desde a Scrum Guide 2020, não existe mais "Scrum Team" composto só por PO + SM + Devs como papéis hierárquicos — todos fazem parte de um único time, auto-gerenciável.

### 3.2 Artefatos

| Artefato | Descrição | Compromisso associado |
|---|---|---|
| **Product Backlog** | Lista ordenada de tudo que é necessário no produto | *Product Goal* |
| **Sprint Backlog** | Itens do Product Backlog selecionados para a Sprint + plano | *Sprint Goal* |
| **Incremento** | Soma de todos os itens completos em uma Sprint (potencialmente entregável) | *Definition of Done* |

### 3.3 Eventos (Cerimônias)

| Evento | Objetivo | Duração (time-box, Sprint de 1 mês) |
|---|---|---|
| **Sprint** | Contêiner para todos os demais eventos; produz o Incremento | Até 1 mês |
| **Sprint Planning** | Planejar o trabalho da Sprint | Até 8h |
| **Daily Scrum** | Sincronizar o time, inspecionar progresso rumo ao Sprint Goal | 15 min |
| **Sprint Review** | Inspecionar o incremento com stakeholders | Até 4h |
| **Sprint Retrospective** | Inspecionar como foi a Sprint (processo, pessoas, ferramentas) e planejar melhorias | Até 3h |

### 3.4 Conceitos importantes

- **Definition of Done (DoD)**: critérios que um incremento deve atender para ser considerado concluído.
- **Definition of Ready (DoR)**: critérios para um item do backlog estar "pronto" para entrar na Sprint (não é oficial da Scrum Guide, mas muito cobrado).
- **Backlog Refinement (Grooming)**: refinamento contínuo do Product Backlog (detalhar, estimar, ordenar).
- **Velocity**: quantidade de trabalho (story points) que o time entrega por Sprint, usada para previsibilidade.
- **Burndown Chart**: gráfico que mostra o trabalho restante ao longo da Sprint.
- **Story Points**: estimativa relativa de esforço/complexidade (ex: sequência de Fibonacci, Planning Poker).

### 3.5 Fluxo do Scrum

```
Product Backlog → Sprint Planning → Sprint Backlog → Daily Scrum (diário)
   → Desenvolvimento (Sprint) → Incremento → Sprint Review → Sprint Retrospective → (nova Sprint)
```

---

## 4. Kanban

Método de gestão visual de fluxo de trabalho, originado no Sistema Toyota de Produção.

### 4.1 Princípios fundamentais

1. **Visualizar o fluxo de trabalho** (quadro Kanban com colunas: To Do, Doing, Done).
2. **Limitar o trabalho em progresso (WIP - Work In Progress)**.
3. **Gerenciar o fluxo** (medir e otimizar o tempo de conclusão).
4. **Tornar as políticas explícitas** (regras claras de cada coluna).
5. **Implementar ciclos de feedback**.
6. **Melhorar colaborativamente, evoluir experimentalmente** (usando modelos científicos).

### 4.2 Características

- **Não possui papéis fixos** (diferente do Scrum, que tem PO/SM/Devs).
- **Não possui iterações fixas (Sprints)** — fluxo contínuo.
- Foco no **Lead Time** e **Cycle Time**:
  - **Lead Time**: tempo total desde a solicitação até a entrega.
  - **Cycle Time**: tempo desde o início do trabalho até a conclusão.
- Utiliza **WIP Limits** para evitar sobrecarga e gargalos.

### 4.3 Exemplo de quadro Kanban

```
| Backlog | To Do (WIP: 3) | Doing (WIP: 2) | Review (WIP: 2) | Done |
|---------|-----------------|-----------------|-------------------|------|
| Item A  | Item D          | Item F          | Item G            | Item H |
| Item B  | Item E          |                 |                   |        |
| Item C  |                 |                 |                   |        |
```

---

## 5. Scrum vs Kanban

| Aspecto | Scrum | Kanban |
|---|---|---|
| Iterações | Sprints fixas (time-boxed) | Fluxo contínuo |
| Papéis | PO, Scrum Master, Developers | Não define papéis específicos |
| Mudanças no backlog em andamento | Evitadas durante a Sprint | Podem ocorrer a qualquer momento |
| Métrica principal | Velocity (story points/Sprint) | Lead Time / Cycle Time |
| Quadro | Sprint Backlog (reiniciado a cada Sprint) | Quadro contínuo, sem reset |
| Limite de trabalho | Definido pela capacidade da Sprint | WIP Limits explícitos por coluna |
| Entregas | Ao fim da Sprint | Contínuas, assim que prontas |

> Pegadinha comum de prova: **Scrumban** é a combinação de Scrum (estrutura de papéis/eventos) com Kanban (fluxo visual e WIP limits).

---

## 6. UML (Unified Modeling Language)

Linguagem de modelagem visual para especificar, construir e documentar sistemas orientados a objetos.

### 6.1 Diagramas Estruturais (estáticos)

| Diagrama | Finalidade |
|---|---|
| **Classes** | Estrutura estática: classes, atributos, métodos e relacionamentos |
| **Objetos** | Instâncias das classes em um momento específico |
| **Componentes** | Organização de componentes de software e suas interfaces |
| **Implantação (Deployment)** | Distribuição física dos componentes em nós de hardware |
| **Pacotes** | Organização de elementos em pacotes/módulos |
| **Estrutura Composta** | Estrutura interna de uma classe/componente em tempo de execução |

### 6.2 Diagramas Comportamentais (dinâmicos)

| Diagrama | Finalidade |
|---|---|
| **Casos de Uso (Use Case)** | Funcionalidades do sistema sob a perspectiva do usuário (ator) |
| **Sequência** | Interação entre objetos ao longo do tempo (ordem das mensagens) |
| **Comunicação** | Similar ao de sequência, mas foca nas relações entre objetos |
| **Atividades** | Fluxo de processos/atividades (parecido com fluxograma) |
| **Máquina de Estados** | Estados possíveis de um objeto e transições entre eles |
| **Interação Geral / Tempo** | Combinações e cronologia de interações |

### 6.3 Diagrama de Casos de Uso — elementos

- **Ator**: entidade externa que interage com o sistema (pessoa, outro sistema).
- **Caso de Uso**: funcionalidade oferecida pelo sistema.
- **Relacionamentos**:
  - `<<include>>`: caso de uso sempre inclui outro (obrigatório).
  - `<<extend>>`: caso de uso opcionalmente estende outro em certas condições.
  - **Generalização**: ator ou caso de uso herda de outro.

```
(Ator: Cliente) --- Realizar Pedido
Realizar Pedido ..> <<include>> ..> Validar Estoque
Realizar Pedido ..> <<extend>> ..> Aplicar Cupom Desconto
```

### 6.4 Diagrama de Classes — relacionamentos

| Relacionamento | Notação | Significado |
|---|---|---|
| **Associação** | linha simples | classes se conhecem/relacionam |
| **Agregação** | linha com losango vazio | "tem um", parte pode existir sem o todo |
| **Composição** | linha com losango preenchido | "é parte de", parte não existe sem o todo (ciclo de vida acoplado) |
| **Herança/Generalização** | linha com seta triangular vazia | "é um" |
| **Realização/Implementação** | linha tracejada com seta triangular vazia | classe implementa uma interface |
| **Dependência** | linha tracejada com seta simples | uma classe depende de outra (uso temporário) |

```
Classe Pedido
- id: Long
- itens: List<ItemPedido>
+ calcularTotal(): double
```

### 6.5 Diagrama de Sequência — elementos

- **Linha de vida (lifeline)**: representa um objeto/ator ao longo do tempo.
- **Mensagem síncrona**: seta sólida cheia (aguarda resposta).
- **Mensagem assíncrona**: seta aberta (não aguarda resposta).
- **Ativação (activation bar)**: retângulo indicando execução de um método.
- **Mensagem de retorno**: seta tracejada.

### 6.6 Diagrama de Atividades — elementos

- **Nó inicial** (círculo preenchido) e **nó final** (círculo com borda).
- **Ação/Atividade** (retângulo arredondado).
- **Decisão** (losango) — fluxo condicional.
- **Barras de sincronização (fork/join)** — paralelismo.
- **Raia (swimlane)** — organiza atividades por responsável.

---

## 7. Engenharia de Requisitos

### 7.1 Classificação de requisitos

| Tipo | Descrição | Exemplo |
|---|---|---|
| **Funcionais (RF)** | O que o sistema deve fazer | "O sistema deve permitir login com CPF e senha" |
| **Não Funcionais (RNF)** | Como o sistema deve se comportar (qualidade) | Desempenho, segurança, usabilidade, disponibilidade |

### 7.2 Atributos de qualidade (RNF) — mnemônico comum

- **Desempenho** (tempo de resposta)
- **Segurança**
- **Usabilidade**
- **Confiabilidade**
- **Disponibilidade**
- **Manutenibilidade**
- **Portabilidade**
- **Escalabilidade**

### 7.3 Processo de Engenharia de Requisitos

1. **Elicitação (Levantamento)** — entrevistas, questionários, observação, brainstorming, workshops (JAD), protótipos.
2. **Análise** — identificar conflitos, ambiguidades, prioridades.
3. **Especificação** — documentar (ex: documento de requisitos, user stories, casos de uso).
4. **Validação** — confirmar com stakeholders que os requisitos refletem a necessidade real.
5. **Gestão de Requisitos** — controle de mudanças, rastreabilidade.

### 7.4 Técnicas de elicitação

| Técnica | Quando usar |
|---|---|
| **Entrevista** | Levantamento individual e detalhado |
| **Questionário** | Grande número de stakeholders |
| **Observação (in loco)** | Entender processos reais do usuário |
| **Brainstorming** | Gerar ideias em grupo |
| **JAD (Joint Application Design)** | Workshops com todos os envolvidos reunidos |
| **Prototipação** | Validar requisitos com um protótipo funcional |
| **Análise de documentos** | Reaproveitar processos/normas já existentes |

### 7.5 User Stories (Ágil)

Formato padrão:
```
Como um <papel/persona>
Eu quero <funcionalidade>
Para que <benefício/motivo>
```

Exemplo:
```
Como um cliente
Eu quero visualizar o histórico dos meus pedidos
Para que eu possa acompanhar minhas compras anteriores
```

**INVEST** — critérios para uma boa user story:
- **I**ndependent (independente)
- **N**egotiable (negociável)
- **V**aluable (valiosa)
- **E**stimable (estimável)
- **S**mall (pequena)
- **T**estable (testável)

### 7.6 Rastreabilidade de Requisitos

Capacidade de acompanhar um requisito desde sua origem até sua implementação e teste, geralmente feita com uma **Matriz de Rastreabilidade**.

```
| Requisito | Origem      | Caso de Uso | Caso de Teste | Status |
|-----------|-------------|-------------|----------------|--------|
| RF-001    | Stakeholder A | UC-01     | CT-01, CT-02   | OK     |
```

---

## 8. Qualidade de Software

### 8.1 Verificação vs Validação

- **Verificação**: "Estamos construindo o produto **corretamente**?" (conformidade com especificação)
- **Validação**: "Estamos construindo o produto **certo**?" (atende à necessidade do usuário)

### 8.2 Normas relevantes (comuns em concursos)

| Norma | Foco |
|---|---|
| **ISO/IEC 25010** | Modelo de qualidade de produto de software (funcionalidade, confiabilidade, usabilidade, eficiência, manutenibilidade, portabilidade, segurança, compatibilidade) |
| **ISO/IEC 12207** | Processos de ciclo de vida de software |
| **CMMI** | Modelo de maturidade de processos organizacionais |
| **MPS.BR** | Modelo brasileiro de melhoria de processo de software |

### 8.3 Testes de Software (visão geral)

| Nível | Foco |
|---|---|
| **Unitário** | Menor unidade de código (método/classe) isolada |
| **Integração** | Interação entre módulos/componentes |
| **Sistema** | Sistema completo, ambiente controlado |
| **Aceitação** | Validação com o usuário/cliente final |

---

## 9. Exercícios de Fixação

1. Cite as diferenças entre o modelo Cascata e o modelo Espiral, destacando o foco principal de cada um.
2. Quais são os 3 papéis do Scrum Team e quais suas principais responsabilidades?
3. Explique o conceito de "WIP Limit" no Kanban e por que ele é importante para o fluxo de trabalho.
4. O que diferencia Agregação de Composição em um diagrama de classes UML? Dê um exemplo de cada.
5. Escreva uma User Story seguindo o critério INVEST para a funcionalidade "recuperação de senha".
6. Explique a diferença entre Verificação e Validação no contexto de qualidade de software.
7. Em um diagrama de casos de uso, quando devemos usar `<<include>>` e quando devemos usar `<<extend>>`?
8. Qual a diferença entre Lead Time e Cycle Time no Kanban?

---

## 10. Referências

- Scrum Guide (oficial): https://scrumguides.org/
- Manifesto Ágil: https://agilemanifesto.org/iso/ptbr/manifesto.html
- Sommerville, Ian. *Engenharia de Software*.
- Pressman, Roger. *Engenharia de Software: Uma Abordagem Profissional*.
- ISO/IEC 25010 — Modelo de Qualidade de Software
- UML.org — https://www.uml.org/

---

> **Dica de estudo**: para provas de concurso, memorize bem os **papéis e eventos do Scrum** (muito cobrados literalmente) e pratique a leitura/interpretação de diagramas UML — geralmente as questões pedem para identificar o tipo de relacionamento ou o tipo de diagrama certo para determinada situação.
