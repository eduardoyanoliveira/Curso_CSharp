# Ref & Value Types (Tipo referência e tipo valor)

* ## Tipo Referência

&nbsp; Tipo referência são tipos de variáveis que não armazenam o próprio valor na memória Stack e sim apontam para um endereço na memória Heap, como o exemplo do artigo anterior.

&nbsp; As variáveis do tipo referência são chamadas de ponteiro, por apontarem para um endereço de memória que não estão alocadas. 

### Características Tipo Referência

&nbsp; Um comportamento muito importante do tipo referência que deve ser compreendido é que, ao atribuir o valor de uma variável X usando o valor de outra variável Y cuja o tipo seja referência, o valor da variável Y não será copiado para a variável Y, o que acontecerá de fato é que X passará a apontar para o mesmo endereço na memória que Y. Logo, caso algo seja alterado em X, também será refletido em Y.

### Exemplo

```csharp
    Product p1, p2;

    p1 = new Product("Teste", 30.0);
    System.Console.WriteLine($"Variável p1: {p1}"); // Output: Variável p1: Produto: Teste, Preço: 30

    p2 = p1;
    p2.Name = "Novo Teste";
    System.Console.WriteLine($"Variável p2: {p2}"); // Output: Variável p2: Produto: Novo Teste, Preço: 30
    System.Console.WriteLine($"Variável p1: {p1}"); // Output: Variável p1: Produto: Novo Teste, Preço: 30

    class ProductException: ApplicationException{
        public ProductException(string message) : base(message){}
    }

    class Product {
        public string Name {get; set;}
        public double Price {get; set;}

        public Product(string name, double price){
            Name = name;
            Price = price;
        }

        public override string ToString()
        {
            return $"Produto: {Name}, Preço: {Price}";
        }

    }

```

&nbsp; Uma variável que seja do tipo referência, como uma classe por exemplo, pode não ser instanciada e apenas receber o valor null. Isto indicará que a variável não possui referência na memória Heap.

### Exemplo

```csharp
    Product p1;

    p1 = null;
```

&nbsp; Apenas no momento da instanciação do objeto o valor será alocado na memória Heap.


* ## Tipos Valor

&nbsp; Os tipos valor ao contrário do tipo referência possuem sua alocação direto na memória Stack. Em c# são comumente relacionado ao tipo "struct". Outros exemplos de tipo valor são os tipos primitivos, como int, double, string, etc.

### Características do Tipo Valor

&nbsp; Por conta do valor de uma variável do tipo valor ser alocada diretamente na memória Stack, quando seu valor é atribuído a outra variável apenas uma cópia será feita.Logo utlizando a mesma analogia do exemplo anterior, caso o valor de X seja alterado o valor de Y continuará o mesmo.

### Exemplo

```csharp
    double x, y;
    x = 20.4;
    y = x;

    System.Console.WriteLine($"O valor de X é {x}"); // Output: O valor de X é 20,4
    System.Console.WriteLine($"O valor de Y é {y}"); // Output: O valor de X é 20,4

    y = 30.0;

    System.Console.WriteLine($"O valor de X é {x}"); // Output: O valor de X é 20,4
    System.Console.WriteLine($"O valor de Y é {y}"); // Output: O valor de Y é 30
```

### Tipo valor customizado

&nbsp; Caso o desenvolvedor possa a necessidade é posssível em C# que seja criado um tipo valor customizado. Para realizar este processo basta utilizar o tipo "struct" em uma sintaxe muito parecida com a sintaxe das classes.O tipo struct até mesmo compartilha muitas funcionalidades da classe, como o método padrão override ToString. 

### Exemplo

&nbsp; O Exemplo abaixo mostra um tipo valor customizado criado para representar uma coordenada geográfica. Por ser um struct o valor da variável será armazenada diretamente na memória stack.

```csharp
    Coordenate teste = new Coordenate(-14.35, 10.37);
    System.Console.WriteLine(teste); // Output: Latitude:-14,35,Longitude:10,37

    struct Coordenate {
        public double Lat, Longi;

        public Coordenate(double lat, double longi){
            Lat = lat;
            Longi = longi; 
        }

        public override string ToString()
        {
            return $"Latitude:{Lat},Longitude:{Longi}";
        }
    }
```

## Principais diferenças entre Ref e Value

- Tipo value é mais peformático

- Tipo ref aceita valor null

- Tipo ref são removidos da memória pelo Garbage Collector em um momento próximo ao seu desuso.

- Tipo value são removidos imediatamente da memória no final de seu escopo.
