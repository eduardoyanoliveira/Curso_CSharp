# TimeSpan (Duração)

&nbsp; O tipo TimeSpan é utilizado para descrever uma duração em C#, e o mesmo compartilha varias similaridades com o Tipo DateTime apresentado no artigo anterior. Também trata-se de um tipo valor (struct) que pode ser instânciado por meio de builders e construtores.

## Sintaxe

&nbsp; A sinteaxe do TimeSpan também é identica a utilizada com o tipo DateTime.

### Exemplo

```
    TimeSpan ts = new TimeSpan();

    Console.WriteLine(ts); // Output: 00:00:00
```

&nbsp; O Exemplo acima demonstra uma variável do tipo TimeSpan que foi instânciada sem receber valores, por isto a mesma terá o valor de duração zero.

## TimeSpan com parâmetros no construtor


&nbsp; No caso do TimeSpan é possível passar os valores como do dias, horas, minutos, segundos e milesegundos, sendo todos os valores do tipo int.

### Exemplo: Horas, minutos e segundos

```
    TimeSpan ts = new TimeSpan(4, 5, 10);

    Console.WriteLine(ts); // Output: 04:05:10
```

### Exemplo: Dias, horas, minutos e segundos

```
    TimeSpan ts = new TimeSpan(2, 4, 5, 10);

    Console.WriteLine(ts); // Output: 2.04:05:10

```

## TimeSpan com builders

&nbsp; Outra maneira de se instânciar um objeto do tipo TimeSpan é utilizando os métodos Builder, que na sua maioria vão extrair um valor de duração de outros valores como: dias, horas, minutos, etc. <br>

&nbsp; Todos os métodos builders do TimeSpan são representados pela palavra From seguida do tipo de valor que receberá. Ex: FromDays, FromHours, etc. E todos receberão valores do tipo double.

* FromDays
* FromHours
* FromMinutes
* FromSeconds
* FromMilliseconds

### Exemplo: FromDays

```
    TimeSpan ts = TimeSpan.FromDays(3.5);

    Console.WriteLine(ts); // Output: 3.12:00:00

```

&nbsp; O exemplo acima mostra que o valor de três dias e meio em TimeSpan é três dias e doze horas.


## Propriedades 

* Days => Quantidade de dias em um TimeSpan
* Hours => Quantidade de horas 
* Minutes => Quantidade de minutos
* Seconds => Quantidade de segundos
* Miliseconds => Quantidade de milisegundos

* TotalDays => Quantidade total de dias . ( Ao contrário de Days que extrai os dias do TimeSpan, TotalDays transforma todo valor em dias, retornando um valor por vezes fracionado em dias que representa todo TimeSpan).
* TotalHours => Quantidade total de horas
* TotalMinutes=> Quantidade total de minutos
* TotalSeconds => Quantidade total de segundos
* TotalMiliseconds => Quantidade total de milesegundos


### Exemplo

```
    TimeSpan ts = new TimeSpan(3, 7, 8, 9, 1000);

    Console.WriteLine(ts.Days); // Output: 3
    Console.WriteLine(ts.TotalDays); // Output: 3,297337962962963
```

## Operações com TimeSpan


Add(TimeSpan) => Soma dois TimeSpans
Subtract(TimeSpan) => Retorna a diferença entre dois TimeSpans
Multiply(double) => Multiplíca um TimeSpan por um valor double
Divide(doble) => Divide um TimeSpan por um valor double

&nbsp; Todos são métodos, e por este motivo devem ser acessados através de uma instância de TimeSpan.

### Exemplo

```
    TimeSpan ts = new TimeSpan(3, 7, 8, 9, 1000);
    TimeSpan ts2 = new TimeSpan(4, 8, 1);

    Console.WriteLine(ts.Add(ts2)); // Output: 3.11:16:11
    Console.WriteLine(ts2.Subtract(ts)); // Output: -3.03:00:09

```