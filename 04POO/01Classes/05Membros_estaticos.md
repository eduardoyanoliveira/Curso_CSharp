# Membros estáticos

&nbsp; Em C# membros estáticos refere-se a propriedades e métodos que estão dentro de uma classe, porém independem de uma instância. Isto é, no caso dos métodos estáticos, são procedimentos que a classe pode executar e que não mudaram em nada de acordo com a instância. No caso das propriedades estáticas, são valores comuns entre instâncias.

## Características

- Para utilizar um membro estático, deve-se utilizar o nome classe para acessar.

- Classes que possuem apenas membros estáticos podem ser declaradas como classes estáticas.Por sua vez uma classe estática não pode ser instanciada.

- Para referir-se a um membro estático deve-se utlizar a palavra reservada "static".

## Métodos estáticos

### Exemplo

&nbsp; O exemplo a seguir mostra uma classe estática Calc que representa uma calculadora simples. A classe possui métodos estáticos para performar operações matemáticas simples. Os métodos neste caso serão estáticos, porque os mesmos independem de propriedades de uma instância.

```csharp

    Console.WriteLine(Calc.Sum(10.0, 5.0)); // Output: 15.0
    Console.WriteLine(Calc.Subtract(10.0, 5.0)); // Output: 5.0
    Console.WriteLine(Calc.Times(10.0, 5.0)); // Output: 50.0
    Console.WriteLine(Calc.Division(10.0, 5.0)); // Output: 2.0

    static class Calc {

        public static double Sum(double numbOne, double numbTwo){
            return numbOne + numbTwo;
        }

        public static double Subtract(double numbOne, double numbTwo){
            return numbOne - numbTwo;
        }

        public static double Times(double numbOne, double numbTwo){
            return numbOne * numbTwo;
        }

        public static double Division(double numbOne, double numbTwo){
            if(numbTwo != 0) return numbOne / numbTwo;

            return 0.0;
        }

    }

```

## Propriedades estáticas

### Exemplo

&nbsp; Propriedades estáticas podem ser utilizadas para armazenar valores comuns entre instâncias. O Exemplo abaixo mostra uma classe Person que utiliza uma propriedade estática para armazenar a data atual, e através da mesma e a data de nascimento informada no construtor, calcula a idade da pessoa.

```csharp
    Person p1 = new Person("Yan", new DateTime(1998, 10, 12), 1.71);
    Console.WriteLine(p1); // Output: "meu nome é Yan, minha idade é 24 anos e minha altura é 1,71 cm"

    class Person {

        public static DateTime now = DateTime.Now;
        public string Name;
        public DateTime BirthDate;
        public double Height;
        
        public Person(string name, DateTime birthDate, double height){
            Name = name;
            BirthDate = birthDate;
            Height = height;
        }

        public int GetAge(){
            TimeSpan livingTime = now.Subtract(BirthDate);
            double age = (livingTime.Days / 360);
            return (int) age;
        }

        public override string ToString(){
            return $"meu nome é {Name}, minha idade é {GetAge()} anos e minha altura é {Height} cm";
        }
    };

```
