# Programação orientada a objetos (Classes)

&nbsp; A Programação orientada a objeto é um paradigma de programação presente em varias linguagens de programação.<br>
&nbsp;A base para este paradigma é a criação de classes para definir objetos do mundo real dentro da programação.

## Classe

&nbsp; Um classe normalmente será definida como um molde de uma entidade (como: Cliente, Pedido, etc). Entretanto, classes podem ser utilizdas para descrever muito mais do que entidades. <br>

### Exemplo:

&nbsp; Um programra precisa representar  uma ou mais pessoas. Para isto é craido uma classe contendo todos os atributos "propriedades" que uma pessoa tenha, exs: nome, idade, altura. Agora sempre que necessário criar uma nova pessoa, utiliza-se a classe.

Obs: <br> 
- Para declarar propriedades dentro de uma classe que podem ser acessadas fora da mesma, deve-se utilizar a palavra public. <br>

- A classe deve ser definida no final do código, caso a esteja no mesmo arquivo que o código que ira utilizá-la.

```csharp
    Person p1, p2;
    p1 = new Person();
    p1.name = "Yan";
    p1.age = 24;
    p1.height = 1.71;

    p2 = new Person();
    p2.name = "Maria";
    p2.age = 22;
    p2.height = 1.65;

    class Person{
        public string name;
        public int age;
        public double height;
    };

```

&nbsp; O exemplo acima mostra de maneira clara que as variáveis criadas apartir da classe Person serão do tipo Person. Outra característica importante das classe é que para criar uma variável do tipo de uma classe é necessário utilizar a palavra "new" para instanciar um novo objeto da classe. <br>

&nbsp; Para facilitar o entendimento, pode-se referir a cada classe como uma fábrica, que produz objetos semelhantes com as mesmas características e funcionalidades. E que cada objeto é uma instância da class.<br>

## Acesar valores de um objeto

&nbsp; Ainda no exemplo acima, torna-se claro que para acessar uma propriedade do objeto é utilizado a notação de ponto ".". Além de utilizar a mesma para atribuir valores como o exemplo mostra, é possível acessar os valores.

```csharp

    Person p1, p2;
    p1 = new Person();
    p1.name = "Yan";
    p1.age = 24;
    p1.height = 1.71;

    p2 = new Person();
    p2.name = "Maria";
    p2.age = 22;
    p2.height = 1.65;

    Console.WriteLine($"Meu nome é {p1.name}, minha idade é {p1.age} anos e minha altura é {p1.height} cm");
    // Output: Meu nome é Yan minha idade é 24 anos e minha altura é 1.71 cm.

    class Person{
        public string name;
        public int age;
        public double height;
    };

```

## Sintexe Alternativa

&nbsp; Também é possível instanciar um objeto da classe utilizando uma sintaxe alternativa que permite informar o valor das propriedades direto na instanciação.

### Exemplo

```csharp

    Person p1 = new Person {name = "Yan", age = 24, height= 1.71};

    Console.WriteLine($"Meu nome é {p1.name}, minha idade é {p1.age} anos e minha altura é {p1.height} cm");
    // Output: Meu nome é Yan minha idade é 24 anos e minha altura é 1.71 cm.

    class Person{
        public string name;
        public int age;
        public double height;
    };

```

## Comportamento da memória

&nbsp; No exemplo acima é possível analisar que as variáveis p1 e p2 são primeiramente declaradas e depois instanciadas. Também é citado, que uma variável de um tipo classe precisa ser instanciada. Isto ocorre porque ao declarar a variável, a mesma é alocada em uma area da memória chamada <strong> <i> Stack </i> </strong> responsável por armazenar variáveis estáticas. Entretanto os objetos de uma classe não são valores estáticos, e sim valores compostos com diversas propriedades e métodos. Logo também é necessário armazenar este valor composto na memório, o que é feito no momento da instanciação do objeto. O valor composto por sua vez não pode ser armazenado na memória <strong> <i> Stack </i> </strong>, então o mesmo será armazenado em outro espaço da memória chamado <strong> <i> Heap </i> </strong>. <br>

&nbsp; Por final, é possível analisar que a variável que representa uma instância de uma classe será armazenada no <strong> <i> Stack </i> </strong> como o valor de um endereço na memória <strong> <i> Heap </i> </strong>. Logo, pode-se afirmar que a variável aponta para um endereço na memória onde está armazenado o objeto (instância), e por conta deste comportamento a variável é chamada de ponteiro, por apontar para o endereço.

