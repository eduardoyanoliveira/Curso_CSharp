# Estruturas de Repetição For

&nbsp; As estruturas de repetição são usadas para controlar a execução de códigos repetidamente até que uma condição seja verdadeira. Comumente utilizadas para iterar (percorrer) listas e arrays.<br>

&nbsp; Este artigo aborda quatro tipos diferentes de estruturas de repetição comumente utilizadas em CSharp.

* ## for

&nbsp; O laço for é uma das estruturas de repetição mais comuns no universo da programação. Neste caso o laço for no C# é o mesmo do for tradicional de linguagens como C e C++. <br>

&nbsp; Sua estrutura consiste nas seguintes etapas:

    - Primeiro deve-se utilizar a palavra reservada for para indicar que um laço for está sendo criado.

    - Dentro de parênteses deve-se primeiro inicializar uma variável de controle que será responsável por controlar em qual repetição o laço encontra-se.

    - Depois da variável de controle, informa-se a condição para que o laço termine a execução. Se está condição nunca for verdadeira o lço resultará em um loop infinito. A condição normalmente está relacionada a variável de controle. Ex: (Até que a variável de controle seja menor que o tamanho da lista).

    - Por final dentro dos parênteses deve-se colocar o padrão de mudança da varável de controle a cada iteração do laço for. Utilizando o exemplo do tópico anterior, o padrão de mudança seria normalmente a incremento da variável de controle a cada rodada do laço for. 

        - Obs: Todas as etapas dentro dos parênteses devem ser separadas por ponto e vírgula.
    
    - Depois do fechamento dos parênteses deve-se declarar o escopo do laço for, isto é, o que será executado a cada iteração. Tal como a estrutura condicional IF o escopo do for é declarado dentro de chavez.

    - Finaliza-se com ponto e vírgula após o fechamento das chaves para indicar término da estrutura.


### Exemplo:

&nbsp; O Exemplo a seguir utiliza a estrutura de repetição for para iterar sobre um array de nomes e a cada repetição o nome armazenado no atual índice do array é printado no console.


```csharp
    String[] names = new String[3]{"Yan", "john", "Mary"};
    
    for (int i = 0; i < names.Length; i++)
    {
        Console.WriteLine(names[i]); 
    };

    /* ----- Output ------
        Yan
        john
        Mary
    */

```

&nbsp; Para acessar o índice atual do array na repetição, deve-se utilizar a variável de controle, neste caso "i", pois a mesma terá o valor atual da iteração que será o mesmo valor do índice atual do array. Uma vez que a mesma, tal como array, começa com o valor zero, é incrementada por repetição e para de ser incrementada quando seu valor for igual ao tamanho do array.

* ## Foreach

&nbsp; Acima, descreve-se o uso do for clássico para iterar sobre um array. Entretanto, o C# também disponibiliza o foreach que pode realizar o mesmo processo com maior simplicidade.

&nbsp; A estrutura do foreach consiste nas seguintes etapas:

    - Como o foreach trata-se de um bloco de código, o mesmo possúira um escopo tal como o for clássico e por ser uma estrutura de repetição também possuirá uma condicional entre parênteses.

    - O foreach como o nome sugere irá performar uma opereção para cada item de um objeto iterável. Desta forma é preciso apenas informar uma variável de controle com o tipo de dados do objeto iterável seguida da palavra reservada "in" e o nome do objeto iterável desejado. A Variável de controle será on valor do índice atual.

        - Obs: Objeto iteráveis são tipos de dados que podem ser percorridos, que possuem índices. Como arrays e listas.



### Exemplo:

&nbsp; O Exemplo a seguir trata-se do mesmo exemplo utilizado para o for clássico, porém utilizando o foreach.

```csharp
    String[] names = new String[3]{"Yan", "john", "Mary"};

    foreach (String name in names)
    {
        Console.WriteLine(name); 
    };

    /* ----- Output ------
        Yan
        john
        Mary
    */

```

&nbsp; Para facilitar a compreensão o código acima pode ser lido como: "Para cada name (nome) dentro da lista names (nomes) faça o que está dentro das chaves".

