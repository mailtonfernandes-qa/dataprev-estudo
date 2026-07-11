# Revisão Completa de Java — Concurso Dataprev (Desenvolvimento de Software)

> Material de estudo focado em: Orientação a Objetos, Coleções, Stream API e Spring Boot.

---

## Sumário

1. [Fundamentos da Linguagem](#1-fundamentos-da-linguagem)
2. [Orientação a Objetos (OO)](#2-orientação-a-objetos-oo)
3. [Coleções (Collections Framework)](#3-coleções-collections-framework)
4. [Stream API](#4-stream-api)
5. [Spring Boot](#5-spring-boot)
6. [Exercícios de Fixação](#6-exercícios-de-fixação)
7. [Referências](#7-referências)

---

## 1. Fundamentos da Linguagem

### 1.1 Tipos primitivos vs Wrapper Classes

| Primitivo | Wrapper     | Tamanho  |
|-----------|-------------|----------|
| `byte`    | `Byte`      | 8 bits   |
| `short`   | `Short`     | 16 bits  |
| `int`     | `Integer`   | 32 bits  |
| `long`    | `Long`      | 64 bits  |
| `float`   | `Float`     | 32 bits  |
| `double`  | `Double`    | 64 bits  |
| `char`    | `Character` | 16 bits  |
| `boolean` | `Boolean`   | 1 bit (JVM-dependente) |

- **Autoboxing/Unboxing**: conversão automática entre primitivo e wrapper.
- **Cuidado**: `Integer` cacheia valores entre -128 e 127 (`==` pode falhar fora desse intervalo).

```java
Integer a = 127, b = 127;
System.out.println(a == b); // true (cache)

Integer c = 200, d = 200;
System.out.println(c == d); // false (objetos diferentes)
```

### 1.2 Modificadores de acesso

| Modificador | Mesma classe | Mesmo pacote | Subclasse | Outro pacote |
|-------------|:---:|:---:|:---:|:---:|
| `private`   | ✔ | ✘ | ✘ | ✘ |
| (default)   | ✔ | ✔ | ✘ | ✘ |
| `protected` | ✔ | ✔ | ✔ | ✘ |
| `public`    | ✔ | ✔ | ✔ | ✔ |

### 1.3 `final`, `static`, `transient`, `volatile`

- `final`: impede reatribuição (variável), sobrescrita (método) ou herança (classe).
- `static`: pertence à classe, não à instância.
- `transient`: exclui o campo da serialização.
- `volatile`: garante visibilidade de memória entre threads (não garante atomicidade).

---

## 2. Orientação a Objetos (OO)

### 2.1 Os 4 pilares

1. **Abstração** — modelar entidades do mundo real focando no essencial.
2. **Encapsulamento** — esconder detalhes internos, expor apenas o necessário (getters/setters, `private`).
3. **Herança** — reaproveitamento de comportamento via `extends`.
4. **Polimorfismo** — mesmo método com comportamentos diferentes (sobrecarga e sobrescrita).

### 2.2 Herança vs Composição

```java
// Herança
class Animal {
    void mover() { System.out.println("Se move"); }
}
class Cachorro extends Animal { }

// Composição (preferível na maioria dos casos - "favor composition over inheritance")
class Motor {
    void ligar() { System.out.println("Motor ligado"); }
}
class Carro {
    private final Motor motor = new Motor();
    void ligar() { motor.ligar(); }
}
```

### 2.3 Polimorfismo

```java
class Forma {
    double area() { return 0; }
}
class Circulo extends Forma {
    double raio;
    Circulo(double raio) { this.raio = raio; }
    @Override
    double area() { return Math.PI * raio * raio; }
}
class Quadrado extends Forma {
    double lado;
    Quadrado(double lado) { this.lado = lado; }
    @Override
    double area() { return lado * lado; }
}

// Uso polimórfico
List<Forma> formas = List.of(new Circulo(2), new Quadrado(3));
formas.forEach(f -> System.out.println(f.area()));
```

**Sobrecarga (overload)**: mesmo nome, assinaturas diferentes (compile-time).
**Sobrescrita (override)**: mesma assinatura, comportamento redefinido em subclasse (runtime).

### 2.4 Classes Abstratas vs Interfaces

| Característica | Classe Abstrata | Interface |
|---|---|---|
| Herança múltipla | Não | Sim (múltiplas interfaces) |
| Atributos de instância | Sim | Não (apenas `static final`) |
| Métodos concretos | Sim | Sim (`default` e `static`, desde Java 8) |
| Construtor | Sim | Não |

```java
interface Pagavel {
    double calcularValor();
    default void imprimirRecibo() {
        System.out.println("Valor: " + calcularValor());
    }
}

abstract class Funcionario implements Pagavel {
    protected String nome;
    Funcionario(String nome) { this.nome = nome; }
    abstract double calcularSalario();
}
```

### 2.5 Princípios SOLID

- **S**ingle Responsibility — uma classe, uma responsabilidade.
- **O**pen/Closed — aberto para extensão, fechado para modificação.
- **L**iskov Substitution — subtipos devem ser substituíveis pelos tipos base.
- **I**nterface Segregation — interfaces específicas em vez de uma genérica.
- **D**ependency Inversion — depender de abstrações, não de implementações concretas.

### 2.6 Equals, HashCode e Comparable

```java
class Pessoa {
    String cpf;

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Pessoa)) return false;
        Pessoa pessoa = (Pessoa) o;
        return Objects.equals(cpf, pessoa.cpf);
    }

    @Override
    public int hashCode() {
        return Objects.hash(cpf);
    }
}
```

> **Regra de ouro**: se sobrescrever `equals`, sempre sobrescreva `hashCode` (contrato do `Object`).

---

## 3. Coleções (Collections Framework)

### 3.1 Hierarquia principal

```
Collection
├── List (permite duplicados, ordem de inserção)
│   ├── ArrayList   -> array dinâmico, acesso O(1), inserção/remoção no meio O(n)
│   ├── LinkedList  -> lista duplamente encadeada, boa para inserção/remoção nas pontas
│   └── Vector      -> sincronizada (legada)
├── Set (não permite duplicados)
│   ├── HashSet      -> sem ordem garantida, O(1) médio
│   ├── LinkedHashSet-> mantém ordem de inserção
│   └── TreeSet      -> ordenado (Red-Black tree), O(log n)
└── Queue / Deque
    ├── PriorityQueue -> heap, ordena por prioridade
    ├── ArrayDeque    -> pilha/fila eficiente

Map (não é Collection)
├── HashMap       -> sem ordem garantida
├── LinkedHashMap -> mantém ordem de inserção
├── TreeMap       -> ordenado por chave
└── Hashtable     -> sincronizada (legada)
```

### 3.2 Comparação rápida List

| Estrutura | Acesso | Inserção/Remoção (meio) | Thread-safe |
|---|---|---|---|
| `ArrayList` | O(1) | O(n) | Não |
| `LinkedList` | O(n) | O(1)* | Não |
| `CopyOnWriteArrayList` | O(1) | O(n) | Sim |

### 3.3 Exemplos

```java
List<String> nomes = new ArrayList<>(List.of("Ana", "Bruno", "Carlos"));
nomes.add("Diego");
nomes.remove("Bruno");

Map<String, Integer> idades = new HashMap<>();
idades.put("Ana", 30);
idades.computeIfAbsent("Bruno", k -> 25);
idades.merge("Ana", 1, Integer::sum); // incrementa idade

Set<Integer> unicos = new TreeSet<>(List.of(5, 3, 5, 1)); // [1, 3, 5]
```

### 3.4 Iterator vs for-each

```java
Iterator<String> it = nomes.iterator();
while (it.hasNext()) {
    String nome = it.next();
    if (nome.equals("Carlos")) {
        it.remove(); // seguro; remover via for-each lança ConcurrentModificationException
    }
}
```

### 3.5 Comparable vs Comparator

```java
class Produto implements Comparable<Produto> {
    String nome;
    double preco;

    @Override
    public int compareTo(Produto o) {
        return Double.compare(this.preco, o.preco);
    }
}

// Ordenação customizada com Comparator
List<Produto> produtos = new ArrayList<>();
produtos.sort(Comparator.comparing((Produto p) -> p.nome).reversed());
produtos.sort(Comparator.comparingDouble((Produto p) -> p.preco).thenComparing(p -> p.nome));
```

### 3.6 Collections utilitárias

```java
Collections.sort(nomes);
Collections.reverse(nomes);
Collections.unmodifiableList(nomes); // lista imutável
Collections.synchronizedList(nomes); // thread-safe
```

---

## 4. Stream API

### 4.1 Conceitos-chave

- **Stream**: sequência de elementos que suporta operações funcionais e pipeline.
- **Operações intermediárias** (lazy): `filter`, `map`, `sorted`, `distinct`, `limit`, `skip`.
- **Operações terminais** (eager): `collect`, `forEach`, `reduce`, `count`, `anyMatch`, `findFirst`.
- Um Stream só pode ser **consumido uma vez**.

### 4.2 Criando Streams

```java
Stream.of(1, 2, 3);
List.of(1, 2, 3).stream();
IntStream.range(1, 10);
Arrays.stream(new int[]{1, 2, 3});
```

### 4.3 Exemplos práticos

```java
List<String> nomes = List.of("Ana", "Bruno", "Carlos", "Diego", "Ana");

// filter + map + collect
List<String> maiusculas = nomes.stream()
        .filter(n -> n.length() > 3)
        .map(String::toUpperCase)
        .distinct()
        .collect(Collectors.toList());

// reduce
int somaTamanhos = nomes.stream()
        .mapToInt(String::length)
        .sum();

// groupingBy
Map<Integer, List<String>> porTamanho = nomes.stream()
        .collect(Collectors.groupingBy(String::length));

// partitioningBy
Map<Boolean, List<String>> particionado = nomes.stream()
        .collect(Collectors.partitioningBy(n -> n.length() > 4));

// joining
String csv = nomes.stream().collect(Collectors.joining(", ", "[", "]"));

// sorted + Comparator
List<String> ordenado = nomes.stream()
        .sorted(Comparator.reverseOrder())
        .toList(); // Java 16+

// anyMatch / allMatch / noneMatch
boolean temAna = nomes.stream().anyMatch(n -> n.equals("Ana"));

// Optional com findFirst
Optional<String> primeiro = nomes.stream()
        .filter(n -> n.startsWith("C"))
        .findFirst();
primeiro.ifPresentOrElse(System.out::println, () -> System.out.println("Não encontrado"));
```

### 4.4 Streams Paralelos

```java
long count = nomes.parallelStream()
        .filter(n -> n.length() > 3)
        .count();
```
> Cuidado: paralelismo tem overhead; só compensa em coleções grandes e operações CPU-bound.

### 4.5 Collectors avançados

```java
// toMap
Map<String, Integer> mapa = nomes.stream()
        .distinct()
        .collect(Collectors.toMap(n -> n, String::length));

// summarizingInt
IntSummaryStatistics stats = nomes.stream()
        .collect(Collectors.summarizingInt(String::length));
System.out.println(stats.getAverage() + " " + stats.getMax());
```

### 4.6 Interfaces Funcionais (base para Streams)

| Interface | Método abstrato | Uso |
|---|---|---|
| `Function<T,R>` | `R apply(T t)` | transformação |
| `Predicate<T>` | `boolean test(T t)` | condição |
| `Consumer<T>` | `void accept(T t)` | efeito colateral |
| `Supplier<T>` | `T get()` | fornecimento |
| `BiFunction<T,U,R>` | `R apply(T t, U u)` | transformação com 2 args |

---

## 5. Spring Boot

### 5.1 Conceitos fundamentais

- **Inversão de Controle (IoC)** e **Injeção de Dependência (DI)**: o Spring gerencia o ciclo de vida dos objetos (*beans*).
- **ApplicationContext**: container de beans.
- **Auto-configuration**: Spring Boot configura automaticamente com base nas dependências no classpath.
- **Starter Dependencies**: `spring-boot-starter-web`, `spring-boot-starter-data-jpa`, etc.

### 5.2 Anotações essenciais

| Anotação | Finalidade |
|---|---|
| `@SpringBootApplication` | Combina `@Configuration`, `@EnableAutoConfiguration`, `@ComponentScan` |
| `@RestController` | Controller que retorna JSON/XML (combina `@Controller` + `@ResponseBody`) |
| `@Service` | Camada de serviço/regra de negócio |
| `@Repository` | Camada de acesso a dados, traduz exceções JDBC |
| `@Component` | Bean genérico gerenciado pelo Spring |
| `@Autowired` | Injeção de dependência (preferir injeção via construtor) |
| `@Configuration` | Classe de configuração com `@Bean` |
| `@Bean` | Define um bean gerenciado manualmente |
| `@Value` | Injeta valor de propriedades |
| `@RequestMapping` / `@GetMapping` / `@PostMapping` | Mapeamento de rotas HTTP |
| `@PathVariable` / `@RequestParam` / `@RequestBody` | Vinculação de parâmetros da requisição |
| `@Transactional` | Gerencia transações declarativas |

### 5.3 Estrutura de um projeto típico

```
src/main/java/com/dataprev/app
├── DataprevApplication.java
├── controller/
│   └── UsuarioController.java
├── service/
│   └── UsuarioService.java
├── repository/
│   └── UsuarioRepository.java
├── model/ (ou entity/)
│   └── Usuario.java
└── dto/
    └── UsuarioDTO.java
```

### 5.4 Exemplo de API REST

```java
@SpringBootApplication
public class DataprevApplication {
    public static void main(String[] args) {
        SpringApplication.run(DataprevApplication.class, args);
    }
}

@Entity
public class Usuario {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String nome;
    private String email;
    // getters e setters
}

public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    Optional<Usuario> findByEmail(String email);
}

@Service
public class UsuarioService {
    private final UsuarioRepository repository;

    // Injeção via construtor (boa prática)
    public UsuarioService(UsuarioRepository repository) {
        this.repository = repository;
    }

    public List<Usuario> listarTodos() {
        return repository.findAll();
    }

    public Usuario salvar(Usuario usuario) {
        return repository.save(usuario);
    }
}

@RestController
@RequestMapping("/api/usuarios")
public class UsuarioController {
    private final UsuarioService service;

    public UsuarioController(UsuarioService service) {
        this.service = service;
    }

    @GetMapping
    public List<Usuario> listar() {
        return service.listarTodos();
    }

    @PostMapping
    public ResponseEntity<Usuario> criar(@RequestBody Usuario usuario) {
        Usuario salvo = service.salvar(usuario);
        return ResponseEntity.status(HttpStatus.CREATED).body(salvo);
    }

    @GetMapping("/{id}")
    public ResponseEntity<Usuario> buscarPorId(@PathVariable Long id) {
        return service.buscarPorId(id)
                .map(ResponseEntity::ok)
                .orElse(ResponseEntity.notFound().build());
    }
}
```

### 5.5 Tratamento de exceções

```java
@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(EntityNotFoundException.class)
    public ResponseEntity<String> handleNotFound(EntityNotFoundException ex) {
        return ResponseEntity.status(HttpStatus.NOT_FOUND).body(ex.getMessage());
    }

    @ExceptionHandler(MethodArgumentNotValidException.class)
    public ResponseEntity<Map<String, String>> handleValidation(MethodArgumentNotValidException ex) {
        Map<String, String> erros = new HashMap<>();
        ex.getBindingResult().getFieldErrors()
                .forEach(erro -> erros.put(erro.getField(), erro.getDefaultMessage()));
        return ResponseEntity.badRequest().body(erros);
    }
}
```

### 5.6 Validação com Bean Validation

```java
public class UsuarioDTO {
    @NotBlank(message = "Nome é obrigatório")
    private String nome;

    @Email(message = "E-mail inválido")
    private String email;
}

@PostMapping
public ResponseEntity<?> criar(@Valid @RequestBody UsuarioDTO dto) {
    // ...
}
```

### 5.7 Perfis (`application.properties` / `application.yml`)

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/dataprev
spring.datasource.username=admin
spring.datasource.password=admin
spring.jpa.hibernate.ddl-auto=update
spring.profiles.active=dev
```

- `application-dev.properties`, `application-prod.properties` — configurações por ambiente.
- `@Profile("dev")` — ativa beans conforme o perfil.

### 5.8 Testes

```java
@SpringBootTest
class UsuarioServiceTest {

    @Autowired
    private UsuarioService service;

    @MockBean
    private UsuarioRepository repository;

    @Test
    void deveListarUsuarios() {
        when(repository.findAll()).thenReturn(List.of(new Usuario()));
        List<Usuario> usuarios = service.listarTodos();
        assertFalse(usuarios.isEmpty());
    }
}
```

### 5.9 Segurança (Spring Security) — noções básicas

- `@EnableWebSecurity`, `SecurityFilterChain` (Spring Security 6+).
- Autenticação via JWT é comum em APIs REST modernas.
- `@PreAuthorize("hasRole('ADMIN')")` para controle de acesso por método.

---

## 6. Exercícios de Fixação

1. Explique a diferença entre `HashMap`, `LinkedHashMap` e `TreeMap`, indicando quando usar cada um.
2. O que acontece se você sobrescrever `equals()` sem sobrescrever `hashCode()`? Por quê isso é um problema em um `HashSet`?
3. Escreva um Stream que, a partir de uma `List<Pedido>`, agrupe por status e some o valor total de cada grupo.
4. Diferencie injeção de dependência via construtor e via campo (`@Autowired` em atributo). Qual é considerada boa prática e por quê?
5. O que é o padrão `Repository` no Spring Data JPA e como ele evita a escrita de SQL repetitivo?
6. Implemente uma classe `ContaBancaria` aplicando encapsulamento (saldo não pode ficar negativo).
7. Qual a diferença entre `List.of(...)` (imutável) e `new ArrayList<>(...)`? Quando usar cada um?
8. O que é `ConcurrentModificationException` e como evitá-la ao remover elementos durante iteração?

---

## 7. Referências

- Documentação oficial Java: https://docs.oracle.com/en/java/
- Documentação Spring Boot: https://docs.spring.io/spring-boot/
- Effective Java (Joshua Bloch)
- Baeldung (baeldung.com) — artigos práticos sobre Java e Spring

---

> **Dica de estudo**: pratique escrevendo código, não apenas leia. Para o cargo de Desenvolvimento de Software, é comum que a prova cobre também questões de lógica sobre saída de código (trace de execução), então treine "rodar o código na cabeça".
