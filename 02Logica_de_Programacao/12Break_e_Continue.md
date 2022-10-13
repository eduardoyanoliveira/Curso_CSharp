# Break e Continue

&nbsp; As palavras reservadas "break" e "continue" podem serem utilizads dentro de laços de repetição para provocar saltos no laço.

* ## Break

&nbsp; A palavra reservada "break" permite que o programador termine o laço de repetição mesmo que a condicional dentre os parênteses do laço seja falsa.

### Exemplo:

&nbsp; O exemplo a seguir itera sobre uma lista de números printando cada número na tela.Entretanto a palavra break é utilizada para interromper a iteração caso o número atual seja o 9.

```
    int[] numbers = new int[]{ 1,5, 6, 7, 3, 4, 10, 8, 2, 9, 17, 23, 51};

    foreach(int number in numbers){

        if(number == 9){
            break;
        };

        Console.WriteLine($"O número atual é {number}");
    };

```

&nbsp; Ao rodar o código acima, percebe-se quue nem o número 9 nem os números posteriores ao 9 no array são printados.

* ## Continue

&nbsp; A Palavra reservada "continue" permite que o desenvolvedor pule para a próxima iteração do laço.

### Exemplo

&nbsp; Este exemplo utilizará o mesmo código do exemplo acima. Entretanto, por utilizar a instrução "continue" apenas o número 9 não será printado no console.

```
    int[] numbers = new int[]{ 1,5, 6, 7, 3, 4, 10, 8, 2, 9, 17, 23, 51};

    foreach(int number in numbers){

        if(number == 9){
            continue;
        };

        Console.WriteLine($"O número atual é {number}");
    };

```