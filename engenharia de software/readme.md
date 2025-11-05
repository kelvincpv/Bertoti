# Atividades de 1 a 8 - Engenharia de Software 💻 (versão com **Livro** e **EstanteLivro**)

## 🧩 Sobre o Projeto

Este repositório contém as atividades de 1 a 6 da disciplina de Engenharia de Software, ministrada pelo Prof. Betoti na Fatec, explorando os conceitos apresentados no livro *Software Engineering at Google* (O'Reilly) por meio de reflexões teóricas, análise de trade-offs e implementações práticas.

> **Atualização:** todos os exemplos que antes eram de *estacionamento* e *quitanda* foram substituídos por **Livro** e **EstanteLivro** (gestão de livros em uma estante/biblioteca). Mantivemos a mesma estrutura, mas com as novas classes.

---

<br>

## 🗂️ Índice

1. [Comentários sobre o Livro Software Engineering at Google, O'Reilly](#-comentários-sobre-o-livro-software-engineering-at-google-oreilly)

   * [Trecho 1: O que é Engenharia de Software?](#-trecho-1-o-que-é-engenharia-de-software)
   * [Trecho 2: Programação ao Longo do Tempo](#-trecho-2-programação-ao-longo-do-tempo)
2. [Exemplos de Trade-offs](#%EF%B8%8F-exemplos-de-trade-offs)

   * [1. Velocidade vs Qualidade](#1%EF%B8%8F⃣-velocidade-vs-qualidade)
   * [2. Escalabilidade vs Simplicidade](#2%EF%B8%8F⃣-escalabilidade-vs-simplicidade)
   * [3. Custo vs Manutenção](#3%EF%B8%8F⃣-custo-vs-manutenção)
3. [Tabela Resumo](#-tabela-resumo)
4. [Conclusão](#-conclusão)
5. [Diagramas e Classes](#-diagramas-e-estudo-de-classes)

   * [Diagrama UML para uma estante de livros](#diagrama-uml-para-uma-estante-de-livros---)
   * [Classes para uma estante de livros](#classes-para-uma-estante-de-livros---)

     * [Classe Livro](#classe-livro)
     * [Classe EstanteLivro](#classe-estantelivro)
     * [Teste JUnit](#teste-junit)
6. [Relatório de Testes](#-relatório-de-testes---surefire)
7. [Implementar um BD com SQLite](#-atividade-7--integração-com-banco-de-dados)

   * [Classe do Banco - Repositório](#classe-repositorio)
   * [Classe de gestão do Banco - Main](#classe-main)
8. [Criar interação com IA](#-atividade-8--interação-com-ia-ollama4j)

   * [Chat interativo](#classe-conversar)
   * [Gerênciamento de BD](#classe-estantelivro-ia)

---

<br>

## 📘 Comentários sobre o Livro *Software Engineering at Google*, O'Reilly

### 📖 Trecho 1: O que é Engenharia de Software?

O livro faz uma distinção clara entre “apenas programar” e **ser engenheiro de software**.

* Programar é comparado a aprender a andar de bicicleta: uma habilidade útil, mas limitada.
* Engenharia de software é como projetar uma ponte ou um avião, exigindo rigor, conhecimento teórico e responsabilidade.
* Com o software presente em tudo — de smartphones a carros autônomos —, a necessidade de **boas práticas e confiabilidade** é crítica.

> “Engenheiros clássicos seguem regras rígidas para evitar que pontes desabem; no software, precisamos do mesmo nível de rigor.”

---

### ⏳ Trecho 2: Programação ao Longo do Tempo

Desenvolver software vai além de escrever um simples *Hello World*.
Envolve a utilização de **ferramentas**, **processos** e **estratégias** para garantir a longevidade e a adaptabilidade do código. O livro destaca três pilares fundamentais:

1. **Tempo e Mudança** — como o código pode se adaptar a mudanças ao longo do tempo.
2. **Escala e Crescimento** — como gerenciar sistemas que crescem exponencialmente.
3. **Trade-offs e Custos** — como tomar decisões equilibradas considerando custos e benefícios.

💡 **Reflexão:** Engenharia de software combina técnica com estratégia, exigindo uma visão de longo prazo.

---

<br>

## ⚙️ Exemplos de Trade-offs

### 1️⃣ Velocidade vs Qualidade

**Descrição:**
Priorizar entregas rápidas pode reduzir o tempo dedicado a testes, aumentando riscos de erros. Investir em qualidade exige mais tempo inicial, mas minimiza problemas futuros.

**Exemplos práticos:**

* **MVP com frameworks ágeis** → **Ruby on Rails** ou **Django** para lançamentos rápidos.
* **Sistemas críticos** → **Java com Spring** ou **Go** para maior desempenho e segurança.
* **Dívida técnica** → Ignorar testes pode acelerar entregas, mas eleva custos de manutenção.
* Estudo: código de baixa qualidade apresenta até 15× mais defeitos.

**Cenário Real:**
Em startups de conteúdo, é comum priorizar o MVP (velocidade) e, após tração, investir em **refatoração** e **testes** para ganhar **qualidade** e **estabilidade**.

---

### 2️⃣ Escalabilidade vs Simplicidade

**Descrição:**
Soluções simples são mais rápidas de implementar, mas podem não suportar um crescimento massivo de usuários ou dados.

**Exemplos práticos:**

* **SQL (PostgreSQL, MySQL)** → Oferece consistência e robustez para sistemas menores.
* **NoSQL (MongoDB, Cassandra)** → Proporciona escalabilidade horizontal e flexibilidade.
* **Monolito** → Mais simples de desenvolver inicialmente.
* **Microsserviços** → Mais complexos, mas ideais para escalabilidade.

**Cenário Real:**
Muitos produtos começam como **monolitos** e evoluem para **microsserviços** conforme a demanda e a equipe crescem, aceitando a maior complexidade para escalar com segurança.

---

### 3️⃣ Custo vs Manutenção

**Descrição:**
Escolhas de baixo custo inicial podem resultar em altos custos de manutenção no futuro, enquanto soluções prontas podem ser mais caras, mas oferecem suporte contínuo.

**Exemplos práticos:**

* **Build vs Buy**

  * Build → Soluções open-source ou internas têm baixo custo inicial, mas demandam alta manutenção.
  * Buy → SaaS ou APIs oferecem suporte e atualizações, mas com custo recorrente.
* **Infraestrutura gerenciada vs autogerenciada**

  * Serverless/PaaS (AWS Lambda, GCP App Engine) → Menos manutenção, maior custo unitário.
  * IaaS (AWS EC2, GCP Compute Engine) → Mais controle, mas exige maior gerenciamento.

**Cenário Real:**
Migrações de infraestrutura própria para **serviços gerenciados** são comuns quando a equipe precisa focar no **core** do produto, aceitando custos previsíveis para reduzir o *overhead* operacional.

---

<br>

## 🧮 Tabela Resumo

| Trade-off                      | Exemplo Rápido                           | Consequência                                           |
| ------------------------------ | ---------------------------------------- | ------------------------------------------------------ |
| Velocidade vs Qualidade        | MVP com Rails vs Go/Java + testes        | Qualidade reduz custos de manutenção a longo prazo     |
| Escalabilidade vs Simplicidade | SQL vs NoSQL; Monolito vs Microsserviços | Complexidade permite escala, mas exige mais esforço    |
| Custo vs Manutenção            | Build (open-source) vs Buy (SaaS/API)    | Build é econômico inicialmente, mas caro a longo prazo |
| Infraestrutura                 | Serverless/PaaS vs IaaS                  | PaaS reduz manutenção, IaaS exige mais gestão          |

---

<br>

## 🏁 Conclusão

A leitura de *Software Engineering at Google* foi transformadora, destacando que a engenharia de software vai além da codificação, exigindo decisões estratégicas que equilibram trade-offs com base no contexto do projeto. A implementação do sistema de **gestão de livros** me permitiu aplicar conceitos práticos como encapsulamento, testes unitários e modelagem UML, consolidando a importância de práticas rigorosas. Os trade-offs não são barreiras, mas sim ferramentas para moldar sistemas sustentáveis e escaláveis.

📌 Mais detalhes no capítulo de trade-offs do
*Software Engineering at Google*.

---

<br>

## 🧱 Diagramas e Estudo de Classes

### Diagrama UML para uma estante de livros - ![Static Badge](https://img.shields.io/badge/Plant-UML-blue?style=plastic\&logo=UML\&logoSize=auto\&labelColor=b22222)

```
+---------------------------+
|           Livro           |
+---------------------------+
| - titulo: String          |
| - autor: String           |
| - paginas: int            |
| - isbn: String            |
+---------------------------+
| + get/set                 |
| + toString(): String      |
+---------------------------+

+-------------------------------+
|         EstanteLivro          |
+-------------------------------+
| - nomeEstante: String         |
| - livros: List<Livro>         |
+-------------------------------+
| + addLivro(Livro): void       |
| + removerPorIsbn(String):bool |
| + buscarPorTitulo(String):List|
| + buscarPorAutor(String):List |
| + getLivros(): List<Livro>    |
+-------------------------------+
```

### Classes para uma estante de livros - ![Static Badge](https://img.shields.io/badge/Java-code-brightgreen?style=plastic\&logo=Java\&logoSize=auto\&labelColor=%23FFFF00)

<br>

#### Classe Livro

**Descrição:** Representa um livro com título, autor, páginas e ISBN. Fornece getters/setters, `toString()` e sobrescreve `equals()`/`hashCode()` por **ISBN**.

```java
package fatec.gov.br.atividades.livros;

import java.util.Objects;

public class Livro {
    private String titulo;
    private String autor;
    private int paginas;
    private String isbn;

    public Livro(String titulo, String autor, int paginas, String isbn) {
        this.titulo = titulo;
        this.autor = autor;
        this.paginas = paginas;
        this.isbn = isbn;
    }

    public String getTitulo() { return titulo; }
    public void setTitulo(String titulo) { this.titulo = titulo; }

    public String getAutor() { return autor; }
    public void setAutor(String autor) { this.autor = autor; }

    public int getPaginas() { return paginas; }
    public void setPaginas(int paginas) { this.paginas = paginas; }

    public String getIsbn() { return isbn; }
    public void setIsbn(String isbn) { this.isbn = isbn; }

    @Override
    public String toString() {
        return "Livro{" +
            "titulo='" + titulo + '\'' +
            ", autor='" + autor + '\'' +
            ", paginas=" + paginas +
            ", isbn='" + isbn + '\'' +
            '}';
    }

    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Livro)) return false;
        Livro livro = (Livro) o;
        return Objects.equals(isbn, livro.isbn);
    }

    @Override
    public int hashCode() { return Objects.hash(isbn); }
}
```

#### Classe EstanteLivro

**Descrição:** Gerencia uma coleção de `Livro` com operações: adicionar, remover por ISBN, busca por título/autor e listagem. Usa `LinkedList` como no exemplo original.

```java
package fatec.gov.br.atividades.livros;

import java.util.LinkedList;
import java.util.List;
import java.util.stream.Collectors;

public class EstanteLivro {
    private String nomeEstante;
    private List<Livro> livros = new LinkedList<>();

    public EstanteLivro(String nomeEstante) {
        this.nomeEstante = nomeEstante;
    }

    public void addLivro(Livro livro) { livros.add(livro); }

    public boolean removerPorIsbn(String isbn) {
        return livros.removeIf(l -> l.getIsbn().equalsIgnoreCase(isbn));
    }

    public List<Livro> buscarPorTitulo(String titulo) {
        return livros.stream()
            .filter(l -> l.getTitulo().equalsIgnoreCase(titulo))
            .collect(Collectors.toList());
    }

    public List<Livro> buscarPorAutor(String autor) {
        return livros.stream()
            .filter(l -> l.getAutor().equalsIgnoreCase(autor))
            .collect(Collectors.toList());
    }

    public List<Livro> getLivros() { return livros; }

    @Override
    public String toString() {
        return "EstanteLivro{" +
            "nomeEstante='" + nomeEstante + '\'' +
            ", livros=" + livros +
            '}';
    }
}
```

#### Teste JUnit

Testes unitários que validam adição, remoção e busca em `EstanteLivro`.

```java
package fatec.gov.br.atividades.livros;

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class Teste_EstanteLivro {

    @Test
    void testAdicionarLivro() {
        EstanteLivro est = new EstanteLivro("Clássicos");
        est.addLivro(new Livro("Dom Casmurro", "Machado de Assis", 288, "978-85-359-0277-8"));
        assertEquals(1, est.getLivros().size());
    }

    @Test
    void testRemoverPorIsbn() {
        EstanteLivro est = new EstanteLivro("Clássicos");
        est.addLivro(new Livro("O Hobbit", "J. R. R. Tolkien", 320, "978-85-98078-15-2"));
        boolean removido = est.removerPorIsbn("978-85-98078-15-2");
        assertTrue(removido);
        assertEquals(0, est.getLivros().size());
    }

    @Test
    void testBuscarPorAutor() {
        EstanteLivro est = new EstanteLivro("Clássicos");
        Livro l = new Livro("Quincas Borba", "Machado de Assis", 240, "978-85-359-0278-5");
        est.addLivro(l);
        assertEquals(1, est.buscarPorAutor("Machado de Assis").size());
    }
}
```

<br>

---

## 📋 Relatório de Testes - Surefire

📊 Exemplo de relatório pode ser gerado com Maven Surefire (ou JUnit Platform). Inclua o HTML exportado aqui, se desejar, após executar a suíte de testes.

---

<br>

## 🧠 Atividade 7 – Integração com Banco de Dados

Implementar um banco de dados (BD) usando **SQLite** para o domínio **Livros**.

### Classe Repositório

**Descrição:** Responsável por toda a interação com o banco SQLite via JDBC. Cria a tabela quando necessário e fornece operações CRUD (inserir, buscar, remover, listar). Define **UNIQUE** em `isbn`.

```java
package fatec.gov.br.atividades.livros;

import java.sql.*;
import java.util.ArrayList;
import java.util.List;

public class Repositorio {
    public static final String URL = "jdbc:sqlite:livros.db";

    static {
        try {
            Class.forName("org.sqlite.JDBC");
        } catch (ClassNotFoundException e) {
            System.err.println("Driver SQLite não encontrado: " + e.getMessage());
        }
    }

    private Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL);
    }

    public void criarTabelaLivro() throws SQLException {
        String sql = "CREATE TABLE IF NOT EXISTS livro (" +
                     "id INTEGER PRIMARY KEY AUTOINCREMENT," +
                     "titulo TEXT NOT NULL," +
                     "autor TEXT NOT NULL," +
                     "paginas INTEGER NOT NULL," +
                     "isbn TEXT NOT NULL UNIQUE" +
                     ");";
        try (Connection conn = getConnection(); Statement stmt = conn.createStatement()) {
            stmt.execute(sql);
        }
    }

    public void inserirLivro(Livro livro) throws SQLException {
        String sql = "INSERT INTO livro(titulo, autor, paginas, isbn) VALUES (?, ?, ?, ?)";
        try (Connection conn = getConnection(); PreparedStatement ps = conn.prepareStatement(sql)) {
            ps.setString(1, livro.getTitulo());
            ps.setString(2, livro.getAutor());
            ps.setInt(3, livro.getPaginas());
            ps.setString(4, livro.getIsbn());
            ps.executeUpdate();
        } catch (SQLException e) {
            if (e.getErrorCode() == 19 && e.getMessage().contains("UNIQUE constraint failed")) {
                throw new SQLException("Já existe um livro com o ISBN " + livro.getIsbn(), e);
            }
            throw e;
        }
    }

    public Livro buscarPorIsbn(String isbn) throws SQLException {
        String sql = "SELECT * FROM livro WHERE isbn = ? COLLATE NOCASE";
        try (Connection conn = getConnection(); PreparedStatement ps = conn.prepareStatement(sql)) {
            ps.setString(1, isbn);
            try (ResultSet rs = ps.executeQuery()) {
                if (rs.next()) {
                    return new Livro(
                        rs.getString("titulo"),
                        rs.getString("autor"),
                        rs.getInt("paginas"),
                        rs.getString("isbn")
                    );
                }
                return null;
            }
        }
    }

    public boolean removerPorIsbn(String isbn) throws SQLException {
        String sql = "DELETE FROM livro WHERE isbn = ? COLLATE NOCASE";
        try (Connection conn = getConnection(); PreparedStatement ps = conn.prepareStatement(sql)) {
            ps.setString(1, isbn);
            return ps.executeUpdate() > 0;
        }
    }

    public List<Livro> listarLivros() throws SQLException {
        List<Livro> livros = new ArrayList<>();
        String sql = "SELECT * FROM livro";
        try (Connection conn = getConnection(); PreparedStatement ps = conn.prepareStatement(sql); ResultSet rs = ps.executeQuery()) {
            while (rs.next()) {
                livros.add(new Livro(
                    rs.getString("titulo"),
                    rs.getString("autor"),
                    rs.getInt("paginas"),
                    rs.getString("isbn")
                ));
            }
        }
        return livros;
    }
}
```

<br>

### Classe Main

**Descrição:** Interface de linha de comando (menu) para o usuário interagir com o sistema. Operações: adicionar, buscar por ISBN, remover por ISBN, listar e sair.

```java
package fatec.gov.br.atividades.livros;

import java.util.List;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Repositorio repositorio = new Repositorio();
        EstanteLivro estante = new EstanteLivro("Principal");
        Scanner scanner = new Scanner(System.in);

        try {
            repositorio.criarTabelaLivro();
            System.out.println("Banco de dados inicializado.");
        } catch (Exception e) {
            System.err.println("Erro ao inicializar o banco: " + e.getMessage());
            return;
        }

        while (true) {
            System.out.println("
=== Sistema de Gerenciamento de Livros ===");
            System.out.println("1. Adicionar livro");
            System.out.println("2. Buscar livro por ISBN");
            System.out.println("3. Remover livro por ISBN");
            System.out.println("4. Listar todos os livros");
            System.out.println("5. Sair");
            System.out.print("Escolha uma opção: ");

            int opcao;
            try { opcao = Integer.parseInt(scanner.nextLine()); }
            catch (NumberFormatException e) { System.out.println("Opção inválida."); continue; }

            switch (opcao) {
                case 1:
                    try {
                        System.out.print("Título: ");
                        String titulo = scanner.nextLine();
                        System.out.print("Autor: ");
                        String autor = scanner.nextLine();
                        System.out.print("Páginas: ");
                        int paginas = Integer.parseInt(scanner.nextLine());
                        System.out.print("ISBN: ");
                        String isbn = scanner.nextLine();

                        Livro livro = new Livro(titulo, autor, paginas, isbn);
                        repositorio.inserirLivro(livro);
                        estante.addLivro(livro);
                        System.out.println("Livro adicionado: " + livro);
                    } catch (Exception e) {
                        System.out.println("Erro ao adicionar livro: " + e.getMessage());
                    }
                    break;

                case 2:
                    try {
                        System.out.print("ISBN para busca: ");
                        String isbnBusca = scanner.nextLine();
                        Livro l = repositorio.buscarPorIsbn(isbnBusca);
                        System.out.println(l != null ? "Encontrado: " + l : "Não encontrado.");
                    } catch (Exception e) {
                        System.out.println("Erro na busca: " + e.getMessage());
                    }
                    break;

                case 3:
                    try {
                        System.out.print("ISBN para remover: ");
                        String isbnRemover = scanner.nextLine();
                        boolean removidoBD = repositorio.removerPorIsbn(isbnRemover);
                        boolean removidoMem = estante.removerPorIsbn(isbnRemover);
                        System.out.println(removidoBD || removidoMem ? "Livro removido." : "Livro não encontrado.");
                    } catch (Exception e) {
                        System.out.println("Erro ao remover: " + e.getMessage());
                    }
                    break;

                case 4:
                    try {
                        List<Livro> livros = repositorio.listarLivros();
                        if (livros.isEmpty()) System.out.println("Nenhum livro cadastrado.");
                        else livros.forEach(System.out::println);
                    } catch (Exception e) {
                        System.out.println("Erro ao listar: " + e.getMessage());
                    }
                    break;

                case 5:
                    System.out.println("Saindo...");
                    scanner.close();
                    return;

                default:
                    System.out.println("Opção inválida.");
            }
        }
    }
}
```

<br>

---

<br>

## 🤖 Atividade 8 – Interação com IA (Ollama4J)

Criar uma classe usando Ollama4J com um modelo de IA e implementar interação com o usuário para **gerenciar livros**.

### Package iachat

Este exercício usa o Banco de dados do *Package Livros*.

<br>

#### Classe Conversar

**Descrição:** Cliente simples de chat que conecta-se ao servidor Ollama local (modelo à escolha) e permite perguntas gerais.

```java
package fatec.gov.br.atividades.iachat;

import io.github.ollama4j.Ollama;
import io.github.ollama4j.models.chat.OllamaChatMessageRole;
import io.github.ollama4j.models.chat.OllamaChatRequest;
import io.github.ollama4j.models.chat.OllamaChatRequestBuilder;
import io.github.ollama4j.models.chat.OllamaChatResult;
import java.util.Scanner;

public class Conversar {
    public static void main(String[] args) {
        final String OLLAMA_URL = "http://localhost:11434";
        final String MODEL_NAME = "qwen3:8b";
        System.out.println("🔹 Iniciando cliente de IA com o modelo '" + MODEL_NAME + "' ...");
        try {
            Ollama ollama = new Ollama(OLLAMA_URL);
            ollama.pullModel(MODEL_NAME);
            OllamaChatRequestBuilder builder = OllamaChatRequestBuilder.builder().withModel(MODEL_NAME);
            builder.withMessage(OllamaChatMessageRole.SYSTEM, "Você é um especialista em assuntos gerais. Seja claro e objetivo.");
            try (Scanner scanner = new Scanner(System.in)) {
                System.out.println("
💬 Pergunte qualquer coisa para a IA (ou digite 'sair')
");
                while (true) {
                    System.out.print("	⊂(◉‿◉)つ -> ");
                    String input = scanner.nextLine().trim();
                    if (input.equalsIgnoreCase("sair")) { System.out.println("
	(ʘ‿ʘ)╯ Até logo!"); break; }
                    builder.withMessage(OllamaChatMessageRole.USER, input);
                    OllamaChatRequest request = builder.build();
                    try {
                        OllamaChatResult chatResult = ollama.chat(request, null);
                        String resposta = chatResult.getResponseModel().getMessage().getResponse();
                        System.out.println("
🤖 IA: " + resposta + "
---");
                        builder.withMessage(OllamaChatMessageRole.ASSISTANT, resposta);
                    } catch (Exception e) {
                        System.err.println("⚠️ Erro ao comunicar com o modelo: " + e.getMessage());
                    }
                }
            }
        } catch (Exception e) {
            System.err.println("❌ Erro ao iniciar o cliente Ollama: " + e.getMessage());
        }
    }
}
```

<br>

#### Classe EstanteLivro IA

**Descrição:** Integra a IA (via Ollama4J) com o backend de **Livros**. O `SYSTEM_PROMPT` exige resposta **JSON** com ações (`add`/`remove`/`list`/`help`/`none`). Filtros por `titulo`, `autor`, `isbn` ou `paginas`.

```java
package fatec.gov.br.atividades.iachat;

import com.google.gson.*;
import fatec.gov.br.atividades.livros.*;
import io.github.ollama4j.Ollama;
import io.github.ollama4j.models.chat.*;
import java.text.Normalizer;
import java.util.*;
import java.util.regex.*;

public class EstanteLivroIA {
    private static List<Livro> ultimaListaExibida = new ArrayList<>();
    private static final String MODEL = "llama3:8b";
    private static final String OLLAMA_URL = "http://localhost:11434/";

    private static final String SYSTEM_PROMPT = """
    Sua função é traduzir comandos do usuário para JSON específico de gestão de livros.
    Responda **somente** com JSON válido: {"action": "add|remove|list|help|none", "params": {..}, "message": "..."}.

    Regras:
    - add: requer titulo, autor, paginas, isbn. Dispare apenas se o usuário usar verbos como adicionar/cadastrar/inserir.
    - remove: aceita isbn ou indice (da última listagem). Dispare com verbos remover/excluir/deletar.
    - list: pode ter filtro por titulo/autor/isbn/paginas.
    - help: quando o usuário pedir ajuda.
    - none: quando não entender.

    Exemplos:
    Input: "adicionar 'Dom Casmurro' autor=Machado paginas=288 isbn=978-..."
    -> {"action":"add","params":{"titulo":"Dom Casmurro","autor":"Machado","paginas":288,"isbn":"978-..."},"message":"Livro adicionado!"}

    Input: "remover isbn 978-..."
    -> {"action":"remove","params":{"isbn":"978-..."},"message":"Removendo livro com ISBN 978-..."}

    Input: "listar por autor Machado de Assis"
    -> {"action":"list","params":{"tipoFiltro":"autor","filtro":"Machado de Assis"},"message":"Listando por autor."}
    """;

    public static void main(String[] args) {
        try {
            Ollama ollama = new Ollama(OLLAMA_URL);
            ollama.pullModel(MODEL);
            OllamaChatRequestBuilder builder = OllamaChatRequestBuilder.builder().withModel(MODEL);

            Repositorio repositorio = new Repositorio();
            EstanteLivro estante = new EstanteLivro("Principal");
            repositorio.criarTabelaLivro();

            Scanner scanner = new Scanner(System.in);
            List<OllamaChatMessage> chatHistory = new ArrayList<>();
            chatHistory.add(new OllamaChatMessage(OllamaChatMessageRole.SYSTEM, SYSTEM_PROMPT));

            System.out.println("Gerencie sua estante com IA (digite 'sair' para encerrar):
");
            while (true) {
                System.out.print("	 ⊂(◉‿◉)つ -> ");
                String input = scanner.nextLine();
                if (input.equalsIgnoreCase("sair")) break;

                OllamaChatRequest request = builder.withMessages(chatHistory)
                    .withMessage(OllamaChatMessageRole.USER, input)
                    .build();

                try {
                    OllamaChatResult chatResult = ollama.chat(request, null);
                    String iaResponse = chatResult.getResponseModel().getMessage().getResponse().trim();
                    System.out.println("Resposta bruta da IA: " + iaResponse);

                    try {
                        Gson gson = new GsonBuilder().setLenient().create();
                        JsonObject json = gson.fromJson(iaResponse, JsonObject.class);
                        String action = json.get("action").getAsString();
                        JsonObject params = json.get("params").getAsJsonObject();
                        String message = json.get("message").getAsString();

                        String result = executeAction(repositorio, estante, action, params, input);
                        if (!result.isBlank()) System.out.println(result);
                        System.out.println("	 IA: " + message);
                    } catch (JsonParseException e) {
                        System.out.println("	 IA: Resposta inválida: " + iaResponse);
                    }
                } catch (Exception e) {
                    System.out.println("	 IA: Erro ao processar: " + e.getMessage());
                }
            }
            System.out.println("
Sessão encerrada. Até mais!");
            scanner.close();
        } catch (Exception e) {
            System.err.println("Erro: " + e.getMessage());
        }
    }

    private static String executeAction(Repositorio repo, EstanteLivro estante, String action, JsonObject params, String input) {
        try {
            switch (action) {
                case "add": {
                    String titulo = params.get("titulo").getAsString();
                    String autor = params.get("autor").getAsString();
                    int paginas = params.get("paginas").getAsInt();
                    String isbn = params.get("isbn").getAsString();
                    Livro novo = new Livro(titulo, autor, paginas, isbn);
                    repo.inserirLivro(novo);
                    estante.addLivro(novo);
                    return "Livro adicionado: " + novo;
                }
                case "remove": {
                    String isbn = null;
                    if (params.has("indice")) {
                        int idx = params.get("indice").getAsInt() - 1;
                        if (idx >= 0 && idx < ultimaListaExibida.size()) {
                            isbn = ultimaListaExibida.get(idx).getIsbn();
                        } else return "Índice inválido.";
                    } else if (params.has("isbn")) {
                        isbn = params.get("isbn").getAsString();
                    } else {
                        Matcher m = Pattern.compile("isbn\s*=?\s*([\w-]+)").matcher(input.toLowerCase());
                        if (m.find()) isbn = m.group(1);
                    }
                    if (isbn != null) {
                        boolean okBD = repo.removerPorIsbn(isbn);
                        boolean okMEM = estante.removerPorIsbn(isbn);
                        return okBD || okMEM ? "Livro removido." : "Livro não encontrado.";
                    }
                    return "ISBN ou índice não fornecido.";
                }
                case "list": {
                    String tipoFiltro = params.has("tipoFiltro") ? params.get("tipoFiltro").getAsString() : null;
                    String filtro = params.has("filtro") ? normalize(params.get("filtro").getAsString()) : null;
                    List<Livro> todos = repo.listarLivros();
                    List<Livro> filtrados = new ArrayList<>(todos);
                    if (tipoFiltro != null && filtro != null && !filtro.isBlank()) {
                        filtrados = filtrar(filtrados, tipoFiltro, filtro);
                    }
                    ultimaListaExibida = new ArrayList<>(filtrados);
                    if (filtrados.isEmpty()) return "Nenhum livro encontrado.";
                    StringBuilder sb = new StringBuilder("Lista de livros:
");
                    for (int i = 0; i < filtrados.size(); i++) {
                        sb.append(i + 1).append(": ").append(filtrados.get(i)).append("
");
                    }
                    return sb.toString();
                }
                case "help":
                    return "Comandos: adicionar (titulo, autor, paginas, isbn) | remover (isbn|indice) | listar [filtros: titulo, autor, isbn, paginas]";
                case "none":
                default:
                    return "Comando não reconhecido. Peça 'ajuda'.";
            }
        } catch (Exception e) {
            return "Erro: " + e.getMessage();
        }
    }

    private static List<Livro> filtrar(List<Livro> base, String campo, String filtro) {
        String f = normalize(filtro);
        switch (campo.toLowerCase()) {
            case "titulo":
                return base.stream().filter(l -> normalize(l.getTitulo()).contains(f)).toList();
            case "autor":
                return base.stream().filter(l -> normalize(l.getAutor()).contains(f)).toList();
            case "isbn":
                return base.stream().filter(l -> normalize(l.getIsbn()).contains(f)).toList();
            case "paginas":
                return base.stream().filter(l -> String.valueOf(l.getPaginas()).contains(f)).toList();
            default:
                return base;
        }
    }

    private static String normalize(String s) {
        String n = Normalizer.normalize(s, Normalizer.Form.NFD);
        return n.replaceAll("\p{InCombiningDiacriticalMarks}+", "").toLowerCase().trim();
    }
}
```

<br>

---

## 🧾 Considerações Finais

Este conjunto de atividades representa a aplicação prática de conceitos de **Engenharia de Software**, agora com o domínio de **Livros/Estante**. A estrutura segue os mesmos tópicos do primeiro material (trade-offs, UML, testes, BD e IA), apenas substituindo os exemplos. Caso queira, posso disponibilizar também versões com **JUnit 5**, **Streams/Collectors** em todas as operações e um **README** bilíngue (PT/EN).
