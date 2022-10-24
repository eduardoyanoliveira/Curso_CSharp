# Comparação entre objetos

&nbsp; Em certas ocasiões no dia a dia da progrmação, o desenvolvedor pode-se encontrar com a necessidade de comparar dois objetos de uma mesma classe, Por exemplo, para saber como uma lista de objetos deve ser ordenada, qual objeto foi criado primeiro, ou até para saber qual o objeto tem o maior valor de uma propriedade, como qual produto tem maior quantidade no estoque.

&nbsp; O Problema com as situações citadas acima é que, o programa não consegue saber por padrão como deve-se comparar dois objetos de uma classe. Em C# para adcionar esta funcionalidade a uma classe, a mesma deve implementar a interface IComparable.

### Exemplo

&nbsp; O Exemplo abaixo mostra um programa que vai ordernar uma lista de objetos Produto do menor preço para o maior.

```
    Product p1 = new Product("Tablet Samsung", 2200.00);
    Product p2 = new Product("Smartphone Mi 8", 1200.00);
    Product p3 = new Product("iPhone 12", 4500.00);
    Product p4 = new Product("Xbox Series S", 2500.00);
    Product p5 = new Product("Desktop Gamer Completo", 3700.00);
    Product p6 = new Product("Playstation 5", 5000.00);
    Product p7 = new Product("Smart Tv Samsung", 2800.00);
    Product p8 = new Product("MacBook", 7000.00);

    List<Product> products = new List<Product>();
    products.Add(p1);
    products.Add(p2);
    products.Add(p3);
    products.Add(p4);
    products.Add(p5);
    products.Add(p6);
    products.Add(p7);
    products.Add(p8);

    products.Sort();

    foreach(Product product in products){
        System.Console.WriteLine(product);
    }

    /* ---- Output ----

    Produto: Smartphone Mi 8, Preço: 1200
    Produto: Tablet Samsung, Preço: 2200
    Produto: Xbox Series S, Preço: 2500
    Produto: Smart Tv Samsung, Preço: 2800
    Produto: Desktop Gamer Completo, Preço: 3700
    Produto: iPhone 12, Preço: 4500
    Produto: Playstation 5, Preço: 5000
    Produto: MacBook, Preço: 7000

    */

    class Product : IComparable {
        public string Name {get; set;}
        public double Price {get; private set;}

        public Product(string name, double price){
            Name = name;
            Price = price;
        }

        public override string ToString()
        {
            return $"Produto: {Name}, Preço: {Price}";
        }

        public int CompareTo(object? obj)
        {
            Product? other = obj as Product;
            return Price.CompareTo(other.Price);
        }
    }

```

Obs: 

- O método List.Sort utilizado no exemplo acima obriga que a classe implemente a interface IComparable.

- Dentro do método CompareTo é utilizado o método de mesmo nome da propriedade Price, isto é possível porque o tipo double também implementa a interface IComparable.