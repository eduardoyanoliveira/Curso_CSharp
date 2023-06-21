# Operadores de Incremento e Decremento

&nbsp; Operadores de Incremento e Decremento são utilizados como sintaxe sugar (facilitadores) para incrementar ou decrementar um número. Sendo sempre incrementado ou decrementado o valor de 1. <br>

&nbsp; Para utilizar o operador de incremento é necessário colocar dois sinas de adição na frente do nome da variável. O memso é válido para o operador de decremento, porém neste caso utilizando dois sinais de subtração. 

### Exemplo: Operador de Incremento

```csharp
    int numb = 3;
    numb++;
    Console.WriteLine(numb);

    // Output: 4
```
### Exemplo: Operador de Decremento

```csharp
    int numb = 3;
    numb--;
    Console.WriteLine(numb);

    // Output: 2
```

#### Obs:

&nbsp; Os Operadores exemplificados acima são chamados de operadores de Pós-Incremento e Pós-Decremento, pois alteram o valor após a execução da linha de código.

## Operadores de Pré-Incremento e Pré-Decremento.

&nbsp; Os ao contrátio dos operadores de Pós-Incremento e Pós-Decremento os operadores de Pré-incremento e Pré-decremento alteram o valor na mesma linha de código. Para utiliza-los deve-se colocar os sinas antecedendo o nome da variável.

### Exemplo: Operador de Pré-Incremento

```csharp
    int numb = 3;
    ++numb;
    Console.WriteLine(numb);

    // Output: 4
```
### Exemplo: Operador de Pré-Decremento

```csharp
    int numb = 3;
    --numb;
    Console.WriteLine(numb);

    // Output: 2
```

&nbsp; Os resultados acima parecem o mesmo quando comparados com os exemplos dos operadores de pós-incremento e pós-decremento. O exemplo abaixo demonstra com clareza a diferença entre os dois tipos de operadores:

### Exemplo Pós

```csharp
    int numb = 10;
    int numb2 = numb++;

    Console.WriteLine(numb2); // Output: 10
    Console.WriteLine(numb);  // Output: 11
```

### Exemplo Pré

```csharp
    int numb = 10;
    int numb2 = ++numb;

    Console.WriteLine(numb2); // Output: 11
    Console.WriteLine(numb);  // Output: 11
```

&nbsp; É possível notar que quando utilizado o operador de pós-incremento para atribuir o valor da variável numb2 recebendo o valor da variável, o valor da variável numb2 não será igual o valor da variável numb mais 1. Isto acontece porque o valor da variável numb somente será alterado na próxima linha de código. 
