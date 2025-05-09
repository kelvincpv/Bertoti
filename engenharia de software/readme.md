<details>
<summary><strong>Trechos do Livro</strong></summary>
  
### Primeiro Trecho

  What precisely do we mean by software engineering? What distinguishes “software engineering” from “programming” or “computer science”? And why would Google have a unique perspective to add to the corpus of previous software engineering literature written over the past 50 years?
 
The terms “programming” and “software engineering” have been used interchangeably for quite some time in our industry, although each term has a different emphasis and different implications. University students tend to study computer science and get jobs writing code as “programmers.”
 
“Software engineering,” however, sounds more serious, as if it implies the application of some theoretical knowledge to build something real and precise. Mechanical engineers, civil engineers, aeronautical engineers, and those in other engineering disciplines all practice engineering. They all work in the real world and use the application of their theoretical knowledge to create something real. Software engineers also create “something real,” though it is less tangible than the things other engineers create.
 
Unlike those more established engineering professions, current software engineering theory or practice is not nearly as rigorous. Aeronautical engineers must follow rigid guidelines and practices, because errors in their calculations can cause real damage; programming, on the whole, has traditionally not followed such rigorous practices. But, as software becomes more integrated into our lives, we must adopt and rely on more rigorous engineering methods. We hope this book helps others see a path toward more reliable software practices.

### Segundo Trecho

Programming Over Time
We propose that “software engineering” encompasses not just the act of writing code, but all of the tools and processes an organization uses to build and maintain that code over time. What practices can a software organization introduce that will best keep its code valuable over the long term? How can engineers make a codebase more sustainable and the software engineering discipline itself more rigorous? We don’t have fundamental answers to these questions, but we hope that Google’s collective experience over the past two decades illuminates possible paths toward finding those answers.
 
One key insight we share in this book is that software engineering can be thought of as “programming integrated over time.” What practices can we introduce to our code to make it sustainable—able to react to necessary change—over its life cycle, from conception to introduction to maintenance to deprecation?
 
The book emphasizes three fundamental principles that we feel software organizations should keep in mind when designing, architecting, and writing their code:
 
Time and Change
How code will need to adapt over the length of its life
 
Scale and Growth
How an organization will need to adapt as it evolves
 
Trade-offs and Costs
How an organization makes decisions, based on the lessons of Time and Change and Scale and Growth
</details>
<details>
<summary><strong>Atividade 1</strong></summary>

### Comentário do primeiro trecho

No primeiro trecho do livro *Software Engineering at Google*, os autores falam sobre algo que muitos confundem: será que programar é o mesmo que ser engenheiro de software? Eles explicam que, apesar das palavras às vezes parecerem iguais, elas têm significados e impactos diferentes.

Quando falamos em "programar", normalmente estamos pensando em escrever código — e é isso que aprendemos nos cursos de Ciência da Computação. Já "engenharia de software" soa mais técnico, mais sério, e com razão: é como aplicar teoria e boas práticas para construir algo real e confiável, mesmo que não seja algo físico como uma ponte ou avião.

A comparação com outras engenharias é interessante. Um erro em engenharia civil ou aeronáutica pode causar acidentes graves — por isso esses campos são super rigorosos. A engenharia de software ainda não chegou nesse nível de exigência, mas precisa evoluir. Afinal, hoje em dia o software está presente em tudo. Por isso, os autores defendem que é hora de encarar a criação de software com mais seriedade e responsabilidade.

</details>

<details>
<summary><strong>Atividade 2</strong></summary>

### Comentário do segundo trecho

O segundo trecho amplia essa conversa e traz uma visão bem legal: engenharia de software não é só escrever código — é pensar no tempo, nas mudanças e em como manter o código útil por muito tempo.

Os autores propõem que a engenharia de software é como "programação integrada ao longo do tempo". Ou seja, desde a hora que o código nasce, até ele ser ajustado, mantido ou até aposentado, tudo isso faz parte do trabalho. Isso envolve processos, ferramentas, organização, decisões... tudo pra garantir que o software continue funcionando bem mesmo depois de meses ou anos.

Eles destacam três ideias principais que toda equipe deveria levar em conta:

1. **Tempo e Mudança** – O código precisa mudar com o tempo. E tudo bem, desde que ele esteja preparado pra isso.
2. **Escala e Crescimento** – À medida que a empresa cresce, o sistema também precisa acompanhar.
3. **Custos e Compensações** – Nem sempre dá pra fazer tudo. É preciso escolher bem onde investir tempo e esforço.

Esse trecho mostra como pensar além do código e começar a enxergar o software como algo vivo, que evolui. E mais: que o jeito como lidamos com ele faz toda a diferença.

</details>
<details>
<summary><strong>Atividade 3</strong></summary>

### De 3 exemplos de trade-off em softwares e explicá-los.

1. Entre otimização de desempenho e consumo de recursos: Muitas vezes é necessário fazer um trade off entre a melhoria no desempenho do programa e o aumento no consumo de recursos do sistema. Por exemplo, aumentar o número de threads em um programa pode melhorar a velocidade de processamento, mas também pode aumentar o uso de memória e CPU.

2. Entre segurança e usabilidade: Implementar medidas de segurança mais rigorosas e manter a facilidade de uso para os usuários. Por exemplo, exigir senhas complexas e autenticação de dois fatores pode aumentar a segurança de um sistema, mas também pode tornar o processo de login mais complicado para os usuários.

3. Entre rapidez no desenvolvimento e qualidade do código: Por vezes, é necessário escolher entre desenvolver um software rapidamente para atender a prazos apertados ou dedicar mais tempo para escrever um código mais limpo e de melhor qualidade. A pressa pode resultar em possíveis bugs e problemas de manutenção no futuro, enquanto a qualidade pode levar mais tempo para ser alcançada.
</details>
<details>
<summary><strong>Atividade 4</strong></summary>

### Classes UML (com exemplo)

A UML é uma forma de representar visualmente o design do sistema. O **diagrama de classes** mostra as classes, seus atributos, métodos e relacionamentos.

#### Exemplo:

Vamos modelar um sistema de vendas:

```
+----------------+           +----------------+           +----------------+
|   Produto      |           |   Cliente      |           |    Pedido      |
+----------------+           +----------------+           +----------------+
| - nome         |           | - nome         |           | - data         |
| - preco        |           | - cpf          |           | - total        |
+----------------+           +----------------+           +----------------+
| +getPreco()    |           | +comprar()     |           | +adicionar()   |
+----------------+           +----------------+           +----------------+
```

Ferramentas recomendadas: [draw.io](https://app.diagrams.net/), [Lucidchart](https://www.lucidchart.com/), StarUML, entre outras.

</details>

<details>
<summary><strong>Atividade 5</strong></summary>

### JAVA (com exemplo)

Baseando-se na UML da Atividade 4, aqui vai a implementação da classe `Produto` em Java:

```java
public class Produto {
    private String nome;
    private double preco;

    public Produto(String nome, double preco) {
        this.nome = nome;
        this.preco = preco;
    }

    public double getPreco() {
        return preco;
    }

    public String getNome() {
        return nome;
    }
}
```

#### Exemplo de uso:

```java
public class Main {
    public static void main(String[] args) {
        Produto p1 = new Produto("Martelo", 29.90);
        System.out.println("Produto: " + p1.getNome());
        System.out.println("Preço: R$ " + p1.getPreco());
    }
}
```

</details>
