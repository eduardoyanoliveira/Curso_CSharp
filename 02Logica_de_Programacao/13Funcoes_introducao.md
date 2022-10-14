# Introdução as Funções

&nbsp; Na programação funções são trechos de códigos que podem ser executados a qualquer momento no programa e que resultará em um mesmo valor ou ação. As funções são utilizadas quando se é necessário reaproveitar um trecho de código,pois o mesmo será necessário em outras partes do programa.

### Exemplo:

&nbsp; Para facilitar a compreensão das funções, abaixo será apresentado uma função que receberá dois números e retornará sua soma.

```
    int sum(int x, int y){
        int result = x + y;

        return result;
    };


    Console.WriteLine(sum(7, 3)); // Output: 10

```


## Características

* Declaração: No exemplo acima, é possível analisar que funções são declaradas da seguinte forma:
    - 1º Deve-se informar o tipo da função, que será o tipo de dados que a função retornará. Caso a mesma não retorne nenhum valor seu tipo será "void".
    
    - 2º Deve-se informar o nome da função que identificará o seu bloco de código na memória, por tanto sendo o que será utilizado para executar a função quando necessário.
    
    - 3º Após o nome da função informa-se dentro de parênteses os parâmetros da função.
    
    - 4º Por fim, dentro de chaves estará o bloco de código da função (a função propriamente dita).

* Parâmetros: são valores que podem ser recebido na execução da função.No caso do exemplo acima, a função "sum" recebe dois parâmetros, ambos do tipo int. Também é possível analisar que dentro de seu bloco de código, a função utliza os valores recebidos pelos parâmetros através de seus nomes. 

    - Uma função que recebe um determinado conjunto de valores como parâmetro, deve sempre retornar o mesmo resultado para este conjunto.Isto é, se x é igual a 7 e y é igual a 3, o resultado sempre deverá ser 10.

* Execução:  As funções podem ser executadas em qualquer parte do código que possua acesso ao escopo de declaração da função. Para executar uma função, é necessário informar seu nome e parênteses. Se caso a função receba parâmetros, os valores dos mesmos devem ser informados dentro dos parênteses na execução.

* Retorno: Uma função pode ou não retornar um valor. Por vezes a função pode ser apenas um processo, como por exemplo conectar ao banco de dados, ou algo do tipo. Caso seja necessário retornar um valor da função, deve-se utilizar a palavra "return" seguida pelo o valor que será o resultado da função. Todo código dentro das chaves, após o retorno da função não será executado.

* Responsabilidade única: Uma função deve ser apenas responsável por uma única responsabilidade. Caso a função faça mais de um processo, ou possua mais de uma responsabilidade, a mesma deve ser dividida em duas ou mais funções. 


### Exemplo:

&nbsp; Abaixo veremos mais um exemplo que unirá todo conhecimento apresentado até aqui. Está função receberá um array de números inteiros e percorrerá o mesmo printando na tela se cada número é par ou ímpar.

```
    int[] numbers = new int[]{2, 18, 1, 15, 82, 37, 6, 96, 4, 84, 10};

    oddOrEven(numbers);

    void oddOrEven(int[] numbers){
        
        foreach(int number in numbers){
            if(number % 2 == 0){
                Console.WriteLine($"O número {number} é par");
            }else{
                Console.WriteLine($"O número {number} é ímpar");
            };
        };
    };
```

&nbsp; No exemplo acima mostra que em C# pode-se executar uma função antes de sua declaração se a mesma for declarada no mesmo escopo que o código de execução.