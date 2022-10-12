# Introducação a Array

&nbsp; Um Array é um conjunto de elementos de um mesmo tipo de dados onde cada elemento do conjunto é acessado pela posição no array que é dada através de um índice (uma sequência de números inteiros).  Um array de uma dimensão é também conhecido como vetor. Para facilitar o entendimento o array pode ser descrito como uma lista de elementos do mesmo tipo.<br>

&nbsp; Os arrays são comumente utilizados no dia a dia da programação como por exemplo: Lista de Produtos; lista de clientes; lista de usuários, etc.

## Declarando Arrays em C#

&nbsp; Na linguagem C#  os arrays possuem o índice com base zero, ou seja, o primeiro elemento do array possui o índice zero (0). <br>

&nbsp;Um array é declarado tal como uma variável, porém no caso do array deve-se colocar colchetes após o tipo de dado para que o compilador possa interpretá-lo como array.

### Exemplos:

```
    int[] numbers = new int[3];
```

&nbsp; O exemplo acima declara um array de  três números inteiros inicializado como um array vázio.

```
    int[] numbers = new int[3]{2,7,9};
```

&nbsp; O exemplo acima declara um array de números inteiros cuja o índice zero tem o valor de 2, o índice 1 tem o valor de 7 e por final o índice 2 tem o valor de 9. Percebe-se também que o valor de cada índice é informado dentro das chaves e separado por vírgula.

## Acessando Valores 

&nbsp; Por tratar-se de um valor vetorizado tal como o tipo de dados string, o array compartilha metódos em comum com o tipo string e utiliza a mesma sintaxe para acessar valores.

### Exemplo:

```
    int[] numbers = new int[3]{2,7,9};

    Console.WriteLine(numbers[1]); // Output: 7
```

## Inicializando array vázio

&nbsp; Acima é possível ver um exemplo de declaração de array vázio, entretanto o mesmo não está inicializado. Para que o faça deve-se acessar cada índice do array e utilizar o sinal de atribuição (igual) para armazenar um valor no índice.

```
    int[] numbers = new int[3];
    numbers[0] = 10;
    numbers[1] = 20;
    numbers[2] = 30;

    Console.WriteLine(numbers[1]); // Output: 20;
```

&nbsp; Caso o programador tente acessar ou atribuir valor á um índice maior do que limite dado na declaração do array (neste caso 3), o compilador retornará o erro System.IndexOutOfRangeException.


### Exemplo:

```
    int[] numbers = new int[3];
 
    numbers[3] = 40;

    // Output: System.IndexOutOfRangeException.
```

&nbsp; Caso o índice atribuído já possua um valor, o mesmo será alterado pelo novo valor.

### Exemplo:

```
    int[] numbers = new int[3]{10, 20, 30};
 
    numbers[1] = 40;

    Console.WriteLine(numbers[1]); // Output: 40;
```

## Pegar índice de um valor específico

&nbsp; Similar ao metódo String.IndexOf que retorna o índice de um determinado caracter em uma string, o array também conta com um metódo que retorna o índice de um determinado valor.Entretanto, neste caso para executar o metódo do array deve-se utilizar o próprio nome Array para acessar o metódo não a variável. O método em questão é o Array.IndexOf que recebe como parametro o array e o valor cuja o índice deve-se descobrir.

### Exemplo:

```
    String[] names = new String[3]{"Yan", "john", "Mary"};
 
    Console.WriteLine(Array.IndexOf(names, "Yan")); // Output: 0;
```

## Array.Length

&nbsp; O tipo de dados array conta com a propriedade Array.length que retornará o tamanh o do array. (Neste caso não será utilizado os parênteses na sua execução por não tratar-se de um metódo).

```
    String[] names = new String[3]{"Yan", "john", "Mary"};
    
    Console.WriteLine(names.Length); // Output: 3;
```