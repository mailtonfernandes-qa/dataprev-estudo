# 02 – Simulado 1 – Questões 1 a 50

> **Concurso:** Dataprev 2026 | **Cargo:** Analista TI – Desenvolvimento de Software | **Banca:** FGV  
> ⏱️ **Tempo sugerido:** 2h30 | 📌 **Sem consulta** | ✏️ Anote suas respostas antes de ver o gabarito

---

## 📋 Folha de Respostas

| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 01 | | 11 | | 21 | | 31 | | 41 | |
| 02 | | 12 | | 22 | | 32 | | 42 | |
| 03 | | 13 | | 23 | | 33 | | 43 | |
| 04 | | 14 | | 24 | | 34 | | 44 | |
| 05 | | 15 | | 25 | | 35 | | 45 | |
| 06 | | 16 | | 26 | | 36 | | 46 | |
| 07 | | 17 | | 27 | | 37 | | 47 | |
| 08 | | 18 | | 28 | | 38 | | 48 | |
| 09 | | 19 | | 29 | | 39 | | 49 | |
| 10 | | 20 | | 30 | | 40 | | 50 | |

---

## 🔵 BLOCO 1 – Engenharia de Software e Metodologias Ágeis (Q01–Q10)

---

**Questão 01**  
No framework Scrum, o artefato que representa a lista ordenada de tudo que é necessário no produto, gerenciada exclusivamente pelo Product Owner, é denominado:

- A) Sprint Backlog  
- B) Product Backlog  
- C) Incremento  
- D) Definition of Done  
- E) Burndown Chart  

---

**Questão 02**  
Em relação ao Scrum, analise as afirmativas abaixo:

I. O Daily Scrum tem duração máxima de 15 minutos e é realizado pelo Time de Desenvolvimento.  
II. O Sprint Planning define o que será entregue na Sprint e como o trabalho será realizado.  
III. O Scrum Master é responsável por maximizar o valor do produto resultante do trabalho do Time de Desenvolvimento.  
IV. A Sprint Retrospective ocorre após a Sprint Review.  

Estão corretas apenas:

- A) I e II  
- B) I, II e IV  
- C) II e III  
- D) I, III e IV  
- E) Todas estão corretas  

---

**Questão 03**  
Considere as afirmativas sobre o modelo de processo Cascata (Waterfall):

I. As fases são executadas de forma sequencial e linear.  
II. É o modelo mais indicado para projetos com requisitos altamente mutáveis.  
III. O retorno a fases anteriores é custoso e não previsto no modelo clássico.  
IV. A fase de testes ocorre apenas após a implementação completa do sistema.  

Estão corretas:

- A) I e III apenas  
- B) I, III e IV apenas  
- C) II e IV apenas  
- D) I, II e IV apenas  
- E) Todas estão corretas  

---

**Questão 04**  
Na Engenharia de Requisitos, a técnica que consiste em observar usuários no seu ambiente de trabalho para identificar necessidades implícitas do sistema é denominada:

- A) Entrevista estruturada  
- B) Prototipação  
- C) Etnografia  
- D) JAD (Joint Application Development)  
- E) Brainstorming  

---

**Questão 05**  
No contexto do Kanban, o conceito de WIP (Work in Progress) Limit refere-se a:

- A) O número máximo de tarefas que podem estar no backlog do projeto.  
- B) A quantidade máxima de itens permitida simultaneamente em uma coluna do quadro.  
- C) O tempo máximo que uma tarefa pode permanecer em desenvolvimento.  
- D) O número de desenvolvedores alocados em uma sprint.  
- E) O limite de histórias de usuário por release.  

---

**Questão 06**  
Em UML, o diagrama utilizado para representar a sequência de mensagens trocadas entre objetos ao longo do tempo, enfatizando a ordem cronológica das interações, é o:

- A) Diagrama de Classes  
- B) Diagrama de Componentes  
- C) Diagrama de Sequência  
- D) Diagrama de Colaboração  
- E) Diagrama de Atividades  

---

**Questão 07**  
O DevOps é uma cultura e conjunto de práticas que visa aproximar as equipes de desenvolvimento e operações. Sobre CI/CD, é correto afirmar que:

- A) CI (Continuous Integration) consiste em entregar automaticamente o software em produção sem intervenção humana.  
- B) CD (Continuous Delivery) garante que o código sempre esteja pronto para ser implantado, mas a implantação em produção pode exigir aprovação manual.  
- C) CI exige que os desenvolvedores integrem código apenas uma vez por semana para evitar conflitos.  
- D) CD (Continuous Deployment) e CD (Continuous Delivery) são termos sinônimos e representam o mesmo processo.  
- E) A prática de CI dispensa o uso de testes automatizados.  

---

**Questão 08**  
No contexto de metodologias ágeis, a técnica de estimativa em que os membros do time atribuem pontos de esforço usando cartas numeradas (geralmente seguindo a sequência de Fibonacci) é conhecida como:

- A) T-Shirt Sizing  
- B) Planning Poker  
- C) Story Mapping  
- D) Dot Voting  
- E) MoSCoW  

---

**Questão 09**  
Sobre o conceito de "Definition of Done" (DoD) no Scrum, é correto afirmar que:

- A) É definido pelo Scrum Master ao início de cada Sprint.  
- B) Representa os critérios que uma história de usuário deve atender para ser considerada aceita pelo cliente.  
- C) É um critério compartilhado por todo o Time Scrum que define quando um incremento está pronto para ser entregue.  
- D) É equivalente ao critério de aceitação definido pelo Product Owner para cada item do backlog.  
- E) Só se aplica ao último Sprint do projeto.  

---

**Questão 10**  
O BPMN (Business Process Model and Notation) é uma notação padrão para modelagem de processos de negócio. Sobre seus elementos, o símbolo que representa um evento que ocorre durante o fluxo de um processo e pode interromper ou não interromper a execução é denominado:

- A) Gateway  
- B) Task  
- C) Intermediate Event  
- D) End Event  
- E) Sub-process  

---

## 🟢 BLOCO 2 – Java e Orientação a Objetos (Q11–Q20)

---

**Questão 11**  
Em Java, sobre o conceito de polimorfismo, analise o trecho de código abaixo:

```java
Animal a = new Cachorro();
a.emitirSom();
```

Considerando que `Cachorro` estende `Animal` e sobrescreve o método `emitirSom()`, o comportamento esperado é:

- A) Chamará o método `emitirSom()` da classe `Animal`, pois a variável é do tipo `Animal`.  
- B) Causará erro de compilação, pois `Animal` não pode referenciar um objeto `Cachorro`.  
- C) Chamará o método `emitirSom()` da classe `Cachorro`, devido ao polimorfismo em tempo de execução.  
- D) O resultado depende do modificador de acesso do método em `Animal`.  
- E) Causará `ClassCastException` em tempo de execução.  

---

**Questão 12**  
Em Java, a palavra-chave `final` pode ser aplicada a variáveis, métodos e classes. Sobre seu uso, é INCORRETO afirmar que:

- A) Uma variável `final` não pode ter seu valor reatribuído após a inicialização.  
- B) Um método `final` não pode ser sobrescrito em subclasses.  
- C) Uma classe `final` não pode ser estendida por outras classes.  
- D) Uma interface `final` impede que outras interfaces a estendam.  
- E) Um parâmetro de método declarado como `final` não pode ser reatribuído dentro do método.  

---

**Questão 13**  
Sobre as coleções em Java, qual das alternativas descreve corretamente a diferença entre `ArrayList` e `LinkedList`?

- A) `ArrayList` utiliza lista encadeada internamente, enquanto `LinkedList` usa array dinâmico.  
- B) `ArrayList` oferece acesso aleatório em O(1), enquanto `LinkedList` tem acesso em O(n).  
- C) `LinkedList` é sempre mais eficiente que `ArrayList` para qualquer operação.  
- D) `ArrayList` não permite elementos nulos, enquanto `LinkedList` permite.  
- E) Ambas implementam a interface `Map`.  

---

**Questão 14**  
Em Java 8+, a Stream API permite o processamento funcional de coleções. Sobre os métodos da Stream API, é correto afirmar que:

- A) O método `filter()` é uma operação terminal que retorna uma nova coleção filtrada.  
- B) O método `collect()` é uma operação intermediária que acumula elementos em uma coleção.  
- C) O método `map()` transforma cada elemento do stream aplicando uma função, retornando um novo stream.  
- D) O método `forEach()` é uma operação intermediária que itera sobre os elementos.  
- E) Streams são reutilizáveis, podendo ser consumidos múltiplas vezes.  

---

**Questão 15**  
Em Java, o modificador de acesso que permite que um membro de classe seja acessível apenas dentro do mesmo pacote e por subclasses, mesmo que estejam em pacotes diferentes, é:

- A) `private`  
- B) `public`  
- C) `default` (sem modificador)  
- D) `protected`  
- E) `internal`  

---

**Questão 16**  
Sobre o princípio da Inversão de Dependência (DIP), o "D" do SOLID, é correto afirmar que:

- A) Módulos de alto nível devem depender de módulos de baixo nível diretamente.  
- B) Classes devem depender de implementações concretas, e não de abstrações.  
- C) Módulos de alto nível e de baixo nível devem depender de abstrações.  
- D) Uma classe deve ter apenas uma única responsabilidade.  
- E) Objetos de uma superclasse devem poder ser substituídos por objetos de suas subclasses sem alterar a correção do programa.  

---

**Questão 17**  
Em Java, sobre o tratamento de exceções, qual afirmativa está INCORRETA?

- A) `RuntimeException` e suas subclasses são exceções não verificadas (unchecked).  
- B) O bloco `finally` é executado independentemente de ocorrer ou não uma exceção.  
- C) Uma exceção verificada (checked) deve ser declarada na assinatura do método com `throws` ou tratada com `try-catch`.  
- D) É possível lançar uma exceção dentro de um bloco `catch`.  
- E) O bloco `finally` não é executado quando `System.exit()` é chamado dentro do bloco `try`.  

---

**Questão 18**  
No contexto de Spring Boot, a anotação utilizada para indicar que uma classe é um componente de serviço da camada de negócio, sendo gerenciada pelo contêiner de injeção de dependência do Spring, é:

- A) `@Repository`  
- B) `@Controller`  
- C) `@Service`  
- D) `@Component`  
- E) `@Bean`  

---

**Questão 19**  
Em Java, sobre interfaces e classes abstratas, é correto afirmar que:

- A) Uma classe abstrata não pode ter métodos com implementação.  
- B) Uma interface não pode ter atributos.  
- C) A partir do Java 8, interfaces podem ter métodos concretos com o modificador `default`.  
- D) Uma classe pode implementar apenas uma interface.  
- E) Uma classe abstrata pode ser instanciada diretamente com `new`.  

---

**Questão 20**  
Em Java, o padrão de projeto Singleton garante que uma classe tenha apenas uma instância. A implementação thread-safe mais recomendada moderna é:

- A) Criar a instância no momento da declaração do atributo estático (Eager Initialization).  
- B) Utilizar bloco `synchronized` em todo o método `getInstance()`.  
- C) Utilizar o padrão de inicialização por demanda com classe interna estática (Initialization-on-demand holder).  
- D) Criar uma nova instância sempre que `getInstance()` for chamado.  
- E) Declarar o construtor como `public` e controlar externamente.  

---

## 🟡 BLOCO 3 – Banco de Dados (Q21–Q30)

---

**Questão 21**  
Em SQL, sobre a diferença entre `INNER JOIN` e `LEFT JOIN`, é correto afirmar que:

- A) `INNER JOIN` retorna todos os registros da tabela da esquerda, mesmo sem correspondência na direita.  
- B) `LEFT JOIN` retorna apenas os registros que possuem correspondência em ambas as tabelas.  
- C) `INNER JOIN` retorna apenas os registros que possuem correspondência em ambas as tabelas.  
- D) `LEFT JOIN` é equivalente ao `FULL OUTER JOIN`.  
- E) Ambos retornam o mesmo resultado quando não há registros sem correspondência.  

---

**Questão 22**  
A forma normal que elimina dependências transitivas em uma tabela relacional, garantindo que atributos não-chave dependam apenas da chave primária, é a:

- A) Primeira Forma Normal (1FN)  
- B) Segunda Forma Normal (2FN)  
- C) Terceira Forma Normal (3FN)  
- D) Forma Normal de Boyce-Codd (BCNF)  
- E) Quarta Forma Normal (4FN)  

---

**Questão 23**  
Sobre bancos de dados NoSQL, qual das alternativas associa corretamente o tipo de banco com um exemplo e seu caso de uso principal?

- A) Documento → Redis → Armazenamento de sessões e cache  
- B) Chave-Valor → MongoDB → Consultas complexas com documentos JSON  
- C) Colunar → Cassandra → Alta escalabilidade para grandes volumes de dados distribuídos  
- D) Grafo → HBase → Armazenamento de séries temporais  
- E) Documento → Neo4j → Relacionamentos complexos entre entidades  

---

**Questão 24**  
Em SQL, o comando utilizado para criar um índice em uma coluna da tabela `funcionarios` na coluna `cpf` é:

- A) `ALTER TABLE funcionarios ADD INDEX cpf;`  
- B) `CREATE INDEX idx_cpf ON funcionarios(cpf);`  
- C) `INSERT INDEX idx_cpf INTO funcionarios(cpf);`  
- D) `ADD INDEX idx_cpf TO funcionarios ON cpf;`  
- E) `CREATE KEY idx_cpf ON funcionarios(cpf);`  

---

**Questão 25**  
Sobre transações em banco de dados, o conjunto de propriedades ACID define os requisitos para garantir a integridade das transações. O que representa a propriedade "Isolamento" (Isolation)?

- A) Garante que uma transação confirmada não será desfeita.  
- B) Garante que o banco de dados permaneça em estado consistente antes e depois da transação.  
- C) Garante que transações concorrentes sejam executadas sem interferência entre si.  
- D) Garante que a transação seja completada integralmente ou desfeita totalmente.  
- E) Garante que os dados sejam replicados em múltiplos servidores.  

---

**Questão 26**  
Em MongoDB, sobre a estrutura de documentos, é correto afirmar que:

- A) Documentos são armazenados no formato XML.  
- B) Uma collection no MongoDB equivale a uma linha em banco relacional.  
- C) Documentos em uma mesma collection devem ter o mesmo esquema fixo.  
- D) O MongoDB armazena dados em documentos no formato BSON (Binary JSON).  
- E) MongoDB não suporta consultas com filtros por campo.  

---

**Questão 27**  
Considere a consulta SQL abaixo:

```sql
SELECT departamento, COUNT(*) as total
FROM funcionarios
WHERE salario > 5000
GROUP BY departamento
HAVING COUNT(*) > 3
ORDER BY total DESC;
```

Sobre esta consulta, é correto afirmar que:

- A) A cláusula `HAVING` filtra os registros antes do `GROUP BY`.  
- B) A cláusula `WHERE` pode ser substituída por `HAVING` sem alteração de resultado.  
- C) O resultado trará departamentos com mais de 3 funcionários com salário acima de R$ 5.000.  
- D) O `ORDER BY` é processado antes do `GROUP BY`.  
- E) A consulta apresentará erro, pois `HAVING` não pode usar funções de agregação.  

---

**Questão 28**  
O conceito de ORM (Object-Relational Mapping) no desenvolvimento Java é implementado pela especificação:

- A) JDBC  
- B) JPA (Java Persistence API)  
- C) JNDI  
- D) JMS  
- E) JSF  

---

**Questão 29**  
Sobre o conceito de sharding em bancos de dados distribuídos, é correto afirmar que:

- A) Sharding é uma técnica de replicação que copia os dados para múltiplos servidores para aumentar a disponibilidade.  
- B) Sharding é o processo de particionar horizontalmente os dados em múltiplos nós para aumentar a escalabilidade.  
- C) Sharding distribui verticalmente os dados, separando tabelas por colunas em servidores distintos.  
- D) Sharding é exclusivo dos bancos de dados relacionais.  
- E) Sharding elimina completamente a necessidade de replicação de dados.  

---

**Questão 30**  
Em Redis, qual estrutura de dados é mais adequada para implementar uma fila (FIFO) de mensagens?

- A) String  
- B) Hash  
- C) Set  
- D) List  
- E) Sorted Set  

---

## 🔴 BLOCO 4 – APIs REST e Microsserviços (Q31–Q38)

---

**Questão 31**  
Sobre os princípios REST (Representational State Transfer), a restrição que determina que o servidor não deve armazenar o estado da sessão do cliente entre requisições é denominada:

- A) Interface Uniforme  
- B) Sistema em Camadas  
- C) Stateless  
- D) Cache  
- E) Code on Demand  

---

**Questão 32**  
Em uma API RESTful, o método HTTP mais adequado para atualizar parcialmente um recurso existente é:

- A) `PUT`  
- B) `POST`  
- C) `DELETE`  
- D) `PATCH`  
- E) `GET`  

---

**Questão 33**  
Sobre os códigos de status HTTP, associe corretamente:

I. 200 – Created  
II. 201 – OK  
III. 401 – Forbidden  
IV. 403 – Unauthorized  
V. 404 – Not Found  

A alternativa que apresenta TODAS as associações corretas é:

- A) Apenas V está correta  
- B) I e II estão invertidos; III e IV estão invertidos; V está correta  
- C) Todas estão corretas  
- D) Apenas I e II estão invertidos  
- E) Apenas III e IV estão invertidos  

---

**Questão 34**  
Em arquitetura de microsserviços, o padrão que consiste em um serviço que atua como ponto único de entrada para todos os clientes, roteando requisições para os microsserviços internos adequados, é denominado:

- A) Service Mesh  
- B) Circuit Breaker  
- C) API Gateway  
- D) Event Sourcing  
- E) Saga Pattern  

---

**Questão 35**  
O padrão Circuit Breaker em microsserviços tem como principal objetivo:

- A) Criptografar a comunicação entre microsserviços.  
- B) Prevenir falhas em cascata ao interromper chamadas para serviços que estão com problemas.  
- C) Garantir a consistência de dados entre microsserviços através de transações distribuídas.  
- D) Gerenciar o balanceamento de carga entre instâncias de um microsserviço.  
- E) Registrar e auditar todas as chamadas entre microsserviços.  

---

**Questão 36**  
Sobre a especificação OpenAPI (anteriormente conhecida como Swagger), é correto afirmar que:

- A) É um protocolo de comunicação entre serviços, substituto do REST.  
- B) É uma especificação para descrever, produzir e consumir APIs RESTful de forma padronizada.  
- C) É exclusiva para APIs SOAP e não se aplica a APIs REST.  
- D) O arquivo de especificação OpenAPI só pode ser escrito em XML.  
- E) OpenAPI é uma ferramenta de monitoramento de APIs em produção.  

---

**Questão 37**  
Em microsserviços, o padrão Saga é utilizado para:

- A) Descoberta de serviços em um ambiente distribuído.  
- B) Gerenciar transações distribuídas entre múltiplos microsserviços, garantindo consistência eventual.  
- C) Implementar autenticação centralizada entre microsserviços.  
- D) Armazenar o estado de cada microsserviço em um banco de dados central.  
- E) Monitorar o desempenho de cada microsserviço em tempo real.  

---

**Questão 38**  
Sobre a diferença entre REST e SOAP, é correto afirmar que:

- A) SOAP é mais leve e performático que REST por usar JSON.  
- B) REST é um protocolo, enquanto SOAP é um estilo arquitetural.  
- C) SOAP utiliza XML como formato de mensagem e possui um contrato formal definido pelo WSDL.  
- D) REST obriga o uso do protocolo HTTP, enquanto SOAP pode usar apenas SMTP.  
- E) Ambos exigem o uso de XML para troca de mensagens.  

---

## 🟣 BLOCO 5 – DevOps, Git, Docker e Segurança (Q39–Q50)

---

**Questão 39**  
No Git, o comando utilizado para criar uma nova branch chamada `feature/login` e já mudar para ela em um único comando é:

- A) `git branch feature/login`  
- B) `git checkout feature/login`  
- C) `git checkout -b feature/login`  
- D) `git merge feature/login`  
- E) `git clone feature/login`  

---

**Questão 40**  
Sobre o Git Flow, o fluxo de trabalho que organiza branches em `main`, `develop`, `feature`, `release` e `hotfix`, é correto afirmar que:

- A) As branches `feature` são criadas a partir da `main` e mergeadas diretamente nela.  
- B) A branch `hotfix` é criada a partir de `develop` para corrigir bugs em produção.  
- C) As branches `feature` são criadas a partir de `develop` e mergeadas de volta em `develop`.  
- D) A branch `release` é mergeada apenas em `main`, sem tocar em `develop`.  
- E) O Git Flow não prevê o uso de tags para marcar versões.  

---

**Questão 41**  
Em Docker, o arquivo `Dockerfile` define como uma imagem Docker é construída. A instrução utilizada para definir o comando padrão que será executado quando o contêiner for iniciado é:

- A) `RUN`  
- B) `COPY`  
- C) `FROM`  
- D) `CMD`  
- E) `EXPOSE`  

---

**Questão 42**  
Sobre Docker e contêineres, é correto afirmar que:

- A) Contêineres compartilham o kernel do sistema operacional host, diferentemente de máquinas virtuais.  
- B) Uma imagem Docker é um contêiner em execução.  
- C) O Docker Compose é utilizado para orquestrar contêineres em ambientes de produção de larga escala.  
- D) Contêineres Docker são sempre imutáveis e não podem ter dados persistidos.  
- E) O `docker run` cria uma nova imagem a partir de um Dockerfile.  

---

**Questão 43**  
No Kubernetes, o recurso que garante que um número específico de réplicas de um Pod esteja sempre em execução é denominado:

- A) Service  
- B) Ingress  
- C) ConfigMap  
- D) ReplicaSet  
- E) Namespace  

---

**Questão 44**  
O OWASP Top 10 é uma lista das principais vulnerabilidades em aplicações web. A vulnerabilidade que ocorre quando dados fornecidos pelo usuário são enviados ao interpretador como parte de um comando ou consulta, sem a devida sanitização, é denominada:

- A) Broken Authentication  
- B) Security Misconfiguration  
- C) Injection  
- D) Insecure Deserialization  
- E) Cross-Site Scripting (XSS)  

---

**Questão 45**  
Sobre a LGPD (Lei Geral de Proteção de Dados – Lei nº 13.709/2018), é correto afirmar que:

- A) A LGPD se aplica apenas a empresas privadas, não abrangendo órgãos públicos.  
- B) O tratamento de dados pessoais sensíveis, como dados de saúde e biométricos, possui regras mais rígidas que os dados pessoais comuns.  
- C) A LGPD não prevê sanções financeiras para organizações que descumprirem suas normas.  
- D) O consentimento do titular é a única base legal que autoriza o tratamento de dados pessoais.  
- E) A LGPD proíbe completamente o tratamento de dados pessoais de crianças e adolescentes.  

---

**Questão 46**  
Em testes de software, o tipo de teste que verifica se diferentes módulos ou componentes do sistema funcionam corretamente quando integrados é denominado:

- A) Teste Unitário  
- B) Teste de Sistema  
- C) Teste de Aceitação  
- D) Teste de Integração  
- E) Teste de Regressão  

---

**Questão 47**  
O TDD (Test-Driven Development) é uma técnica de desenvolvimento em que os testes são escritos antes do código de produção. O ciclo correto do TDD é:

- A) Código → Refatoração → Teste  
- B) Teste → Código → Refatoração (Red → Green → Refactor)  
- C) Refatoração → Teste → Código  
- D) Código → Teste → Refatoração  
- E) Teste → Refatoração → Código  

---

**Questão 48**  
Sobre o padrão arquitetural MVC (Model-View-Controller), é correto afirmar que:

- A) A View contém a lógica de negócio da aplicação.  
- B) O Controller acessa diretamente o banco de dados sem passar pelo Model.  
- C) O Model representa os dados e a lógica de negócio da aplicação.  
- D) O MVC é exclusivo para aplicações desktop e não se aplica a aplicações web.  
- E) Em MVC, a View se comunica diretamente com o Model sem passar pelo Controller.  

---

**Questão 49**  
Em relação à Inteligência Artificial aplicada ao desenvolvimento de software, o uso de modelos de linguagem (LLMs) como assistentes de código tem como principal benefício:

- A) Substituir completamente os desenvolvedores humanos em projetos complexos.  
- B) Garantir que o código gerado esteja sempre livre de vulnerabilidades de segurança.  
- C) Aumentar a produtividade ao sugerir código, completar funções e auxiliar na detecção de bugs.  
- D) Gerar código que não precisa de revisão humana para ser enviado à produção.  
- E) Eliminar a necessidade de testes de software nas aplicações geradas por IA.  

---

**Questão 50**  
Sobre computação em nuvem, os modelos de serviço IaaS, PaaS e SaaS diferem pela responsabilidade do provedor e do cliente. A respeito do modelo PaaS (Platform as a Service), é correto afirmar que:

- A) O cliente gerencia o sistema operacional, middleware e runtime, além da aplicação.  
- B) O provedor gerencia toda a infraestrutura, incluindo a aplicação e os dados do cliente.  
- C) O cliente é responsável apenas pelo desenvolvimento e gestão de suas aplicações e dados, enquanto o provedor gerencia a plataforma subjacente.  
- D) PaaS é o mesmo que SaaS, diferindo apenas no modelo de cobrança.  
- E) No PaaS, o cliente tem acesso e controle total sobre o hardware físico.  

---

## 📊 Gabarito Resumido

> ⚠️ **Não consulte antes de terminar o simulado!**

| Q | R | Q | R | Q | R | Q | R | Q | R |
|---|---|---|---|---|---|---|---|---|---|
| 01 | B | 11 | C | 21 | C | 31 | C | 41 | D |
| 02 | B | 12 | D | 22 | C | 32 | D | 42 | A |
| 03 | B | 13 | B | 23 | C | 33 | B | 43 | D |
| 04 | C | 14 | C | 24 | B | 34 | C | 44 | C |
| 05 | B | 15 | D | 25 | C | 35 | B | 45 | B |
| 06 | C | 16 | C | 26 | D | 36 | B | 46 | D |
| 07 | B | 17 | E | 27 | C | 37 | B | 47 | B |
| 08 | B | 18 | C | 28 | B | 38 | C | 48 | C |
| 09 | C | 19 | C | 29 | B | 39 | C | 49 | C |
| 10 | C | 20 | C | 30 | D | 40 | C | 50 | C |

---

> 📌 **Próximo passo:** Acesse o [Gabarito Comentado do Simulado 1](03-gabarito-simulado-1.md) para entender cada resposta em detalhe!
