# Strings: Introdução

&nbsp;  Como já referido strings na programação são encadeamentos de caracteres e no caso do CSharp são representados dentro de aspas duplas. Este artigo apresenta diversas possibilidades no uso de strings.


* ## Caracter de escape

&nbsp; O caracter de escape é utilizando como uma barra invertida anterior a algum caracter dentro da string, asegurando que o caracter subsequente será uma string. O mesmo pode ser usado por exemplo para colocar aspas duplas dentro da string, o que não seria possível sem o mesmo, porque o compilador entenderia que as aspas duplas estão fechando a string.

```csharp
    Console.WriteLine("Gendalf gritou \"Não Passará\" e com seu cajado golpeou o chão.");
    // Output: Gendalf gritou "Não Passará" e com seu cajado golpeou o chão.
```

#### Obs:

    O método Console.WriteLine permite printar uma informação no console.

&nbsp; Para colocar uma barra invertida literal dentro da string basta colocar duas barras invertidas seguidas.

```csharp
    Console.Write("Teste \\ "); // Output: Teste \
```

### Outros exemplos de caracteres de escape são:

   - \t 	 Tabulação horizontal.
   - \v 	 Tabulação vertical.
   - \n 	 Nova linha.
   - \b 	 Backspace


# Indexação de Strings

&nbsp; Em CSharp todas as strings são indexaveis, isto é, possuem índices.
Quando criado uma string,a mesma será indexada transformando cada caracter em um índice.

    Ex: "Ceu Azul"
         01234567

&nbsp; No exemplo acima é possível observar que a indexação começa por zero e será incrementada de forma finita de acordo
com a quantiadade de caracteres da string. <br>

&nbsp; A indexação da string permite acessar cada caracter de acordo com seu índice. Um exemplo de tal funcionalidade seria acessar o primeiro caracter de uma string e printá-lo na tela.

### Exemplo:

```csharp
    string phrase =  "Ceu Azul";

    Console.WriteLine(phrase[0]); // Output: C
    Console.WriteLine(phrase[4]); // Output: A
    Console.WriteLine(phrase[3]); // Output: ' ' => espaço em branco
```

&nbsp; Ao tentar acessar um índice que não existe em uma string o compilador retornará o seguinte erro "System.IndexOutOfRangeException".

## Encontrar índice de um determinado caracter

&nbsp; O método IndexOf da clase String pode ser utilizado para descobrir o índice de um determinado caracter dentro da string.


### Exemplo:

```csharp
    string phrase =  "Ceu Azul";

    Console.WriteLine(phrase.IndexOf("l")); // Output: 7
    Console.WriteLine(phrase.IndexOf("C")); // Output: 0
```

#### Obs:
    Caso o caracter não exista dentro da string, será retornado o índice -1.


&nbsp; Ainda com este método é possível passar um segundo parametro que será o índice inicial por onde o compilador pesquisará o caracter na string.

### Exemplo:

```csharp
    string text = "exemplo";
    
    Console.WriteLine(text.IndexOf("e")); // Output: 0
    Console.WriteLine(text.IndexOf("e", 1 )); // Output: 2
```

### Obs: 

    O método IndexOf retornará apenas o primeiro índice cuja o valor seja igual ao informado.

&nbsp; Para encontrar o ultimo índice de um valor em uma string, srá utilizado o método String.LastIndexOf


### Exemplo:

```csharp
    string text = "exemplo";
    
    Console.WriteLine(text.LastIndexOf("e")); // Output: 2
```

## Substituição de caracteres em uma string

&nbsp; O método String.Replace é utilizado para substiuir um caracter dentro da string, sendo o primeiro parâmetro o caracter a ser substituído e o segundo o caracter substituto.

### Exemplo:

```csharp
    string text = "batata";

    Console.WriteLine(text.Replace("a", "o")); // Output: bototo
```

## Quantidade de Caracteres em uma string

&nbsp; Para obter a quantidade de caracteres de uma string utiliza-se o método String.Length. 

### Exemplo:

```csharp
    string text = "batata";

    Console.WriteLine(text.Length()); // Output: 6
```

## Obter substring. (Fatiar string)

&nbsp; O método String.Slice permite o desenvolvedor a obter uma substring através de uma string. Para executar o método é necessário informar índice inicial onde a substring começará e o índice final.

### Exemplo:

```csharp
    string text = "O rato roue a roupa do rei de roma";

    Console.WriteLine(text.Slice(2, 6)); // Output: "rato"
```

## Criar array através de strings

&nbsp; Na programação a palavra array refere-se a uma lista indexada. Este é um tópico que será abordado em próximas seções. Entretanto aqui será exemplificado o método String.Split que separa uma string por um dado caracter armazenando as separações resultantes em um array.


### Exemplo:

```csharp
    string text = "O rato roue a roupa do rei de roma";

    text.Split("r").ToString(); // O resultado será a lista: [ "O ", "ato ", "oue a ", "oupa do ", "ei de ", "oma" ]
    text.Split("r", 3).ToString(); // O resultado será a lista: [ "O ", "ato ", "oue a " ]

    // Por espaço
    text.Split(" ");  // O resultado será a lista: ["O", "rato", "roue", "a", "roupa", "do", "rei", "de", "roma"]
```

## Transformar string em letras maiúsculas

&nbsp; O método String.ToUpper é utilizado para transformar todos os caracters de uma string em letras maiúsculas 

### Exemplo:

```csharp
    string text = "test";

    Console.WriteLine(text.ToUpper()); // Output: "TEST"
```

## Transformar string em letras minúsculas

&nbsp; O método String.ToUpper é utilizado para transformar todos os caracters de uma string em letras minúsculas 

### Exemplo:

```csharp
    string text = "Test";

    Console.WriteLine(text.ToLower()); // Output: "test"
```

## Capitalizar string. (Transformar a primeira letra de todas as palavras de uma string em maiúscula)


&nbsp; Para transformar a primeira letra de todas as palavras de uma string em maiúscula utiliza-se o método String.ToTitleCase

### Exemplo:

```csharp
    string text = "lua e dol ";

    Console.WriteLine(text.ToTitleCase()); // Output: "Lua E Sol"
```

### Obs

    Este são apenas alguns exemplos de métodos do tipo string em C#. 
