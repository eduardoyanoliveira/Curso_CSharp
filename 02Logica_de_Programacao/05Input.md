# Entrada de dados/Input

&nbsp; O artigo 01 desta seção apresenta o conteúdo "Output", trata-se de métodos para retornar valor no console. Este artigo por sua vez ira se dedicar a explicar o Input, que na programação refere-se a entrada de dados pelo usuário do sistema.<br>

&nbsp; Para receber dados do sistema tal como no Output será necessário utilizar o métodos ReadLine() da clase Console. O método Console.ReadLine() permite que o desenvolvedor receba um valor através do console e atribuá-o imediatamente a uma variável.

&nbsp; Uma observação necessária é que todo valor recebido através do uso do método ReadLine() é automaticamente convertido para string. Logo caso necessário o desenvolvedor deve converter o valor para tipo primitivo desejado.

## Exemplo

```csharp
    Console.WriteLine("Digite seu nome: ");
    string name = Console.ReadLine();
    // O valor de name será o valor digitado pelo usuário

```
