# Saída de dados pelo Console/Output

&nbsp; Saída de dados ou output é utilizado quando o desenvolvedor precisa retornar um valor na tela, neste caso no console. Para utilizar o console no C# primeiro é necessário criar uma aplicação do tipo console e executar um comando que irá printar o valor. Os comandos de print no C# serão executados atrávez da <i>classe</i> Console que está dentro do <i>namespace</i> System, que por sua vez já é importado por padrão em qualquer aplicação DotNet. <br>

- #### Observação: Classes e Namespaces são tópicos abordados na seção de Programação Orientada a Objetos.

&nbsp; Existem dois comandos comumente utilizados para printar algo no console em C#.

    * Console.Write("") => Printa o valor em uma linha do console. (Não quebra a linha)
    * Console.WriteLine("") => Printa o valor em uma linha do console e gera uma quebra de linha no final.


&nbsp; É possível printar strings, variáveis, números, etc.

## Exemplos:

```csharp
    int age = 24;
    string name = "Yan";

    Console.WriteLine(name);
    Console.WriteLine(age);
    Console.Write("Hello ");
    Console.Write("World!"); 

    /* ---- Output -----
        Yan
        24
        Hello World!
    */
```

## Formatando strings 

&nbsp; Outra prática muito utilizada junto aos comandos de output do Console é a formatação de strings. Por vezes o programador pode encontrar-se con situações que vários valores devem ser apresentados no Console em somente uma linha. Uma solução simples para este problema seria utilizar técnicas como Formatação/Concatenação ou Interpolação. <br>

### Exemplo: Formatação com placeholder

```csharp
    int age = 24;
    string name = "Yan";

    Console.WriteLine("Meu nome é {0} e minha idade é {1} anos.", name, age);

    /* ---- Output -----
        Meu nome é Yan e minha idade é 24 anos.
    */
```

&nbsp; Para realizar a formatação com placeholders é utilizado dentro da string o padrão de chaves com o número do placeholder. Após fechar a string deve-se informar os valores que serão preenchidos em cada placeholder separados por vírgula e na ordem que os placeholders foram utilizados.

### Exemplo: Interpolação

```csharp
    int age = 24;
    string name = "Yan";

    Console.WriteLine($"Meu nome é {name} e minha idade é {age} anos.");

    /* ---- Output -----
        Meu nome é Yan e minha idade é 24 anos.
    */
```


&nbsp; A Interpolação surge como uma alternativa simplista ao placeholder. Neste caso é necessário apenas utilizar o sinal $ antes da abertura da string e para informar uma variável a ser interpolada coloca-se a mesma dentro de chaves.


### Exemplo: Concatenação de strings

```csharp
    int age = 24;
    string name = "Yan";

    Console.WriteLine("Meu nome é " + name + " e minha idade é " + age  + " anos.");

    /* ---- Output -----
        Meu nome é Yan e minha idade é 24 anos.
    */
```

&nbsp; Na programação em geral é possível utilizar o sinal de adição para juntar duas ou mais strings. Está junção de strings é chamada concatenação.<br>
