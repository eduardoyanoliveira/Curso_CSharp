# Estruturas condicionais

&nbsp; Os artigos anterios demonstram como operadores de comparação e operadores lógicos podem serem utilizados para determinar se hipóteses (testes lógicos) são verdairo ou falso. Entretanto, na maioria das ocasiões tais operadores são utlizados para impor determinada condição ao código do tipo "Se for verdade faça isso, senão faça aquilo. <br>

## Sintaxe

&nbsp; Em c#, tal como na programação em geral,  para criar uma condicional deve-se utilizar o operador <i>if</i>, que receberá por parênteses o teste lógico.

### Exemplo:

&nbsp; O programa abaixo apenas printará no console a mensagem "Olá" caso o teste lógico for verdadeiro.

```csharp
    if(10 > 2){
        Console.WriteLine("Olá");
    };

    // Output: Olá
```

&nbsp; Nota-se que após os parênteses do teste lógico apresenta-se um par de chaves com um trecho de código. Este par de chavez é responsável por delimitar o código que apenas será executado caso a condicional for verdadeira. O par de chavez juntamente ao código é chamado <i>escopo</i>

## if else

&nbsp; Por vezes também é desejando que algum código sejá executado cada a condicional falhe. Para realizar tal porcesso coloca-se a estrutura else no final da condicional e este por sua vez não pode receber teste lógico. (Mesmo que trate-se de um encadeamento de if's a estrutura else deve ser colocada no final).

### Exemplo

&nbsp; O programa abaixo apenas printará no console a mensagem "Verdadeiro" caso o teste lógico for verdadeiro e "Falso" caso o teste lógico for falso.


```csharp
    if(1 > 2){
        Console.WriteLine("Verdadeiro");
    }else{
        Console.WriteLine("Falso");
    };

    // Output: Falso
```

## else if

&nbsp; Também é possível criar um encadeamento de testes lógicos com escopos diferentes de acordo com cada resultado.Para realizá-lo utiliza-se  a estrutura else if recebendo um teste lógico.(O else if pode ser encadiado por quantas vezes for necessário).

### Exemplo:

&nbsp; O programa abaixo se comportará da seguinte forma:

    * Caso o valor de "x" for menor ou igual a 10 printará "Número de valor pequeno".
    * Caso o valor de "x" for maior que 10 e menor ou igual a 100 printará "Número de valor médio".
    * Caso nenhum dos testes acima forem verdadeiros o programa printará "Número de valor grande".

```csharp
    Console.WriteLine("Digite seu número: ");
    int x = int.Parse(Console.ReadLine());

    if(x <= 10){
        Console.WriteLine("Número de valor pequeno");
    }else if(x <= 100){
        Console.WriteLine("Número de valor médio");
    }else{
        Console.WriteLine("Número de valor grande");
    };

```


## if Ternário

&nbsp; O if ternário é um sintaxe sugar (simplificação) que permite que o desenvolvedor aplique um estrutra condicional em apenas uma linha de código.<br>

### Exemplo

```csharp
    String result = 1 > 2 ? "Verdadeiro" : "Falso";

    Console.WriteLine(result); //Output: "Falso"
```

&nbsp; No if ternário primeiro deve-se informar o teste lógico, depois uma interrrogação seguida pelo código que será executado caso o teste for verdadeiro e por final os dois pontos seguidos pelo código a ser executado caso o teste for falso. <br>

* Obs: Apesar de possível, o if ternário não deve ser encadeado como uma estrutura de if ,else if, else.


## Switch 

&nbsp; A estrutura de repetição switch é utilizada como uma sintaxe alternativa a um encadeamento de IF's.

## Sintaxe

&nbsp; Para melhor entendimento da sua sintaxe deve-se observar que:

1º Após cada palavra "case" está o valor a ser testado. Logo pode-se ler um case como: "Caso o valor seje x faça algo". <br>

2º Após a valor do case estará o símbolo de dois pontos, o memso indicará que apertir deste ponto do código será executado o que será feito caso o valor seja o valor testado pelo case.

3º Ao final de cada "case" deve-se utilizar a palavra reservada "break", a mesma fará com que os cases abaixos não sejam executados ou testados, se um case já foi satisfeito.

4º No final de todo encadeamento de "cases" deve-se colocar a estrutura "default", está será semelhante a estrutura "else", que será executada caso nenhum "case" seja satisfeito.

### Exemplo

```csharp
    int day = 4;
    
    switch (day) 
    {
    case 1:
        Console.WriteLine("Monday");
        break;
    case 2:
        Console.WriteLine("Tuesday");
        break;
    case 3:
        Console.WriteLine("Wednesday");
        break;
    case 4:
        Console.WriteLine("Thursday");
        break;
    case 5:
        Console.WriteLine("Friday");
        break;
    case 6:
        Console.WriteLine("Saturday");
        break;
    case 7:
        Console.WriteLine("Sunday");
        break;
    }

    // Outputs "Thursday" (day 4)


```
