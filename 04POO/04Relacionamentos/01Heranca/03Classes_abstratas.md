# Classes Abstratas:

&nbsp; Utilizando o conceito de herança pode ser cirado uma classe Animal que será especializada nas classes Cachorro e Gato. Neste caso a classe Animal pode ser um exemplo de classe abstrata, pois a mesma abstrai o conceito de ambas classes especializadas, mantendo características e ações compartilhadas pelas subclasses. Entretanto, a própria classe abstrata não possui características únicas o suficiente para que um objeto da mesma faça sentido dentro do programa.

## Características de classes abstratas


1º São classes que devem abstrair um conceito que será especializado, logo a mesma não deve
ser instânciada.

2º Podem possuir métodos abstratos, que são métodos que não possuem implementação.

- Métodos abstratos não são implementados está responsabilidade fica para subclasse. Utilizando o exemplo
da classe animal, pode-se criar um método abstrato <i>FazerBarulho</i>, porque todo animal faz barulho, entretanto cada
animal faz um barulho diferente. Logo toda subclasse de animal deve implementar o método <i>FazerBarulho</i>
de sua própria maneira.

## Classes Abstratas vs Interfaces

&nbsp; Tal como as interfaces, uma classe abstrata pode ser entendida como um contrato, pois, todas as classe que herdam de uma classe abstrata devem conter os membros da mesma e também implementar os métodos abstratos necessários. Entretanto, a classe abstrata pode conter implementações, isto é, métodos concretos.Enquanto interfaces não podem conter implementações.

## Sintaxe

&nbsp; Para criar uma classe ou método abstrato basta apenas utilizar a palavra reservada "abstract" na declaração. Deve-se lembrar que um método com a palavra abstract não pode possuir implementação em sua declaração.

Obs:

- Métodos abstratos também podem ser declarados dentro de classes não abstratas.

## Exemplo

&nbsp; No exemplo abaixo ambas as classe Dog e Cat que herdam da classe abstrata Animal, possuem sua própria implementação do método MakeNoise(FazerBarulho).

```csharp
    Dog puppy = new Dog("Rex", 4.5);
    Cat kitten = new Cat("Napoleão", 2.4);

    puppy.MakeNoise(); // Output: Rex está latindo
    kitten.MakeNoise(); // Output: Napoleão está miando
    abstract class Animal {

        public string Name {get; set;}
        public double Weight {get; set;}
        
        public Animal(string name, double weight){
            Name= name;
            Weight = weight;
        }

        public abstract void MakeNoise();
    }


    class Dog : Animal
    {

        public Dog(string name, double weight) : base(name, weight){}

        public override void MakeNoise()
        {
            Console.WriteLine($"{Name} está latindo");
        }
    }

    class Cat : Animal
    {

        public Cat(string name, double weight) : base(name, weight){}

        public override void MakeNoise()
        {
            Console.WriteLine($"{Name} está miando");
        }
    }
```

&nbsp; Apesar que no exemplo acima as subclasses não implementam novos métodos, ou possui propriedades para além das propriedades já herdadas. Um subclasse de uma classe abstrata pode sim possuir seus próprios membros. 

## Polimorfismo

&nbsp; O exmplo acima apresenta um tipo de polimorfismo, porque o método MakeNoise é polimorfico.Isto é, possui várias formas diferentes. 
