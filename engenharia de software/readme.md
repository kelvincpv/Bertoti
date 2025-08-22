# Exemplo alternativo — Biblioteca (Livro/EstanteLivro)

Este exemplo refaz a estrutura da sua atividade (antes: Filme/SalaFilme) usando **Livro/EstanteLivro**.
Mantém a mesma ideia de composição (uma estante possui vários livros) e busca por atributo.

## Arquivos
- `Livro.java` — entidade com título, autor, páginas e ISBN.
- `EstanteLivro.java` — agrega `List<Livro>`, com métodos de adicionar e buscar.
- `TestarEstanteLivro.java` — executa um cenário de teste simples no `main`.

## Como compilar e executar

```bash
javac Livro.java EstanteLivro.java TestarEstanteLivro.java
java TestarEstanteLivro
```

## UML (ASCII)

+---------------------------+
|           Livro           |
+---------------------------+
| - titulo: String          |
| - autor: String           |
| - paginas: int            |
| - isbn: String            |
+---------------------------+
| + Livro(titulo:String,    |
|         autor:String,     |
|         paginas:int,      |
|         isbn:String)      |
| + get/set (cada campo)    |
| + toString(): String      |
+---------------------------+

+---------------------------+
|        EstanteLivro       |
+---------------------------+
| - nomeEstante: String     |
| - livros: List<Livro>     |
+---------------------------+
| + EstanteLivro(nome:String)|
| + addLivro(l:Livro): void |
| + getLivros(): List<Livro>|
| + buscarPorTitulo(String):|
|        List<Livro>        |
| + buscarPorAutor(String): |
|        List<Livro>        |
| + toString(): String      |
+---------------------------+

