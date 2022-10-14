# Conversão entre Tipos e Casting

&nbsp; Por diversas vezes na programação é facíl deparar-se com a necessidade de converete um tipo para outro, para realizar uma operação, teste lógico, etc. A linguagem CSharp além de suportar a conversão implícita e explícita, também suporta o casting, que por sua vez também é uma forma de conversão explícita.

## Conversão implícita

&nbsp; A Conversão implícita é realizada automáticamente pelo compilador. Um exemplo de conversão implícita é quando uma váriavel do tipo double recebe um valor do tipo float.Isto ocorrerá porque o tipo double suporta um número de ponto flutuante de até 8 bits, enquanto o tipo float suporta um número de ponto flutuante de até 4 bits. Logo é possível dizer que float está contido em double.

### Exemplo

```
    float numb = 4.8f;
    double numb2 = numb;

    Console.WriteLine(numb2); // Output: 4.8
```

&nbsp; Caso a operação fosse feita ao contrário o compilador lançaria um erro, pois float não pode ser convertido para double sem correr um risco de perda de dados.

## Conversão explícita com Casting

&nbsp; Um maneira de realizar a atribuição de uma variável do tipo float utilizando uma variável do tipo double seria utilizando o casting. O casting é uma maneira do desenvolvedor informar que realmente deseja converter o valor mesmo conciente da possível perda de dados. Para utilizá-lo é necessário informar entre parênteses o tipo de dado desejado na frente do valor a ser convertido.


### Exemplo

```
    double numb = 4.8;
    float numb2 = (float)numb;

    Console.WriteLine(numb2); // Output: 4.8
```

#### Obs:

Neste caso não ocorrerá perda de dados,pois o valor 4.8 é muito pequeno e não ultrapassa 4 bits.

## Métodos para conversão

&nbsp; Além das conversões vistas acima, é possível utilizar um método para auxilar na conversão de tipos dados. Alguns exemplos destes métodos estão abaixo.

### Exemplo: Converter para int

```
    int numb = int.Parse("4");
    // Neste caso o valor de numb será 4 e não a string "4"
```

### Exemplo: Converter para float

```
    float numb = float.Parse("4,5");

    Console.Write(numb + 5); // Output: 9,5
```

### Exemplo: Converter para char

```
    string oneChar = "Y";
    char text = char.Parse(oneChar);

    Console.Write(text.GetType()); //Output: System.Char
```

* #### Obs:

&nbsp; O Exemplo acima mostra como é possível obter o tipo de uma variável utilizando o método GetType.

### Exemplo: Converter para bool

```
    string isOnn = "true";
    bool isActvive = bool.Parse(isOnn);

    Console.WriteLine(isActvive); // Output: True
    Console.Write(isActive.GetType()); // Output: System.Boolean
```

### Exemplo: Converter para string

```
    int numb = 234;
    string text = numb.ToString();

    Console.Write(text.GetType()); // Output: System.String
```

* #### Obs:

&nbsp; O tipo string não possui o método Parse, porém quase todos os tipo possuem uma implementação do método ToString que transformará o valor em string.
