# Estruturas condicionais

&nbsp; Os artigos anterios demonstram como operadores de comparação e operadores lógicos podem serem utilizados para determinar se hipóteses (testes lógicos) são verdairo ou falso. Entretanto, na maioria das ocasiões tais operadores são utlizados para impor determinada condição ao código do tipo "Se for verdade faça isso, senão faça aquilo. <br>

## Sintaxe

&nbsp; Em c#, tal como na programação em geral,  para criar uma condicional deve-se utilizar o operador <i>if</i>, que receberá por parênteses o teste lógico.

### Exemplo:

&nbsp; O programa abaixo apenas printará no console a mensagem "Olá" caso o teste lógico for verdadeiro.

```
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


```
    if(1 > 2){
        Console.WriteLine("Verdadeiro");
    }else{
        Console.WriteLine("Falso");
    };

    // Output: Falso
```

## else if

&nbsp; Também é possível criar um encadeamento de testes lógicos com escopos diferentes de acordo com cada resultado.Para realizá-lo utiliza-se  a estrutura else if recebendo um teste lógico.

&nbsp; O programa abaixo se comportará da seguinte forma:

    * Caso o valor de "x" for menor ou igual a 10 printará "Número de valor pequeno".
    * Caso o valor de "x" for maior que 10 e menor ou igual a 100 printará "Número de valor médio".
    * Caso nenhum dos testes acima forem verdadeiros o programa printará "Número de valor grande"


```
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