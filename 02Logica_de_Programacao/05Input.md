# Entrada de dados/Input

&nbsp; O artigo 01 desta seção apresenta o conteúdo "Output", trata-se de metódos para retornar valor no console. Este artigo por sua vez ira se dedicar a explicar o Input, que na programação refere-se a entrada de dados pelo usuário do sistema.<br>

&nbsp; Para receber dados do sistema tal como no Output será necessário utilizar o metódos ReadLine() da clase Console. O metódo Console.ReadLine() permite que o desenvolvedor receba um valor através do console e atribuá-o imediatamente a uma variável.

&nbsp; Uma observação necessária é que todo valor recebido através do uso do metódo ReadLine() é automaticamente convertido para string. Logo caso necessário o desenvolvedor deve converter o valor para tipo primitivo desejado.

## Exemplo

```
    string name = Console.ReadLine("Digite seu nome: ");
    // O valor de name será o valor digitado pelo usuário

```