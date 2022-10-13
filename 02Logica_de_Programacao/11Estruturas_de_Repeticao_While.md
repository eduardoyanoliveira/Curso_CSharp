# Estruturas de Repetição While

* ## While

&nbsp; O Artigo anterior apresenta as estruturas de repetição "for" que são normalmente utilizadas para iterar. Este artigo por sua vez apresenta a estrutura de repetição "while" que cria um loop que será executado enquanto uma condicional for verdadeira.<br>

&nbsp; A maneira mais simples de entender o laço while é atrvés de um exemplo, que neste caso apresenta um programa que solicitará que o usuário informe um número até que o número informado for igual ao valor de uma variável.

### Exemplo:

&nbsp; Neste exemplo o usuário deve descobrir o número secreto de um a dez.

```
Random rand = new Random();
int secret = rand.Next(1, 10);

Console.WriteLine("Digite um número de um à dez: ");
int guess = int.Parse(Console.ReadLine());

while(guess != secret)
{
    Console.WriteLine("Digite um número de um à dez: ");
    guess = int.Parse(Console.ReadLine());
};

Console.WriteLine($"Correto!!! o número secreto é {secret}");

```

&nbsp; No exemplo acima caso o usuário acerte o número secreto aleatório na primeira tentativa o programa sequer entrará no laço while.<br>

&nbsp; Para facilitar o compreendimento o exemplo acima pode ser lido da seguinte forma: "enquanto guess(palpite) for diferente de secrete(número secreto) faça o que estiver dentro do escopo de código do laço while. 

* ## Do while

&nbsp; Caso necessário que o laço while seja executado ao menos uma vez, o desenvolvedor pode optar por utilizar o laço do while, cuja a única diferença sintática para o laço while é que na abertura do laço deve-se utilizar a palavra "do" e apenas no final do escopo do laço deve-se informar a palavra "while" junto a sua condicional.

### Exemplo

```

    int secret = 7;
    int guess = int.Parse(Console.ReadLine());

    do{

        Console.WriteLine("Executou o laço");

        Console.WriteLine("Digite um número de um à dez: ");
        guess = int.Parse(Console.ReadLine());
        
    }while(guess != secret);

    Console.WriteLine($"Correto!!! o número secreto é {secret}");
```

&nbsp; No exemplo acima o programa executará o laço while ao menos uma vez, permitindo que a linha de código que solicita a entrada do palpite do usuário esteja dentro do laço while.

