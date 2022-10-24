# Enum (Enumerações)

&nbsp; Na programação as enumerações são utilizadas para limittar possibilidades de valores para determinada atribuição.

### Exemplo

&nbsp; Um exemplo de enum pode ser dado por cores de canetas. Normalmente as cores comuns de canetas são { Vermelho, Azul e Preto}. Logo se um programa deseja restringir a possibilidade de atribuição para a cor de uma caneta , deve-se utilizar o enum, pois desta forma apenas as cores previamente enumeradas poderão ser atribuídas a propriedade da cor da caneta.

```
    Pen blackPen = new Pen{Brand="Bic", Color=Colors.Preto};
    Pen redPen = new Pen{Brand="Compact", Color=Colors.Vermelho};
    Pen bluePen = new Pen{Brand="MontBlanc", Color=Colors.Azul};

    blackPen.Write(); // Output: Caneta da marca Bic e cor Preto está escrevendo
    redPen.Write(); // Output: Caneta da marca Compact e cor Vermelho está escrevendo
    bluePen.Write(); // Output: Caneta da marca MontBlanc e cor Azul está escrevendo

    class Pen {
        public string? Brand {get; set;}
        public Colors Color {get; set;}

        public void Write(){
            System.Console.WriteLine($"Caneta da marca {Brand} e cor {Color} está escrevendo");
        }
    }

    enum Colors : int {
        Vermelho,
        Azul,
        Preto
    }
```

## Sintaxe

&nbsp; O exemplo acima mostra que para criar um enum deve-se utilzar a palavra chave "enum" em uma sintaxe parecida com a declaração de uma classe. Entretanto, dentro do enum deve estar apenas os valores enumerados separados por vírgula.

## Sintaxe alternativa

&nbsp; Por padrão um enum do tipo int, como apresentado no exemplo, será automaticamente enumerado pelo compilador.Logo o primeiro valor será zero, o segundo será um, e assim por diante.Porém caso necessário, o programador pode atribuir os valores na ordem desejada utilizando o operador de atribuição.

### Exemplo:

```
    enum Colors : int {
        Vermelho = 1,
        Azul = 2,
        Preto = 3
    }
```

## Conversões

&nbsp; É possível que um enum como mostrado acima seja convertido para string e que uma string cuja o valor sejá igual a um valor enumerado dentro do enum, seja convertido para um enum.

* ### enum para string

&nbsp; Para converter um valor de um enum para uma string, basta utilizar o método ToString.

### Exemplo

```
    string str = Colors.Vermelho.ToString();

    System.Console.WriteLine(str); // Output: Vermelho

    enum Colors : int {
        Vermelho = 1,
        Azul = 2,
        Preto = 3
    }
```

* ### string para enum

&nbsp; Para converter uma string para enum, deve-se utilizar o método Parse da classe Enum recebendo o valor a ser convertido.

### Exemplo

```
    Colors blue = Enum.Parse<Colors>("Azul");

    System.Console.WriteLine(blue); // Output: Azul

    enum Colors : int {
        Vermelho = 1,
        Azul = 2,
        Preto = 3
    }

```