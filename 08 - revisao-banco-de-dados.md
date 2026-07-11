# Revisão de Banco de Dados — Concurso Dataprev

> Material de estudo focado em: SQL, NoSQL, Modelagem de Dados e Normalização.

---

## Sumário

1. [Conceitos Fundamentais](#1-conceitos-fundamentais)
2. [Modelagem de Dados](#2-modelagem-de-dados)
3. [Normalização](#3-normalização)
4. [SQL — Linguagem](#4-sql--linguagem)
5. [Transações e Controle de Concorrência](#5-transações-e-controle-de-concorrência)
6. [Índices e Performance](#6-índices-e-performance)
7. [NoSQL](#7-nosql)
8. [SQL vs NoSQL](#8-sql-vs-nosql)
9. [Exercícios de Fixação](#9-exercícios-de-fixação)
10. [Referências](#10-referências)

---

## 1. Conceitos Fundamentais

### 1.1 Definições

- **SGBD (Sistema de Gerenciamento de Banco de Dados)**: software que gerencia a criação, manutenção e uso de bancos de dados (ex: PostgreSQL, MySQL, Oracle, SQL Server).
- **Banco de Dados Relacional**: organiza dados em tabelas (relações) com linhas (tuplas) e colunas (atributos).
- **Chave Primária (Primary Key - PK)**: identifica unicamente cada registro em uma tabela.
- **Chave Estrangeira (Foreign Key - FK)**: referencia a chave primária de outra tabela, garantindo integridade referencial.
- **Chave Candidata**: qualquer atributo (ou conjunto) que poderia ser PK.
- **Chave Composta**: chave formada por mais de uma coluna.

### 1.2 Propriedades ACID

| Propriedade | Significado |
|---|---|
| **A**tomicidade | Transação é "tudo ou nada" — ou executa completamente ou não executa |
| **C**onsistência | Transação leva o banco de um estado válido a outro estado válido |
| **I**solamento | Transações concorrentes não interferem umas nas outras |
| **D**urabilidade | Após o commit, os dados persistem mesmo em caso de falha |

---

## 2. Modelagem de Dados

### 2.1 Níveis de modelagem

1. **Modelo Conceitual** — visão abstrata, independe de tecnologia (ex: Diagrama Entidade-Relacionamento — DER/MER).
2. **Modelo Lógico** — já considera o tipo de SGBD (relacional, documentos, etc.), mas ainda não é físico.
3. **Modelo Físico** — implementação real no SGBD (tipos de dados específicos, índices, constraints).

### 2.2 Modelo Entidade-Relacionamento (MER/DER)

**Componentes principais:**

- **Entidade**: objeto do mundo real representado no banco (ex: Cliente, Pedido).
- **Atributo**: propriedade de uma entidade (ex: nome, CPF).
  - **Simples** vs **Composto** (ex: endereço → rua, cidade, CEP).
  - **Monovalorado** vs **Multivalorado** (ex: telefones de um cliente).
  - **Atributo derivado**: calculado a partir de outro (ex: idade a partir da data de nascimento).
- **Relacionamento**: associação entre entidades (ex: Cliente **faz** Pedido).
- **Cardinalidade**: quantas ocorrências de uma entidade se relacionam com outra.

### 2.3 Cardinalidades

| Tipo | Notação | Exemplo |
|---|---|---|
| 1:1 | um-para-um | Pessoa — Passaporte |
| 1:N | um-para-muitos | Cliente — Pedidos |
| N:M | muitos-para-muitos | Aluno — Disciplina |

> Relacionamentos N:M no modelo lógico/físico exigem uma **tabela associativa** (tabela de junção) para serem implementados no modelo relacional.

```
Aluno (id, nome)
Disciplina (id, nome)
Aluno_Disciplina (aluno_id FK, disciplina_id FK, nota)
```

### 2.4 Especialização/Generalização

- **Generalização**: entidades específicas generalizadas em uma entidade "pai" (ex: Cliente Pessoa Física e Cliente Pessoa Jurídica generalizam para Cliente).
- **Especialização**: processo inverso — dividir uma entidade genérica em subtipos.
- **Total vs Parcial**: toda ocorrência da entidade pai deve (total) ou não (parcial) pertencer a uma subclasse.
- **Disjunta vs Sobreposta**: uma ocorrência pode pertencer a apenas uma subclasse (disjunta) ou a várias (sobreposta).

### 2.5 Diagrama Entidade-Relacionamento (exemplo textual)

```
[Cliente] 1 ---- N [Pedido] N ---- N [Produto]
   PK: id             PK: id            PK: id
   nome                cliente_id (FK)   nome
   cpf                 data              preco
```

---

## 3. Normalização

Processo de organizar os dados para reduzir **redundância** e evitar **anomalias** de inserção, atualização e exclusão.

### 3.1 Anomalias evitadas pela normalização

- **Anomalia de Inserção**: impossível inserir um dado sem que outro esteja presente.
- **Anomalia de Atualização**: necessidade de atualizar o mesmo dado em vários lugares (inconsistência).
- **Anomalia de Exclusão**: ao excluir um registro, perde-se informação que não deveria ser perdida.

### 3.2 Formas Normais

#### 1ª Forma Normal (1FN)
- Todos os atributos devem ser **atômicos** (sem grupos repetitivos ou valores multivalorados).

```
❌ Não está em 1FN:
Cliente(id, nome, telefones: "11999, 11888")

✔ Em 1FN:
Cliente(id, nome)
Telefone(cliente_id FK, numero)
```

#### 2ª Forma Normal (2FN)
- Deve estar em 1FN.
- Todo atributo não-chave deve depender da **chave primária inteira** (elimina dependência parcial — aplica-se a chaves compostas).

```
❌ Não está em 2FN (chave composta: pedido_id + produto_id):
ItemPedido(pedido_id, produto_id, nome_produto, quantidade)
-- nome_produto depende só de produto_id, não da chave inteira

✔ Em 2FN:
ItemPedido(pedido_id, produto_id, quantidade)
Produto(produto_id, nome_produto)
```

#### 3ª Forma Normal (3FN)
- Deve estar em 2FN.
- Nenhum atributo não-chave pode depender de **outro atributo não-chave** (elimina dependência transitiva).

```
❌ Não está em 3FN:
Funcionario(id, nome, departamento_id, nome_departamento)
-- nome_departamento depende de departamento_id (não-chave), não do id do funcionário

✔ Em 3FN:
Funcionario(id, nome, departamento_id)
Departamento(id, nome_departamento)
```

#### Forma Normal de Boyce-Codd (FNBC/BCNF)
- Versão mais rigorosa da 3FN: para toda dependência funcional X → Y, X deve ser uma **superchave**.

#### 4ª Forma Normal (4FN)
- Elimina dependências multivaloradas independentes.

> Para concursos, o mais cobrado é até a **3FN**. FNBC e 4FN aparecem em provas mais avançadas.

### 3.3 Dependência Funcional

Notação: `A → B` significa "B depende funcionalmente de A" (conhecendo A, determina-se B).

```
CPF → Nome, Endereço  (CPF determina nome e endereço)
```

### 3.4 Desnormalização

Processo inverso, aplicado intencionalmente para **melhorar performance de leitura** em troca de redundância controlada (comum em Data Warehouses e relatórios).

---

## 4. SQL — Linguagem

SQL (Structured Query Language) se divide em sublinguagens:

| Sublinguagem | Comandos | Finalidade |
|---|---|---|
| **DDL** (Data Definition Language) | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` | Define estrutura |
| **DML** (Data Manipulation Language) | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | Manipula dados |
| **DCL** (Data Control Language) | `GRANT`, `REVOKE` | Controla permissões |
| **TCL** (Transaction Control Language) | `COMMIT`, `ROLLBACK`, `SAVEPOINT` | Controla transações |

### 4.1 DDL — Exemplos

```sql
CREATE TABLE cliente (
    id BIGINT PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    nome VARCHAR(100) NOT NULL,
    cpf CHAR(11) UNIQUE NOT NULL,
    data_nascimento DATE
);

CREATE TABLE pedido (
    id BIGINT PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    cliente_id BIGINT NOT NULL,
    data_pedido TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    CONSTRAINT fk_cliente FOREIGN KEY (cliente_id) REFERENCES cliente(id)
);

ALTER TABLE cliente ADD COLUMN email VARCHAR(150);
ALTER TABLE cliente DROP COLUMN data_nascimento;

DROP TABLE pedido;
TRUNCATE TABLE pedido; -- remove todos os dados, mas mantém a estrutura (mais rápido que DELETE)
```

### 4.2 DML — Exemplos

```sql
-- INSERT
INSERT INTO cliente (nome, cpf) VALUES ('Ana Silva', '12345678900');

-- SELECT básico
SELECT nome, cpf FROM cliente WHERE data_nascimento > '1990-01-01';

-- UPDATE
UPDATE cliente SET email = 'ana@email.com' WHERE id = 1;

-- DELETE
DELETE FROM cliente WHERE id = 1;
```

### 4.3 JOINs

```sql
-- INNER JOIN: apenas registros que possuem correspondência em ambas as tabelas
SELECT c.nome, p.data_pedido
FROM cliente c
INNER JOIN pedido p ON p.cliente_id = c.id;

-- LEFT JOIN: todos os registros da esquerda, mesmo sem correspondência (NULL na direita)
SELECT c.nome, p.id AS pedido_id
FROM cliente c
LEFT JOIN pedido p ON p.cliente_id = c.id;

-- RIGHT JOIN: todos os registros da direita (menos comum na prática)
-- FULL OUTER JOIN: união de LEFT e RIGHT (todos os registros de ambos os lados)

-- SELF JOIN
SELECT f1.nome AS funcionario, f2.nome AS gestor
FROM funcionario f1
LEFT JOIN funcionario f2 ON f1.gestor_id = f2.id;
```

### 4.4 Agregação e Agrupamento

```sql
SELECT cliente_id, COUNT(*) AS total_pedidos, SUM(valor) AS valor_total
FROM pedido
GROUP BY cliente_id
HAVING COUNT(*) > 5
ORDER BY valor_total DESC;
```

> **Diferença importante**: `WHERE` filtra **antes** do agrupamento; `HAVING` filtra **depois** do agrupamento (sobre valores agregados).

Funções de agregação: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`.

### 4.5 Subconsultas (Subqueries)

```sql
-- Subquery no WHERE
SELECT nome FROM cliente
WHERE id IN (SELECT cliente_id FROM pedido WHERE valor > 1000);

-- Subquery correlacionada
SELECT nome FROM cliente c
WHERE EXISTS (SELECT 1 FROM pedido p WHERE p.cliente_id = c.id);

-- Subquery no FROM
SELECT departamento, media_salario
FROM (
    SELECT departamento_id AS departamento, AVG(salario) AS media_salario
    FROM funcionario
    GROUP BY departamento_id
) AS resumo
WHERE media_salario > 5000;
```

### 4.6 Common Table Expressions (CTE)

```sql
WITH pedidos_altos AS (
    SELECT cliente_id, SUM(valor) AS total
    FROM pedido
    GROUP BY cliente_id
    HAVING SUM(valor) > 1000
)
SELECT c.nome, pa.total
FROM cliente c
JOIN pedidos_altos pa ON pa.cliente_id = c.id;
```

### 4.7 Window Functions (Funções de Janela)

```sql
SELECT nome, salario,
       RANK() OVER (PARTITION BY departamento_id ORDER BY salario DESC) AS ranking,
       AVG(salario) OVER (PARTITION BY departamento_id) AS media_departamento
FROM funcionario;
```

- `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()` — numeração/ranking de linhas.
- `PARTITION BY` — divide o resultado em grupos (sem colapsar linhas, diferente de `GROUP BY`).

### 4.8 Constraints (Restrições)

| Constraint | Finalidade |
|---|---|
| `PRIMARY KEY` | Identifica unicamente a linha |
| `FOREIGN KEY` | Garante integridade referencial |
| `UNIQUE` | Valor não pode se repetir |
| `NOT NULL` | Campo obrigatório |
| `CHECK` | Valida uma condição (ex: `CHECK (idade >= 18)`) |
| `DEFAULT` | Valor padrão quando não informado |

---

## 5. Transações e Controle de Concorrência

### 5.1 Comandos de Transação

```sql
BEGIN; -- ou START TRANSACTION
UPDATE conta SET saldo = saldo - 100 WHERE id = 1;
UPDATE conta SET saldo = saldo + 100 WHERE id = 2;
COMMIT; -- confirma as alterações
-- ou ROLLBACK; -- desfaz tudo desde o BEGIN
```

### 5.2 Níveis de Isolamento (do menos ao mais restritivo)

| Nível | Permite Dirty Read | Permite Non-Repeatable Read | Permite Phantom Read |
|---|:---:|:---:|:---:|
| **Read Uncommitted** | Sim | Sim | Sim |
| **Read Committed** | Não | Sim | Sim |
| **Repeatable Read** | Não | Não | Sim |
| **Serializable** | Não | Não | Não |

- **Dirty Read**: ler dado de uma transação não commitada.
- **Non-Repeatable Read**: reler o mesmo dado e obter valores diferentes (foi alterado por outra transação).
- **Phantom Read**: reexecutar uma query e obter **novas linhas** que satisfazem a condição (inseridas por outra transação).

### 5.3 Deadlock

Situação em que duas ou mais transações ficam bloqueadas esperando recursos umas das outras indefinidamente. SGBDs geralmente detectam e resolvem abortando uma das transações.

---

## 6. Índices e Performance

### 6.1 O que são índices

Estruturas (geralmente **B-Tree** ou **Hash**) que aceleram buscas, evitando *full table scan*.

```sql
CREATE INDEX idx_cliente_cpf ON cliente(cpf);
CREATE UNIQUE INDEX idx_cliente_email ON cliente(email);
```

### 6.2 Prós e contras

- **Vantagem**: acelera `SELECT` (buscas, `JOIN`, `ORDER BY`, `WHERE`).
- **Desvantagem**: cada índice tem custo de armazenamento e desacelera `INSERT`/`UPDATE`/`DELETE` (o índice precisa ser atualizado também).

### 6.3 EXPLAIN

```sql
EXPLAIN ANALYZE
SELECT * FROM pedido WHERE cliente_id = 10;
```
Mostra o plano de execução da query — útil para identificar se um índice está sendo usado (`Index Scan`) ou se está ocorrendo `Seq Scan` (varredura completa).

---

## 7. NoSQL

Bancos "Not Only SQL" — surgiram para atender necessidades de **escalabilidade horizontal**, **esquemas flexíveis** e **grandes volumes de dados**.

### 7.1 Categorias de NoSQL

| Categoria | Exemplos | Estrutura | Caso de Uso |
|---|---|---|---|
| **Chave-Valor** | Redis, DynamoDB | par chave/valor simples | Cache, sessões |
| **Documentos** | MongoDB, CouchDB | documentos JSON/BSON | Catálogos, conteúdo semi-estruturado |
| **Colunar (Wide-Column)** | Cassandra, HBase | famílias de colunas | Big Data, séries temporais |
| **Grafos** | Neo4j, ArangoDB | nós e arestas | Redes sociais, recomendação |

### 7.2 Exemplo de Documento (MongoDB)

```json
{
  "_id": "1",
  "nome": "Ana Silva",
  "enderecos": [
    { "tipo": "residencial", "cidade": "Rio de Janeiro" },
    { "tipo": "comercial", "cidade": "São Paulo" }
  ],
  "pedidos": [
    { "produto": "Notebook", "valor": 3500 }
  ]
}
```
> Diferente do relacional, o documento pode **embutir** dados relacionados (desnormalização natural), evitando JOINs.

### 7.3 Teorema CAP

Em um sistema distribuído, só é possível garantir **2 das 3** propriedades simultaneamente:

- **C**onsistency (Consistência) — todos os nós veem os mesmos dados ao mesmo tempo.
- **A**vailability (Disponibilidade) — toda requisição recebe uma resposta (sem garantir que seja a mais recente).
- **P**artition Tolerance (Tolerância a Partição) — sistema continua funcionando mesmo com falha de comunicação entre nós.

> Na prática, como partições de rede são inevitáveis em sistemas distribuídos, a escolha real é entre **CP** (ex: MongoDB, HBase) ou **AP** (ex: Cassandra, DynamoDB).

### 7.4 BASE vs ACID

| ACID (SQL) | BASE (NoSQL) |
|---|---|
| Atomicidade | **B**asically Available |
| Consistência | **S**oft state |
| Isolamento | **E**ventually consistent |
| Durabilidade | |

- **BASE**: prioriza disponibilidade, aceitando consistência eventual (os dados convergem para o estado correto após algum tempo).

---

## 8. SQL vs NoSQL

| Aspecto | SQL (Relacional) | NoSQL |
|---|---|---|
| Esquema | Rígido, definido previamente | Flexível/dinâmico |
| Escalabilidade | Vertical (principalmente) | Horizontal (sharding nativo) |
| Consistência | Forte (ACID) | Eventual (BASE), geralmente |
| Relacionamentos | Nativos via JOIN | Geralmente desnormalizados/embutidos |
| Linguagem | SQL padronizado | Varia por banco (API própria, query language específica) |
| Casos de uso | Sistemas transacionais (ERP, financeiro) | Big Data, alta escala, dados semi-estruturados |

---

## 9. Exercícios de Fixação

1. Dada uma tabela não normalizada com múltiplos telefones em uma única coluna, normalize-a até a 3FN.
2. Explique a diferença entre `WHERE` e `HAVING` com um exemplo de SQL.
3. O que é uma dependência transitiva e por que ela viola a 3FN?
4. Escreva uma query usando `LEFT JOIN` para listar todos os clientes, mesmo aqueles que não fizeram nenhum pedido.
5. Explique o Teorema CAP e diga se o MongoDB prioriza Consistência ou Disponibilidade (em configuração padrão).
6. Qual é a diferença entre os níveis de isolamento `Read Committed` e `Repeatable Read`?
7. Quando um índice pode prejudicar, em vez de ajudar, a performance de um sistema?
8. Diferencie um banco de dados chave-valor de um banco de dados orientado a documentos, com exemplos.

---

## 10. Referências

- Elmasri & Navathe. *Fundamentos de Sistemas de Banco de Dados*.
- Date, C.J. *Introdução a Sistemas de Bancos de Dados*.
- Documentação PostgreSQL: https://www.postgresql.org/docs/
- Documentação MongoDB: https://www.mongodb.com/docs/
- Martin Kleppmann. *Designing Data-Intensive Applications* (para aprofundar CAP, consistência distribuída).

---

> **Dica de estudo**: pratique escrever queries SQL manualmente (sem IDE/autocomplete) — é comum a prova pedir para identificar o resultado de uma consulta ou apontar erros de sintaxe. Para NoSQL, foque em entender **quando usar cada modelo** e o Teorema CAP, que são os pontos mais cobrados em bancas de concurso.
