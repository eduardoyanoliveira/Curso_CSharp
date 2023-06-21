# Properties

&nbsp; O Artigo anterior demonstra que é possível restringir o acesso a certas partes do código utilizando modificadores de acessos. Entretanto, por vezes, deseja-se impedir que outros desenvolvedores consigam alterar diretamento o valor de uma propriedade dentro de uma classe, mas permita que alterem indiretamente. Para resolver tal problema, pode-se utilizar o conceito de Property.<br>

## Definição 

&nbsp; Uma Property em c# substitui métodos get e set em outras línguagens. As properties Permitem criar uma interface que controla o acesso tanto de leitura, como de alteração de uma propriedade da classe.

## Casos de uso

&nbsp; Além do exemplo citado no começo do artigo, uma property pode ser utilizada para liberar o acesso apenas a leitura de uma propriedade.E outro forma de uso, é que as properties podem ser utilizadas para tratar o valor que uma propriedade recebe, podendo até restringir a alteração da propriedade, caso o valor não adeque-se a uma certa lógica.

### Exemplo


```csharp
    Product p1 = new Product("iPhone", 7000.00, 50);
    Console.WriteLine(p1); // Output: "Produto iPhone, Preço: 7000, quantidade 50"

    p1.Price = -1; // Error: De acordo com a Property set o valor do produto não pode ser negativo

    class Product {
        public string _name;
        private double _price;
        private int _quantity;

        public Product(string name, double price, int quantity){
            _name = name;
            _price = price;
            _quantity = quantity;
        }

        // Property Name
        public string Name{
            get { return _name;}
            set {
                if(value != null && value.Length > 0){
                    _name = value;
                };
            }
        }

        // Property Price
        public double Price{
            get { return _price;}
            set{
                if(value >= 0){
                    _price = value;
                };
            }
        }

        // Property Quantity
        public int Quantity{
            get { return _quantity;}
            set{
                if(value >= 0){
                    _quantity = value;
                };
            }
        }

        public override string ToString(){
            return $"Produto {Name}, Preço: {Price}, quantidade {Quantity}";
        }
    };
```

&nbsp; Caso seja necessário que uma propriedade da classe possa apenas ser lida, basta que se implemente apenas o "get" dentro da property.

&nbsp; Obs:

- No exemplo acima é possível observar que para que as Properties funcionem as propriedades da classe devem utilizar o modificador de acesso "private". Outra observação é que, por convenção em C#, ao criar uma propriedade como privada, seu nome deve começar com o caracter de underline e letra minúscula.

## Auto Property

&nbsp; Caso uma propriedade não possua uma lógica para sua alteração e seja necessário que a mesma seja protegida com uma Property, pdoe-se utilizar a Auto Property.

### Exemplo

&nbsp; No exemplo abaixo nota-se que, utlizando a Auto Property, a propriedade da classe utilizará o modificador de acesso "public". E que caso seja necessário criar uma propriedade apenas leitura, será utilizado o modificador de acesso "private" apenas no método "set" da Auto Property.

```csharp

    Person p = new Person("Yan", 24, 1.71);

    Console.WriteLine(p); //Output: "meu nome é Yan, minha idade é 24 anos e minha altura é 1,71 cm"

    class Person {
        public string Name {get; set;}
        public int Age {get; private set;} // O valor pode ser apenas lido
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

&nbsp; Ex:

- Como já citado acima, não é possivel utilizar Auto Property quando o método set possui uma lógica particular.
