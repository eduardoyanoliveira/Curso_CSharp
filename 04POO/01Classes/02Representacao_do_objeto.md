# Representação do objeto

&nbsp; Ao criar um objeto apartir de uma classe o memso será representado pelo nome de sua classe quando por exemplo printado no console. Entretanto, muita das vezes, o programador deseja que o objeto seja representados por suas característacas. O que lhe torna único. <br>

&nbsp; Para sobscrever o comportamento padrão que retorna o nome da classe, pode-se utilizar a palavra reservada <i> override </i>. O conceito de override será abordado em próximos artigos, no entanto, uma simples definição pode facilitar a compreensão do override neste exemplo.

- Override é utilizado para sobscrever o comportamento de um método já existente. Normalmente um método presente em uma classe mãe.

&nbsp; A classe mãe referida na definição acima, neste caso será a classe Object, porque todas as classes em C# são filhas da classe object. (Este conceito é chamado herança e também será abordado posteriormente).

## Sobscrevendo o método ToString

&nbsp; O método que deve ser sobscrito para alterar a  representação de um objeto é o método ToString. Abaixo é possível analisar um exemplo com e um exemplo sem o método sobescrito.

### Exemplo: Sem ToString

```
    Animal lion = new Animal();
    lion.name = "Leo";

    Console.WriteLine(lion); //Output: "Animal"

    class Animal {
        public string name;
        
        public void Feed(){
            Console.WriteLine($"{name} está se alimentando.");
            return;
        }
    };

```

### Exemplo: com ToString

```
    Animal lion = new Animal();
    lion.name = "Leo";

    Console.WriteLine(lion); //Output: "meu nome é Leo"

    class Animal {
        public string name;
        
        public void Feed(){
            Console.WriteLine($"{name} está se alimentando.");
            return;
        }

        public override string ToString(){
            return $"meu nome é {name}";
        }
    };

```