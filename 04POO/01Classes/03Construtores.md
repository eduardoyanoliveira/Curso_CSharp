# Construtores (Constructors)

&nbsp; Até agora os exemplos dos artigos anteriores sobre classes, apresentam um modelo onde deve-se instanciar um objeto da classe e depois atribuir o valor de suas propriedades um à um. Entretanto, é possível utlizar construtures para atribuir os valores das propriedades no momento da instanciação do objeto.

&nbsp; O construtor deve ser declarado dentro da classe, e uma classe pode possuir mais de um construtor (sobrecarga).

&nbsp; Os construtores também podem ser utilizados para obrigar que o usuário da classe (programador) informe determinados valores na instanciação do objeto.

## Sintaxe

&nbsp; Para criar um construtor deve-se seguir os seguintes passos:

1º Normalmente os construtores são publicos, logo é necessário informar primeiramente a palara "public".

2° Informa-se o nome da classe seguido por parênteses.

3º Dentro dos parênteses, deve-se informar os parâmetros que serão resnponsáveis por receber o valor de cada propriedade.

4º Após os parênteses, abre-se o bloco de código do construtor, onde cada valor recebido nos parâmetros serão atribuídos as respectivas propriedades do objeto que está sendo instanciado.


### Exemplo:

&nbsp; Neste exemplo deve-se observar duas coisas:

    1º Apartir do momento que a classe possui um construtor, ao instanciar um novo objeto da classe será obrigatório que se informe os valores solicitados pelo construtor.

    2º Os pârametros do construtor não são iguais aos nomes das propriedades, pois não começam com letra maiúscula. Está diferenciação é utilizada para que o compilador entenda que os valores das propriedades estão sendo atribuídos conforme os valores recebidos no construtor.

```csharp
    Person p = new Person("Yan", 24, 1.71);

    Console.WriteLine(p); //Output: "meu nome é Yan, minha idade é 24 anos e minha altura é 1,71 cm"

    class Person {
        public string Name;
        public int Age;
        public double Height;
        
        public Person(string name, int age, double height){
            Name = name;
            Age = age;
            Height = height;
        }

        public override string ToString(){
            return $"meu nome é {Name}, minha idade é {Age} anos e minha altura é {Height} cm";
        }
    };

```

## Sobrecarga de construtores

&nbsp; A sobrecarga é uma técnica utilizada em C#, onde uma função pode receber uma quantidade de parâmetros (atributos) diferentes. Algumas vezes a sobrecarga também pode gerar um leve osilação no comportamento da função.

&nbsp; Para gerar uma sobrecarga de construtores basta declarar mais um construtor, recebendo entretanto uma quantidade de atributos diferentes.

### Exemplo

&nbsp; O Exemplo abaxo mostra uma classe Product onde se pode instanciar um produto, passando ou não sua quantidade. Isto ocorre porque um dos construtores não recebe o atributo quantidade.

```csharp
    Product prod1 = new Product("notebook", 2500.00, 3);
    Product prod2 = new Product("iPhone", 10000.00);

    Console.WriteLine(prod1); //Output: "Produto notebook, Preço: 2500, quantidade 3"
    Console.WriteLine(prod2); //Output: "Produto iPhone, Preço: 10000, quantidade 0"

    class Product {
        public string Name;
        public double Price;
        public int Quantity;
        
        public Product(string name, double price, int quantity){
            Name = name;
            Price = price;
            Quantity = quantity;
        }

        public Product(string name, double price){
            Name = name;
            Price = price;
            Quantity = 0;
        }

        public override string ToString(){
            return $"Produto {Name}, Preço: {Price}, quantidade {Quantity}";
        }
    };

```

&nbsp; É possível observar no exemplo acima que dentro do escopo do segundo construtor é atribuído manualmente o valor zero a propriedade Quantity. Entretanto, esta linha de código não é necessária, pois por padrão, quando não informado o valor a uma propriedade númerica de uma classe, será atribuído o valor zero.

## Construtor padrão

&nbsp; Para que sejá possível novamente instanciar um objeto sem passar os valores de suas propriedades no momento de sua instanciação, ou, para que seja possível utilizar a sintaxe alternativa de chaves para instanciar um objeto. Deve-se declarar um construtor padrão dentro da classe. Isto é, um construtor que não recebe atributos.


### Exemplo

```csharp
    Product prod1 = new Product();
    prod1.Name = "notebook";
    prod1.Price =  2500.00;
    prod1.Quantity = 3;

    Product prod2 = new Product{Name= "iPhone", Price= 10000.00, Quantity= 30};

    Console.WriteLine(prod1); //Output: "Produto notebook, Preço: 2500, quantidade 3"
    Console.WriteLine(prod2); //Output: "Produto iPhone, Preço: 10000, quantidade 30"

    class Product {
        public string Name;
        public double Price;
        public int Quantity;

        // Construtor padrão
        public Product(){

        }
        
        public Product(string name, double price, int quantity){
            Name = name;
            Price = price;
            Quantity = quantity;
        }

        public Product(string name, double price){
            Name = name;
            Price = price;
            Quantity = 0;
        }

        public override string ToString(){
            return $"Produto {Name}, Preço: {Price}, quantidade {Quantity}";
        }
    };

```
