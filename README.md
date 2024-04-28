# Preparando o Ambiente

Para iniciar vamos instalar o JDK do Java acessando o site da Oracle.

https://www.oracle.com/br/java/technologies/downloads/

Depois de instalado vamos seguir agora para nossa IDE IntelliJ Community Edition

https://www.jetbrains.com/idea/download/?section=windows#section=windows

Depois de instalado ambos os arquivos, abrindo o IntelliJ vamos criar nosso primeiro projeto e vamos ver então nossa primeira tela. Aqui ao lado esquerdo temos dentro da pasta SRC nossa pasta dos arquivos fonte, teremos um arquivo gitignore para uso do Git além da pasta .idea e um arquivo de configuração do IntelliJ com final .iml.


<aside>
💡 Para ocultar a barra de pastas do lado esquerdo podemos usar o atalho ALT + 1.

</aside>

Para executarmos nosso primeiro programa podemos clicar no botão de play na parte de cima e veremos nosso programa ser executado no console.

<aside>
💡 Para executar diretamente o programa podemos usar o atalho SHIFT+ F10

</aside>

# O que é a JVM

A JVM, Java Virtual Machine é uma maquina virtual que permite a execução de um arquivo compilado Java. Ao compilar nosso programa você vai ver uma pasta out gerada pelo sistema que contem os arquivos que serão interpretados pela JVM e serão executados por ela.

Com a JVM podemos executar um programa Java em qualquer sistema operacional, pois é a JVM que irá executar o codigo gerado pelo nosso programa.

<aside>
💡 Para usar um *`System.out.println()`* no IntelLiJ podemos usar um atalho digitando “`sout`” que a IDE irá completar com o comando.

</aside>

# Linguagem Java

## Variáveis

No Java para usarmos variáveis precisamos declarar seu tipo ou seja, para declarar uma variável iremos usar da seguinte maneira:

```java
int ano = 2020;
```

Como convenção quando usamos variáveis sempre digitaremos um identificador com letras minúsculas, e quando temos uma variável de nome composto usaremos o formato camelCase, onde cada letra da separação estará em letra maiúscula sem espaço. Exemplo:

```java
int anoDeLancamento = 2020;
boolean incluidoNoPlano = true;
double notaDoFilme = 8.1;
```

Para armazenamento de texto iremos usar o tipo String. 

```java
String sinopse;
sinopse = "Filme de aventura bem bacana";
```

## Text Blocks

No Java 15 foi implementado os text blocks onde podemos digitar uma string da maneira como queremos que ela apareça na tela. Para isso usamos 3 aspas duplas seguidas. Veja Exemplo:

```java
String sinopse;
sinopse = """ 
					Filme Top Gun
					Filme muito legal que mostra uma aventura muito bacana
					Ano de Lançamento: """ + anoDeLancamento;
System.out.println(sinopse);
```

## Comentários

Para incluir um comentário em Java usaremos os caracteres `//` `/* */` *ou `/*** */`

```java
String sinopse;
/* Bloco de Código da descrição do filme */
sinopse = """ 
					Filme Top Gun
					Filme muito legal que mostra uma aventura muito bacana
					Ano de Lançamento: """ + anoDeLancamento;
System.out.println(sinopse);
```

## Casting - Conversão de tipos

Para realizar um casting no Java podemos usar o tipo antes do dado entre parênteses. Esse método é o chamado de casting explicito. Veja exemplo:

```java
int classificacao;
double media = (8.3 + 2.5) / 2;

classificacao = (int) media / 2;
```

No modo implícito acontece quando você atribui um valor de um tipo de dado menor para um tipo de dado maior, e o Java faz a conversão automaticamente. Para essa conversão implícita temos a seguinte tabela:

![tabela](https://github.com/vitormigoto/java-studies-screenmatch/assets/56165095/50e0a20a-ffb5-45d1-a182-874ad0466433)

## Criação de nova classe

Para criarmos uma nova classe podemos clicar com o botão direito na nossa pasta src e em New > Java Class. Digite o nome da Classe e depois pode clicar em Add para adicionar essa nova classe no nosso repositório Git.

<aside>
💡 Um atalho para abrir o menu de nova classe é digitar CTRL + ALT + INSERT

</aside>

![nova classe](https://github.com/vitormigoto/java-studies-screenmatch/assets/56165095/bc180ce0-3d2c-4d9f-8e13-d6677584707f)

Ao iniciar iremos criar nosso método principal onde podemos usar o atalho ao digitar `main` e dar enter a IDE completa pra gente.

![main](https://github.com/vitormigoto/java-studies-screenmatch/assets/56165095/b8684b5c-c342-4fe0-854d-aba6da3824c8)

# Comando Condicional

O comando condicional no Java é o IF, sua sintaxe é muito próxima do usado no Javascript. Veja a sintaxe abaixo:

```java
if( condição ){
	 codigo se verdadeiro
}
else
{
	 codigo se falso
}
```

## Operadores lógicos

Os operadores lógicos são o E e o OU suas sintaxes são: `&&` e `||`

## Operadores Relacionais

Temos os operadores 
relacionais comuns em outras linguagens como o >, <, >=, <=, == e !=.

Para strings é preferencial usarmos o método equals, veja o exemplo abaixo:

```java
if (tipoPlano.equals("plux") ){
		preco = 15.99;
}
```

# Leitura de dados

Para ler nossos dados vamos utilizar um novo evento chamado Scanner, quando você inserir a palavra Scanner você irá ver que a IDE irá realizar uma importação de uma classe logo acima.

Para usar essa classe vamos ver o código abaixo:

```java
import java.util.Scanner;

public class Leitura {
    public static void main(String[] args) {
        Scanner leitura = new Scanner(System.in);

        System.out.println("Digite seu filme favorito: ");
        // Para ler uma string vamos usar o nextLine()
        String filme = leitura.nextLine();

        System.out.println("Qual o ano do lançamento:");
        // Para ler um int iremos usar o nextInt()
        int anoDeLancamento = leitura.nextInt();

        System.out.println("Diga sua avaliação para o filme: ");
        // Para ler um double iremos usar o nextDouble()
        double avaliacao = leitura.nextDouble();

        System.out.println(filme);
        System.out.println(anoDeLancamento);
        System.out.println(avaliacao);
    }
}
```

# Orientação a Objeto

**Classe** é o modelo

**Objeto** é cada um

Dentro de uma classe temos os métodos e os atributos de um objeto.

**Atributos** → São valores característicos deste objeto. Exemplo: nome, dataNascimento, RG, CPF

**Métodos** → São ações que um objeto pode executar. Exemplo: exibirDadosDaPessoa, exibirNome.

**Encapsulamento** → impede que os dados do objeto sejam alterados internamente sem usar um método. Para evitar isso usamos o modificador `private` na declaração dos atributos da classe.

**Modificador Public** → quando temos um pacote precisamos especificar os métodos e atributos que são publicas.

Normalmente quando temos uma classe os atributos são por padrão definidos como Privados e para que possamos alterar ou ler estes valores usamos os **Getters** e **Setters**

**Herança →** Quando uma classe possui atributos que são equivalentes a atributos de uma outra classe, podemos fazer com que essa classe herde os atributos de uma outra classe. Ou seja, a classe A possui 2 atributos e a classe B possui os mesmos 2 atributos da classe A porem possui mais um atributo que a classe A não tem. Para criar esse laço de herança usamos a palavra **extends.** A herança pode ser feita apenas de uma única classe.

**Polimorfismo →** Possibilidade de eu chamar uma classe por sua classe mãe ou pela sua classe direta. Por exemplo, podemos chamar o Filme pela classe Titulo ou pela classe Filme porque Filme estende de Titulo. O Java consegue identificar quando é um Filme ou quando é uma Série por exemplo.
