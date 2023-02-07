# Operadores de Atribuição

&nbsp; Na seção anterior "Tipagem" no artigo variáveis foi introduzido o conceito de atribuição utilizando o sinal de igual para atribuir valor a uma variável. Entretanto o CSharp provê outros operadores de atribuição com as citadas abaixo.

    = O valor da variável será igual o valor informado.

```csharp
    int numb = 10;
    Console.WriteLine(numb);

    // Output: 10
``` 

    += O valor da variável será igual o valor já contido mais o valor informado.

```csharp
    int numb = 10;
    numb += 5;
    Console.WriteLine(numb);

    // Output: 15
```   

* #### Obs: 

&nbsp; O operador +=  também pode ser utilizado para concatenar strings.

```csharp
    string text = "ABC";
    text += "DE";
    Console.WriteLine(text);

    // Output: "ABCDE"
```   

    -= O valor da variável será igual o valor já contido menos o valor informado.

```csharp
    int numb = 10;
    numb -= 5;
    Console.WriteLine(numb);

    // Output: 5
```   

    *= O valor da variável será igual o valor já contido multiplicado pelo valor informado.

```csharp
    int numb = 10;
    numb *= 5;
    Console.WriteLine(numb);

    // Output: 50
```   


    /= O valor da variável será igual o valor já contido multiplicado pelo valor informado.

```csharp
    int numb = 10;
    numb /= 5;
    Console.WriteLine(numb);

    // Output: 2
``` 
