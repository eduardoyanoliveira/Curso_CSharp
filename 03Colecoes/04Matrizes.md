# Matrizes

&nbsp; A definição de uma matriz na programação é um vetor bidimensional. Isto é, matrizes são estruturas de dados semelhantes aos vetores (abordado na seção Logica_de_Programção), porém , ao contrário dos vetores comuns, as matrizes possuem linhas e colunas (2 dimensões).

## Sintaxe

&nbsp; A sintaxe utilizada para declarar uma matriz em C# é muito parecida com a sintaxe dos vetores. Entretanto,  no caso da matriz, deve-se colocar uma vírgula dentro dos colchetes para que o compilador entenda a declaração como uma matriz, e também deve-se informar a quantidade de linhas e colunas que a matriz possuirá.

### Exemplo

&nbsp; O exemplo abaixo instância uma matriz de 3 linhas e 2 colunas.

```
    double[,] mat = new double[3, 2];
```

## Verificar a quantidade total de elementos de uma matriz

&nbsp; Utiliza-se a propriedade length para verificar a quantidade total de elementos de uma matriz.

### Exemplo


```
    double[,] mat = new double[3, 2];

    Console.WriteLine(mat.Length); // Output: 6
```

## Verificar a quantidade de linhas de uma matriz e quantidade de colunas

&nbsp; Para descobrir ambas as quantidades linhas e colunas de uma matriz, deve-se utilizar o método GetLength. Este método recebe como parâmetro a dimensão cuja o tamanho é desejado. Logo, para descobrir a quantidade de linhas de uma matriz utiliza-se o GetLength(0), enquanto GetLength(1) será utilizado para retornar a quantidade de colunas.

### Exemplo

```
    double[,] mat = new double[3, 2];

    Console.WriteLine(mat.GetLength(0)); // Output: 3
    Console.WriteLine(mat.GetLength(1)); // Output: 2
```

## Obs

- O primeiro índice de cada dimensão de uma matriz se inicializará com o valor zero.