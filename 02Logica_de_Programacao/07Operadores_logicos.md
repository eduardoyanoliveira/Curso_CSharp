# Operadores Lógicos

&nbsp; Operadores lógicos são utilizados quando o desenvolvedor precisa realizar uma ou mais validações dentro do código. Os operadores lógicos testam hipóteses de estados a um ou mais valores.

## Operadores

&& operador "e" ou "and". Utilizado para realizar mais de uma comparação dentro do mesmo teste lógico.<br>
O Programa apenas retornará True caso ambas as comparações forem veredadeiras.

### Exemplo:

```csharp
    Console.WriteLine(10 > 3 && 4 < 7); // Output: True
    Console.WriteLine(4 > 2 && 4 < 3); // Output: False
```


|| operador "ou" ou "or". Utilizado para realizar mais de uma comparação dentro do mesmo teste lógico.<br>
O Programa retornará True caso ao menos uma das comparações for veredadeira.

### Exemplo:

```csharp
    Console.WriteLine(1 > 3 && 4 < 2); // Output: False
    Console.WriteLine(4 != 2 || 4 < 3); // Output: True
```

! operador "não" ou "not". Utilizado para inverter o valor do teste lógico, de por exemplo, "dois é maior que 3?" para "dois não é maior que três?".<br>
O Programa retornará True caso o teste lógico resulte em False.

### Exemplo:

```csharp
    Console.WriteLine(!(1 > 3)); // Output: True
    Console.WriteLine(!(4 > 2)); // Output: False
```

## Precedência de Operadores

&nbsp; Tal como a precedência em operadores aritiméticos, os o operadores lógicos também possuem sua precedência que se dá por:

    ! (not) tem maior precedência que && (and) que tem maior do que || (or).

&nbsp; E também como os operadores aritiméticos, a precedência dos opreadores lógicos pode ser alterada por parênteses.
