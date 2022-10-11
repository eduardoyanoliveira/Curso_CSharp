# Operadores Aritiméticos

&nbsp; Operadores aritiméticos no Csharp são respeitam a regra de precedência matemática e são utilizados da seguinte forma:

    + Adição
    - Subtração
    * Multiplicação
    / Divisão
    % Resto da Divisão

Para alterar a precedência de uma parte da operação pode-se utilizar os parênteses.

```
    double numb = 5.5 + 10 * (2 + 2) / 2;
    Console.WriteLine(numb);    

    // Output: 25,5
```

* #### Obs:

Para gerar um valor double pelos menos um número da expressão deve conter casas decimais, caso contrário o compilador irá truncar o resultado para um número inteiro.

## Petenciação e Raiz Quadrada

&nbsp; Os metódos Pow e Sqrt da classe Math são utilizados respectivamente para Potênciação e Raiz Quadrada.

### Exemplo: Potenciação

```
    Console.WriteLine(Math.Pow(5, 2));
    // Output: 25
```


### Exemplo: Raiz Quadrada

```
    Console.WriteLine(Math.Sqrt(9));
    // Output: 3
```

* #### Obs:

&nbsp; Para acesar um metódo ou propriedade de uma classe é utilizado a notação de ponto. 
<nome_da_classe>.<metodo_ou_propriedade>