# Herança

&nbsp; O paradigma de programação orientada a objetos tem como um dos seus quatro pilares a herança. Esta que nada mais é que um relacionamento entre classes. 

## Relação

&nbsp; No relacionamento da herança uma subclass (classe filha) herda membros de uma superclass (classe mãe), permitindo que a subclasse implemente comportamento diferente para métodos da superclass (override) e que também extenda membros.Isto é, a subclass pode possuir características intrínsecas não compartilhadas com a superclass.

&nbsp; Um classe pode ser herdada por mais de uma subclass e ambas a subclass e a superclass são classes comuns em C#, porém a subclass conta com o advento de herdar ourtra classe.

&nbsp; A subclasse não altera o comportamento da superclasse, apenas o comportamento de métodos herdados dentro da própria subclass.(polimorphismo)

### Exemplo

&nbsp; Para que um relacionamento de herança seja configurado deve existir classes com características intrínsecas compartilhadas em um grau de hierarquia.<br>
&nbsp; Para que o entendimento seja facilitado é possível observar um exemplo do mundo real, como a herança entre animais. 

- Sistema de análise de evolução animal feito utilizando herança.

    - Deve possuir uma classe base Animal contendo todas as características intrínsecas compartilhadas entre todos animais. como: (Emitir som, alimentar-se, Locomover-se, espécie, peso, altura, etc).

    - Por tratar-se de um sistema de herança, o memso também deve conter classes especializadas (classes filhas) que herdam da classe Animal (classe mãe). Como por exemplo: (Felinos, Caninos, Répteis, Aves, etc).

    - A herança ainda permite que a criação de uma árvore de relacionamentos. Isto é, que uma classe herde de uma classe que já herdou de outra classe. Como (Animal -> Felinos -> Gato Doméstico | Animal -> Caninos -> Lobo)

    - No conceito apresentado acima de árvore de herança. A cada nova classe será atribuído novas características intrínsecas. Ex:
        * Animal:  (Emitir som, alimentar-se, Locomover-se, espécie, peso, altura)
        * Animal -> Aves (Todas as características do Animal + Voar) // Este é apenas um exemplo. Nem todas aves voam.
        * Animal -> Aves -> Patos (Todas as características da classe Aves + Nadar)

Obs: No exemplo acima a classe Animal é uma classe abstrata e não deve ser instanciada. (O tópico de classes abstratas será abordado em artigos posteriores).

&nbsp; Abaixo será apresentado a construção do exemplo de herança de Bird(Ave) até a classe Duck(Pato).

```csharp
    Duck duck = new Duck("Cinza", 3.0, 0.40);

    duck.Feed(); // Output: A ave está se alimentando
    duck.Swim(); // Output: O Pato está nadando

    class Bird {
        public double Weight {get; set;}
        public double Height {get; set;}

        public Bird(double weight, double height){
            Weight = weight;
            Height = height;
        }

        public void Feed(){
            Console.WriteLine("A ave está se alimentando");
        } 
    }

    class Duck : Bird {

        public string Color {get; set;}
        public Duck(string color, double weight, double height): base (weight, height) {
            Color = color;
        }

        public void Swim(){
            Console.WriteLine("O Pato está nadando");
        }
    }
```

&nbsp; No exemplo acima é possível notar que:

1º A sintaxe utilizada para sinalizar ao compilador que uma classe herda de outra é a mesma usada para mostrar que uma classe implementa uma interface. (Dois pontos seguidos do nome da classe)

2º A Classe Duck especializa a classe Bird adicionando uma nova proprieade Color e um novo método Swim.

3º Na herança é possível aproveitar o construtor da classe mãe utilizando a palavra reservada "base" da mesma forma que a palavra "this" é utilizada para aproveitar um construtor da mesma classe.

### Obs:

&nbsp; A herança é categorizada como um tipo de relacionamento "é um". Utilizando o exemplo acima pode-se dizer: "Um pato é uma ave".

## Upcasting

&nbsp; Por conta da herança ser uma relação "é um", pode-se realizar o upcasting entre as classes. Isto é, uma subclasse pode ser instanciada com o tipo da superclasse.

### Exemplo

&nbsp; No exemplo abaixo a subclass Duck é instanciada com o tipo Animal


```csharp
    Animal duck = new Duck("Cinza", 3.0, 0.40);

    duck.Feed(); // Output: A ave está se alimentando

    class Bird {
        public double Weight {get; set;}
        public double Height {get; set;}

        public Bird(double weight, double height){
            Weight = weight;
            Height = height;
        }

        public void Feed(){
            Console.WriteLine("A ave está se alimentando");
        } 
    }

    class Duck : Bird {

        public string Color {get; set;}
        public Duck(string color, double weight, double height): base (weight, height) {
            Color = color;
        }

        public void Swim(){
            Console.WriteLine("O Pato está nadando");
        }
    }
```
