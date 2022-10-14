# List

&nbsp; Lists ou Listas são um tipo de dados que em muito se assemelha com os arrays. Ambos são responsáveis por aramazenar uma coleção. Entretanto, ao contrário dos arrays, as listas são muito mais maleáveis, permitindo que valores seja adicionados e removidos após a criação da lista.<br>

&nbsp; As listas também possuem vários métodos que podem ser utilizados para filtrar, pesquisar e reduzi-lá.

## Sintaxe

&nbsp; A sintaxe da lista é muito parecida com a sintaxe do array. O exemplo abaixo mostra uma lista de nomes.

### Exemplo:

```
    List<string> names = new List<string>{"Yan", "John", "Emmily"};

    foreach(string name in names){
        Console.WriteLine(name);
    };

    /* ---- Output ----
        Yan
        John
        Emmily
    */
```
&nbsp; A palavra reservada "new" é utilizada para referir que trata-se de um nova instância da classe List. O tópico de classes será abordado em seções relacionadas a orientação a objetos.
## Adicionando elementos a lista

&nbsp; Como citado acima, ao contrário dos arrays que contém um número fixo de elementos, no caso das listas é possível adicionar a quantidade de elementos necessários após sua instanciação (criação).

* ### Add

&nbsp; O método "Add" adiciona um elemento no final da lista.

### Exemplo:

```
    List<string> names = new List<string>{"Yan", "John", "Emmily"};
    names.Add("Smith");

    foreach(string name in names){
        Console.WriteLine(name);
    };

    /* ---- Output ----
        Yan
        John
        Emmily
        Smith
    */
```

* ### Insert

&nbsp; Com o método "Insert" é possível adicionar elementos em um determinado índice da lista, passando como o primeiro parâmetro o índice desejado, e o valor a ser adicionado como segundo parâmetro.

```
    List<string> names = new List<string>{"Yan", "John", "Emmily"};
    names.Insert(1, "Smith");

    foreach(string name in names){
        Console.WriteLine(name);
    };

    /* ---- Output ----
        Yan
        Smith
        John
        Emmily
    */
```

## Removendo elementos da lista

* ### Remove

&nbsp; O método "Remove" permite o desenvolvedor remover um elemento da lista pelo seu valor. É importante atentar-se que apenas o primeiro elemento encontrado na lista com o valor desejado será removido.

```
    List<int> numbers = new List<int>{2, 5, 8, 6, 2};

    numbers.Remove(2);

    foreach(int number in numbers){
        Console.WriteLine(number);
    };

    /* ---- Output ----
        5
        8
        6
        2
    */

    // Apenas o primeiro número 2 foi removido da lista
```

* ### RemoveAll

&nbsp; Para remover todos os elementos de uma lista que sejam igual a um valor desejado, deve-se utilizar o método RemovAll.<br>

&nbsp; O método RemoveAll recebe como parâmetro um <i> predicate </i>, que trata-se de uma função que receberá cada valor da lista e verificará se o valor atende uma condição. Neste caso como está se utilizando o método RemoveAll, se o valor atender a condição o mesmo será removido da lista.

### Exemplo

&nbsp; O exemplo abaixo utiliza o método RemoveAll em uma lista de números inteiros, recebendo como predicate uma função que verifica se o número é par. Logo todos os números pares serão removidos da lista.

```
    List<int> numbers = new List<int>{2, 5, 8, 6, 2, 7, 28, 6, 9, 11, 14, 37, 53 };

    numbers.RemoveAll(IsOdd);

    foreach(int number in numbers){
        Console.WriteLine(number);
    };

    /* ---- Output ----
        5
        7
        9
        11
        37
        53
    */

    bool IsOdd(int number){
        return number % 2 == 0;
    };


```

&nbsp; Perceba que a função predicate não deve ser executada.

* ### RemoveAt

&nbsp; O método RemoveAt remove um elemento da lista pelo seu índice.

### Exemplo

```
    List<string> names = new List<string>{"Yan", "John", "Emmily"};
    names.RemoveAt(1);

    foreach(string name in names){
        Console.WriteLine(name);
    };

    /* ---- Output ----
        Yan
        Emmily
    */
```

* ### RemoveRange

&nbsp; RemoveRange remove uma quantidade de elementos de uma lista apartir de um determinado índice. Logo para executar o método, deve-se informar como primeiro parâmetro o índice incial onde a remoção começará, e como segundo parâmetro a quantidade de elementos a ser removidos.

### Exemplo

&nbsp; Neste exemplo será removido do índice 4 (o segundo número 2) cinco elementos (até o valor 11).

```
    List<int> numbers = new List<int>{2, 5, 8, 6, 2, 7, 28, 6, 9, 11, 14, 37, 53 };

    numbers.RemoveRange(4, 5);

    foreach(int number in numbers){
        Console.WriteLine(number);
    };

    /* ---- Output ----
        2
        5
        8
        6
        11
        14
        37
        53
    */
```

## Encontrando elementos na lista

* ### Find

&nbsp; Find é o método utilizado para encontrar o primeiro que esteja na condição da função predicate passada como parâmetro.

### Exemplo

&nbsp; No exemplo abaixo como a função predicate é a mesma função utilizada em exemplos anteriores que verifica se um número é par, o método Find irá retornar o primeiro número par da lista.

```
    List<int> numbers = new List<int>{5, 8, 6, 2, 7, 28, 6, 9, 11, 14, 37, 53 };

    int number = numbers.Find(IsOdd);

    Console.WriteLine(number); // Output: 8

    bool IsOdd(int number){
        return number % 2 == 0;
    };

```

* ### FindAll

&nbsp; FindAll funcionará tal como Find, porém retornará todos os valores que respeitarem a condição da função predicate, gerando assim uma nova lista.

### Exemplo

&nbsp; Neste exemplo será retornado de uma lista de nomes, todos nomes que contiverem a letra "a".

```
    List<string> names = new List<string>{"Yan", "John", "Emmily", "Mary", "Rafael", "Ana", "Robert"};

    List<string> newNames = names.FindAll(hasLetterA);

    foreach(string name in newNames){
        Console.WriteLine(name);
    };

    /* ---- Output ---
        Yan
        Mary
        Rafael
        Ana
    */

    bool hasLetterA(string word){
        return word.IndexOf('a') >= 0;
    };
```

* ### FindLast

&nbsp; FindLast também assemelha-se a Find, entretanto, FindLast retornará o ultimo valor na lista que respeitar a condição da função predicate.

### Exemplo

```
    List<string> names = new List<string>{"Yan", "John", "Emmily", "Mary", "Rafael", "Ana", "Robert"};

    string name = names.FindLast(hasLetterA);

    Console.WriteLine(name); // Output: "Ana"

    bool hasLetterA(string word){
        return word.IndexOf('a') >= 0;
    };

```

## Encontrar elemento pelo seu índice

* ### FindIndex e FindLastIndex

&nbsp; FindIndex e FindLastIndex encontrará respectivamente o primeiro e o ultimo elemento da lista que satisfaça o predicado.

### Exemplo

&nbsp; Este exemplo encontra o índice do primeiro e ultimo número par na lista.

```
    List<int> nubmers = new List<int>{3, 1, 4, 7, 8, 9, 11, 10, 15};

    int firstIndex = numbers.FindIndex(isOdd);
    int lastIndex = numbers.FindLastIndex(isOdd);

    Console.WriteLine(firstIndex); // Output: 2
    Console.WriteLine(lastIndex); // Output: 7

    bool IsOdd(int number){
        return number % 2 == 0;
    };

```
