# Java Bandtec

## Sumário
- [Estrutura básica](#estrutura-básica)
- [Método Main](#método-main)
- [Tipos](#tipos)
- [Operadores](#operadores)
- [Exibição (print)](#exibição)
- [Input](#input)
- [Estrutura Condicional](#estrutura-condicional)
- [Estrutura de Repetição](#estrutura-de-repetição)
- [Valores Randomicos](#valores-randomicos)
- [Orientação a Objetos](#orientação-a-objetos)
    - [Classes e Objetos](#classes-e-objetos)

## Estrutura básica

Um arquivo java deve começar com a primeira letra maiúscula e ter a extensão **.java**.

Exemplo:

> App.java

Todo arquivo **.java** contêm uma classe principal, e essa classe deve ser nomeada de acordo com o nome do arquivo.

~~~java
class App {
    // conteúdo da classe
}
~~~~

### Método main
Para tornar um arquivo **.java** executável, é necessário criar um método **main** dentro da classe principal.

~~~java
public static void main(String[] args) {
    // bloco de código
}
~~~

Sendo assim, a estrutura básica de um arquivo java (executável) é a seguinte:

~~~java
class App {
    public static void main(String[] args) {
        // bloco de código
    }
}
~~~

## Tipos

Os tipos primitivos do java são extremamente simples, nem mesmo aceitam o valor **null**. Portanto, as classes Wraper são mais utilizadas, pois as mesmas aceitam o valor **null** e possuem métodos úteis de conversão.

Tipos primitivos:
- int
- double
- boolean
- char

Classes Wrapper:
- Integer
  ~~~java
  Integer age = 20;
  ~~~
- Double
  ~~~java
  Double height = 1.68;
  ~~~~ 
- Boolean
  ~~~java
  Boolean isHappy = true;
  ~~~
- String
  ~~~java
  String nome = "Lucas";
  ~~~~ 
  
## Operadores

Operadores aritméticos

~~~java
2 + 3;   // Adição
2 - 3;   // Subtração
2 * 3;   // Multiplicação
2 / 3;   // Divisão
2 % 3;   // Resto da divisão
~~~

Operadores Unários

~~~java
i++;    // Incremento
i--;    // Decremento
!true;  // Opedador de complemento lógico, inverte o valor de um boleano
~~~

Operadores Relacionais
~~~java
1 == 1;  // Igualdade
1 != 1;  // Diferente
1 > 1;   // Maior que
1 >= 1;  // Maior ou igual à
1 < 1;   // Menor que
1 <= 1;  // Menor ou igual à
~~~

> Nota: ao comparar Strings, o operador **==** se mostra ineficiente. Por isso, é recomendado o uso do método **equals()** para relacionar **Strings**.

~~~java
String txt1 = "string 1";
String txt2 = "string 2";
String txt3 = "string 1";

txt1.equals(txt2); // retorna false
txt1.equals(txt3); // retorna true
~~~

Operadores condicionais
~~~java
true && false;   // e (and)
true || false;   // ou (or)
true ? "do it" : "do that";  // Operador ternário
~~~

## Exibição

Hello World
~~~java
System.out.println("Hello World");
~~~

Interpolação
~~~java
String txt = "Olá %s, você tem %d anos";
txt = String.format(txt, name, age);
System.out.println(txt);
~~~

Output:
> Olá Lucas, você tem 20 anos

Para repetir uma string uma determinada quantidade de vezes, pode ser usado o método **repeat()**.

~~~java
    String txt = "=";
    
    txt.repeat(10);      // return: "=========="
~~~

Para arredondar um valor Double, existem métodos da clase Math:

~~~java
    Double pi = 3.14;
    
    Math.ceil(pi);      // return 4.0
    Math.floor(pi)      // return 3.0
    Math.round(pi);     // return 3.0
~~~

## Input

Para realizar inputs, é necessária a importação da biblioteca Scanner:

~~~java
import java.util.Scanner;
~~~

> A importação deve acontecer fora da classe principal.

O uso do Scanner é muito simples, basta instanciar a classe e usar seus métodos de acordo com o tipo do dado desejado.

~~~java
Scanner sc = new Scanner(System.in);    // Instanciando a classe Scanner

String name = sc.nextLine();            // Capturando input do tipo String
Integer age = sc.nextInt();             // Capturando input do tipo Integer
Double age = sc.nextDouble();           // Capturando input do tipo Double

sc.close();                             // Fechando instancia do Scanner
~~~

> Diferente da importação, o uso do Scanner deve ocorrer dentro do método main, ou seja, dentro da classe principal.

## Estrutura condicional

A estrutura condicional tem a seguinte sintaxe

~~~java
    Boolean condition = true;
    
    if (condition) {
        // if block;
    } else {
        // else block;
    }
~~~

## Estrutura de Repetição

Sintaxe **for**:

~~~java
    for (int i = 0; i <= 10; i++) {
        // block code
    }
~~~

Sintaxe **while**:

~~~java
    Boolean condition = false;
    
    while(condition) {
        // block code
    }
~~~

Sintaxe **do while**:

~~~java
    do {
        // block code
    } while (condition);
~~~

## Switch case

~~~java
    int day = 4;
    
    switch (day) {
        case 6:
            System.out.println("Today is Saturday");
            break;
        case 7:
            System.out.println("Today is Sunday");
            break;
        default:
            System.out.println("Looking forward to the Weekend");
    }
~~~

## Valores Randomicos

Gerando valor pseudoaleatório entre 0 e 1.

~~~java
    Math.random(); 
~~~

Classe random:

~~~java
    import java.util.Random;
~~~

Gerando números inteiros
~~~java
    Random rand = new Random();
    rand.nextInt(10)      // retorna número inteiro entre 0 e 9
~~~

Para gerar valores entre um determinado intervalo, pode-se usar a método **ThreadLocalRandom()**

~~~java
    import  java.util.concurrent.ThreadLocalRandom;
~~~

Retornando valor inteiro entre 0 e 9:
~~~java
    ThreadLocalRandom.current().nextInt(0, 10); 
~~~

## Fatorial
~~~java
    // input
    Scanner sc = new Scanner(System.in);

    System.out.println("Digite um número: ");
    Integer number = sc.nextInt();
    Integer factory = number;
    // sc.close();
    System.out.println("-".repeat(20));

    // calculo
    for (Integer i = number - 1; i >= 1; i--) {
        factory *= i;
    }

    // exibição
    String txt = "%d! = %d";
    txt = String.format(txt, number, factory);
    System.out.println(txt);
~~~

## Orientação a Objetos

### Classes e Objetos
Uma classe é um elemento que define quais atributos e métodos um objeto deve conter.

Exemplo de classe:

~~~java
    class Person {
        // attributes
        String name = "John";
        Integer age = 21;
        
        // methods
        void Greetings() {
            System.out.println("Hi, my name is " + this.name + " and I'm " + this.age);
        }
    }
~~~

Já um objeto (ou instância) é a implementação de uma classe, contendo seus atributos e métodos. 

Em java, um objeto pode ser instanciado através do operador **new** e armazenado em uma variável, seguindo a notação:

> TipoClasse varName = new TipoClasse();

Exemplo de objeto:

~~~java
    // instancing a Person object
    Person p1 = new Person();
~~~

Depois de instânciado, os atribudos/métodos podem ser acessados ou modificados através do operador de acesso. 

> object.attribute;
> object.method();

~~~java
    System.out.println(p1.name);    // prints: "John"
    System.out.println(p1.age);     // prints: 21
    p1.greetings();                 // prints: "Hi, my name is John and I'm 21"
~~~

Vários objetos podem ser criados a partir de uma mesma classe e podem conter estados (valores) diferentes de suas instâncias "irmãs". 

~~~java 
    Person p1 = new Person();
    Person p2 = new Person();
    
    // modifying p2.name 
    p2.name = "Yoko";
    
    System.out.println(p1.name);    // prints: "John"
    System.out.println(p2.name);    // prints: "Yoko"
~~~
