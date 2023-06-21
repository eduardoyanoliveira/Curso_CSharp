# Params

&nbsp; O artigo anterior apresenta o tópico de funções, onde uma função pode receber valores exeternos no momento de sua execução chamado de parâmetros. Entretanto, por vezes é preciso criar uma função que receba uma quantidade desconhecida de parâmetros, com por exemplo uma função para calcular a média de uma amostra.

&nbsp; Para resolver o problema de parâmtros em quantidade desconhecida pode-se utilizar a palavra reservada "params". A palavra params permite que a função receba um array de valores. Para que o entendimento seja facilitado, deve-se analisar o exemplo abaixo.

### Exemplo

&nbsp; Neste exemplo a função Avg recebe uma lista de números inteiros e deve retornar sua média, o único parâmetro que a função recebe é chamado numbers indicado com a palavra params seguida pelo tipo do array, que neste caso é int.

```csharp
    double averageAge = Avg(18, 37, 48, 24, 32, 51, 60, 70);

    System.Console.WriteLine(averageAge); // Output: 42


    double Avg(params int[] numbers){
        int sum = 0;

        foreach (int number in numbers)
        {
            sum += number;
        }

        double result = sum / numbers.Length;

        return result;
    };
```
