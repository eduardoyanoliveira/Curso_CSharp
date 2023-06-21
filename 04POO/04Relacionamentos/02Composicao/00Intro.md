# Coposition (Composição)

&nbsp; A Composição é um relacionamento na programação orientada a objetos onde um objeto se relaciona com outro objeto de outra classe. Na prática uma propriedade de uma classe vai ser do Tipo de outra classe ou interface.

### Exemplo

&nbsp; O exemplo abaixo mostra como a classe Author(Autor) é composta pela classe Pen(Caneta).Neste caso um autor precisa de uma caneta para escrever. Logo, uma instância de caneta  deve ser passada na instâciação de um autor.

```csharp

    Pen pen = new Pen("Bic", "Preta");
    Author author = new Author("Yan", pen);

    author.Write(); // Output: Yan está escrevendo com a caneta da marca Bic e cor Preta.

    class Pen {

        public string Brand {get; private set;}
        public string Color {get; private set;}

        public Pen(string brand, string color){
            Brand = brand;
            Color = color;
        }
    }

    class Author{

        public string Name {get; private set;}
        public Pen Pen {get; set;} 

        public Author(string name, Pen pen){
            Name= name;
            Pen = pen;
        }
        public void Write(){
            Console.WriteLine($"{Name} está escrevendo com a caneta da marca {Pen.Brand} e cor {Pen.Color}.");
        }

    }
```

## Composição com interface

&nbsp; No exemplo acima é possível dizer que a classe Author está fortemente acoplada a classe Pen. Isto causa um problema muito grave, porque alterações na classe Pen, podem causar efeitos colaterais na classe Author. Logo o desenvolvedor terá que persistir as alterações de Pen em Author.<br>

&nbsp; O problema de acoplamento (coupling) quebra os pricípios responsabilidade única(Single responsibility) e inversão de dependência (Dependency inversion). Para resolver este problema e deixar o código ainda melhor arquitetado é possível utilizar uma interface no lugar da classe pen.

- Existe uma regra na programação que diz que sempre é melhor depender de uma interface do que implementações.

&nbsp; Com a interface será possível uma composição agnóstica a implementação, permitindo assim que uma classe independa da outra.

### Exemplo

&nbsp; O exemplo abaixo mostra um sistema de vendas onde para criar o pedido deve-se informar uma estratégia de frete que implemente a interface IShippingStrategy.

```csharp
    BaseShipping baseShipping = new BaseShipping(0.05);
    ShippingWithTaxes shippingWithTaxes = new ShippingWithTaxes(0.05, 100.0);

    Order oreder1 = new Order("Yan", 1000.00, baseShipping); // Output: Este pedido é do cliente Yan e seu valor total é 950
    Order order2 = new Order("Maria", 1000.00, shippingWithTaxes); // Output: Este pedido é do cliente Maria e seu valor total é 850

    Console.WriteLine(oreder1);
    Console.WriteLine(order2);

    interface IShippingStrategy {
        public double Calculate(double value);
    }

    class BaseShipping : IShippingStrategy
    {
        private double Percentage;

        public BaseShipping(double percentage) {
            Percentage = percentage;
        }

        public double Calculate(double value)
        {
            return value - value * Percentage;
        }
    }


    class ShippingWithTaxes : IShippingStrategy
    {
        private double Percentage;
        private double Taxes;

        public ShippingWithTaxes(double percentage, double taxes) {
            Percentage = percentage;
            Taxes = taxes;
        }
        public double Calculate(double value)
        {
            double result =  value - value * Percentage;
            result -= Taxes;

            return result;
        }
    }

    class Order {
        public string ClientName {get; set;}
        public double Total {get; set;}
        private IShippingStrategy _shippingStrategy;

        public Order(string clientName, double total, IShippingStrategy shippingStrategy){
            ClientName = clientName;
            Total = total;
            _shippingStrategy = shippingStrategy;
        }

        public double TotalWithoutShipping(){
            return _shippingStrategy.Calculate(Total);
        }

        public override string ToString()
        {
            return $"Este pedido é do cliente {ClientName} e seu valor total é {TotalWithoutShipping()}";
        }

    }
```

#### Obs

- No exemplo acima, ao substituir a composição por classe por uma interface, é utilizado a inversão de controle e injeção de depedência.

- O exemplo acima utiliza a palavra "strategy" porque sua implementação é basicamente a mesma do Strategy Design Pattern. 

- É uma boa prática de programação adotar a composição ao invés da herança, pois a composição aumenta a coesão do código(code cohesion) e diminue o acomplamento (coupling).
