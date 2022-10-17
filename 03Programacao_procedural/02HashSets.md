# HashSets (Conjuntos)

&nbsp; HashSet são conjuntos de elementos. Por possuir similariadas aos conjuntos álgebricos, são muito utilizados em algoritimos matemáticos.

## Características

* Não admite repetições.
* Elementos não possuem posição.
* Acesso, inserção e remoção de elementos são rápidos.
* Oferece operações eficientes de conjunto: interseção, união, diferença.

## Sintaxe

&nbsp; A sintaxe de declaração de um HashSet em C# é identica a sintaxe de um List (Apresentado no artigo anterior).

### Exemplo

```
    HashSet<string> names = new HashSet<string>{"Yan", "John", "Emmily", "Mary", "Rafael", "Ana", "Robert"};

    HashSet<int> numbers = new HashSet<int>();
```

&nbsp; Os HashSets podem ou não ser inicializados na sua declaração.

* ### Adicionar e Remover elementos

&nbsp; Para adicionar ou remover um elemento em um HashSet deve-se utilizar os métodos Add e Remove tal como utilizados com List.

* ### RemoveWhere

&nbsp; O método RemoveWhere pode ser utilizado para remover um ou mais elementos que satisfaça a função predicate recebida como parâmetro.

### Exemplo-

```
    HashSet<string> names = new HashSet<string>{"Yan", "John", "Emmily", "Mary", "Rafael", "Ana", "Robert"};

    names.RemoveWhere(containsOLetter);

    foreach(string name in names){
        Console.WriteLine(name);
    };

    /* ---- Output ----
        Yan
        Emmily
        Mary
        Rafael
        Ana
    */

    bool containsOLetter(string word){
        return word.IndexOf('o') > 0;
    };
```

&nbsp; No Exemplo acima é possível observar que por ser um tipo de dados indexável, o HastSet pode ser iterado com for ou foreach.

## Operações de conjuntos álgebricos

&nbsp; Como citado anteriormente, o HashSet possui características de conjunto álgebrico. O mesmo possui métodos que performam operações similares as operadas na álgrabra, como: União, Intersecção, Diferença.

* ### UnionWith (União)

&nbsp; UnionWith pode ser utilizado para unir dois conjuntos. Está união adicionará apenas os elementos do conjunto B que já não estejam contidos no conjunto A.

### Exemplo


```
    HashSet<int> numbersOne = new HashSet<int>{1, 5, 7, 6};
    HashSet<int> numbersTwo = new HashSet<int>{6, 2, 10};

    numbersOne.UnionWith(numbersTwo);

    foreach(int number in numbersOne){
        Console.WriteLine(number);
    };


    /* ---- Output ----
        1
        5
        7
        6
        2
        10
    */

```

* ### IntersectWith (Intersecção)

&nbsp; Da mesma maneira que utiliza-se o UnionWith para unir conjuntos, o IntersectWith pode ser utilizado para realizar gerar um conjunto de Intersecção entre dois conjuntos. (Intersecção é o conjunto de elementos que estão presentes em ambos cojuntos).

### Exemplo

```
    HashSet<int> numbersOne = new HashSet<int>{1, 5, 7, 6};
    HashSet<int> numbersTwo = new HashSet<int>{6, 2, 10};

    numbersOne.IntesectWith(numbersTwo);

    foreach(int number in numbersOne){
        Console.WriteLine(number);
    };


    /* ---- Output ----
        6
    */

```

* ### ExceptWith (Diferença)

&nbsp; O método IntersectWith é utilizado para gerar um conjunto com a diferença entre elementos de um conjunto A com outro conjunto B. ( A Diferença entre conjuntos são os elementos que não estão presentes no outro).


### Exemplo

```
    HashSet<int> numbersOne = new HashSet<int>{1, 5, 7, 6};
    HashSet<int> numbersTwo = new HashSet<int>{6, 2, 10};

    numbersOne.ExceptWith(numbersTwo);

    foreach(int number in numbersOne){
        Console.WriteLine(number);
    };


    /* ---- Output ----
        1
        5
        7
    */

```

## SortedSet

&nbsp; O C# também apresenta o tipo SortedSet que é praticamente identico ao HashSet. As únicas diferenças estão listadas abaixo.


###  HashSet

- Armazenamento em tabela hash.
- Extremamente rápido: inserção, remoção e busca O(1).
- A ordem dos elementos não é garantida.

### SortedSet

- Armazenamento em árvore.
- Rápido: inserção, remoção e busca O(log(n)).
- Os elementos são armazenados ordenadamente conforme implementação IComparer<T>.