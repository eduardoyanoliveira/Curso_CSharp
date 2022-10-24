# Custom Exception (Exceção Customizada)

&nbsp; Exceções customizadas são criadas pelo próprios desenvolvedores da applicação para lançar erros que costumam estar ligados as regras do negócio.

## Sintaxe

&nbsp; Uma Exceção customizada deve ser uma classe que herda da classe ApplicationException e normalmente irá possuir um construtor recebendo a propriedade message(string) que será repassada para o construtor da superclass.

## Casos de uso

&nbsp; Alguns exemplos de usos de uma exceção customizada seriam:

- Um programa que precisa receber um valor como: taxa de frete, preço, quantidade no estoque. Estes valores não podem ser negativos, logo se o usuário inserir um valor negativo uma exceção deveria ser lançada.

- Programas que recebem datas como: reserva, entrega, vencimento. Estas datas não podem ser menor que a data atual. (teoricamente)

&nbsp; Acima está apresentado apenas alguns exemplos de casos de uso para exceções customizadas. Entretanto, existe uma infinidade a mais de casos de usos.

### Exemplo

&nbsp; O exemplo abaixo trata-se de um programa de cadastro de produtos onde a classe Product(produto) não pode aceitar que a propriedade preço seja negativa, ou que a propriedade nome possua menos que três caracteres.

```
    Product p1 = new Product("Test", -1.0);
    System.Console.WriteLine(p1);
    // Output: Unhandled exception. ProductException: Error: Preço do produto não pode ser negativo

    class ProductException: ApplicationException{
        public ProductException(string message) : base(message){}
    }

    class Product {
        public string Name {get; private set;}
        public double Price {get; private set;}

        public Product(string name, double price){

            if(name.Length < 3){
                throw new ProductException("Error: Nome do produto deve conter ao menos três caracteres");
            }

            Name = name;

            if(price < 0){
                throw new ProductException("Error: Preço do produto não pode ser negativo");
            }

            Price = price;
        }

        public override string ToString()
        {
            return $"Produto: {Name}, Preço: {Price}";
        }
    }
```

&nbsp; No exemplo acima caso o produto possua um nome contendo menos que três caracteres um erro também seria lançado.

