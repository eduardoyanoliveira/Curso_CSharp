# DateTime

&nbsp; Na rotina de desenvolvimento de uma software, por vezes é necessário controlar dados do tipo data. Por exemplo: data de emissão de um relatório, data de venda, data de compra, etc. No caso o DateTime representará um instante. 

&nbsp; Para armazenar datas em C# utiliza-se  o tipo de dado DateTime, que por sua vez, trata-se de um tipo "struct". <br>

&nbsp; O tipo struct será abordado em seções futuras, mas no momento, é necessário entender que um tipo struct deve ser instânciado na sua declaração, e para que isto ocorra é necessário que o programador utilize a palavra "new" ao criar uma variável deste tipo.

### Exemplo

&nbsp; Ao Criar uma nova variável do tipo data sem nenhum parâmetro como é mostrado abaixo, a data armazenada na variável será a primeira hora da época moderna.

```csharp
    DateTime d = new DateTime();

    Console.WriteLine(d.ToString());
    // Output: 01/01/0001 12:00:00 AM
```

## Datas com parâmetros no construtor

&nbsp; Ao utilizar a palavra "new" para criar uma nova variável apartir de uma classe ou o tipo struct será dito que um novo objeto do tipo em questão foi instânciado. Neste caso o tipo será o DateTime. E ao instânciar certas classes e structs é possível enviar parâmetros na sua criação (construção) para definir como exatamente o valor da variável será criado.

&nbsp; No caso do DateTime é possível passar os valores do ano, mês, dia, hora, minuto, segundo que a data representará através do construtor.Também é importante salientar que todos estes parâmentros são do tipo int.

### Exemplo:

```csharp
    DateTime d = new DateTime( 2022, 01, 01);
    Console.WriteLine(d.ToString()); // Output: 01/01/2022 12:00:00 AM
```

&nbsp; No exemplo acima coma as informações refenrente a hora não foram informadas, a data será gerada com a hora padrão de "12:00:00 AM".

### Exemplo com horas

```csharp
    DateTime d = new DateTime( 2022, 01, 01, 07, 45, 30);
    Console.WriteLine(d.ToString()); // Output: 01/01/2022 07:45:30 AM

```

## Builders

&nbsp; Além de construtures como visto acima, classes e structs em C# possuem métodos e propriedades estáticas chamadas de builders.<br>
&nbsp; Um método ou propriedade estática podem ser acessados através do nome da classe ou struct sem necessidade  da instânciação de um objeto. Isto é, não é necessário utilizar a palavra reservada "new". <br>
&nbsp; Os builders por sua vez, são métodos e propriedades utilizados para criar um novo objeto da classe, tal como os construtores.

* ## DateTime.Now

&nbsp; O DateTime.Now é uma propriedade que retornará o valor atual do sistema.

### Exemplo

```csharp
    DateTime now = DateTime.Now;
    Console.WriteLine(now); // Output: Hora e data atual
```

* ## DateTime.Today

&nbsp; O DateTime.Now será o valor da data atual.

### Exemplo

```csharp
    DateTime now = DateTime.Today;
    Console.WriteLine(now); // Output: data atual
```

* ## DateTime.Parse

&nbsp; O DateTime.Parse é um método que receberá uma data em formato de string e transformará a mesma em um valor do tipo DateTime.

### Exemplo

```csharp
    DateTime d = DateTime.Parse("12-10-1998");
    Console.WriteLine(d); // Output: 12/10/1998 12:00:00 AM

    DateTime d2 = DateTime.Parse("2000-08-15 13:05:58");
    Console.WriteLine(d2); // Output: 15/08/2000 01:05:58 PM
```

* ## DateTime.ParseExact

&nbsp; Tal como o DateTime.Parse, o DateTime.ParseExact é um método que receberá uma data em formato de string, porém além disto, receberá como segundo parâmetro a máscara de formatação desejada para data. Isto é, o formato que a data deve ser interpretada.

### Exemplo

```csharp
    using System.Globalization;

    DateTime d = DateTime.ParseExact("1998/12/10", "yyyy/mm/dd", CultureInfo.InvariantCulture);
    Console.WriteLine(d); // Output: 10/01/1998 12:12:00 AM
```

&nbsp; O exemplo acima utiliza a obrigatóriamente a propriedade "CultureInfo.InvariantCulture" para evitar destorções de fuso horários.


## Propriedades do tipo DateTime

* Day (int) => Extrai o dia da data
* DayOfWeek (DayOfWeek) => Extrai o dia da semana (Exemplo: Domingo = 0, Segunda = 1)
* DayOfYear (int) => Extrai o dia do ano da data ( Exemplo: 220)
* Month (int) => Extrai o mês
* Year (int) => Extrai o ano
* Hour (int) => Extrai a hora
* Minute (int) => Extrai os minutos
* Second (int) => Extrai os segundos
* TimeOfDay (TimeSpan) => Extrai a hora do dia
* etc

## Métodos de formatação

&nbsp; Os métodos de formatação são utilizados para transformar a data é um formato específico, para que a mesma possa ser apresentada.

### Exemplo: ToLongDateString

```csharp
    using System.Globalization;

    DateTime d = DateTime.ParseExact("1998/12/10", "yyyy/mm/dd", CultureInfo.InvariantCulture);
    Console.WriteLine(d.ToLongDateString()); // Output: sábado, 10 de janeiro de 1998
```

### Exemplo: ToLongTimeString

```csharp
    using System.Globalization;

    DateTime d = DateTime.ParseExact("1998/12/10", "yyyy/mm/dd", CultureInfo.InvariantCulture);
    Console.WriteLine(d.ToLongTimeString()); // Output: 12:12:00 AM
```

&nbsp; Acima são apresentados apenas alguns exemplos dos métodos de formatação de data. Além de outros métodos não apresentados nos exemplos, também é possível utilizar o método ToString passando como parâmetro a máscara de formatação desejada.

### Exemplo: Com máscara de formatação

```csharp
    using System.Globalization;

    DateTime d = DateTime.ParseExact("1998/12/10", "yyyy/mm/dd", CultureInfo.InvariantCulture);
    Console.WriteLine(d.ToString("yyyy-MM-dd HH:mm:ss")); // Output: 1998-01-10 00:12:00
```

## Operações com datas

&nbsp; Ainda é possível realizar operações com datas, como:

* Add(timeSpan) => Adiciona duração a data (tempo)
* AddHours(double) => Adiciona horas
* AddMinutes(double) => Adiciona minutos
* AddSeconds(double) => Adiciona segundos
* AddDays(double) => Adiciona dias
* AddMonths(int) => Adiciona meses
* AddYears(int) => Adiciona anos
* etc

### Exemplo

```csharp
    using System.Globalization;

    DateTime date = DateTime.ParseExact("21/02/2007", "dd/MM/yyyy", CultureInfo.InvariantCulture);
    DateTime newDate = date.AddDays(2.0);

    Console.WriteLine(newDate); //Output: 23/02/2007 12:00:00 AM
```

&nbsp; Utilize o método Subtract para retornar a diferença entre duas datas. A diferença retornada será apresendata em milesegundos com o tipo TimeSpan.<br>

&nbsp; O tipo TimeSpan será apresentado no próximo artigo.

### Exemplo

```csharp
    using System.Globalization;

    DateTime dateOne = DateTime.ParseExact("21/02/2007", "dd/MM/yyyy", CultureInfo.InvariantCulture);
    DateTime dateTwo = DateTime.ParseExact("13/01/2000", "dd/MM/yyyy", CultureInfo.InvariantCulture);

    TimeSpan time = dateOne.Subtract(dateTwo);

    Console.WriteLine(time); // Output: 2596.00:00:00

```
