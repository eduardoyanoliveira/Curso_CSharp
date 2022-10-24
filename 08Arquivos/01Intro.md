# Manipulação de Arquivos

&nbsp; No dia a dia da programação é comum deparar-se com a necessidade de manipular ou criar arquivos.Arquivos podem ser usados como sistema de logos, relatórios,etc.

&nbsp; Para manipular arquivos em C# deve-se utilizar ou a classe File ou a classe FileInfo. Abaixo apresenta-se uma introdução sobre ambas.

## File 

&nbsp; A classe File trata-se de uma classe estática, logo não é necessário a instanciação de um objeto para trabalhar com a classe File. Entretanto, esta classe exige mais computação do sistema.

### Métodos

- create => Cria um arquivo.
- copy => Copia um arquivo.
- delete => Deleta um arquivo.
- move => Move um arquivo.
- open => Abre um arquivo.

## FileInfo

&nbsp; A Classe FileInfo por sua vez deve ser instanciada, porém possui maior performance do que a classe File. Deve ser utilizada principalmente para processo mais complexos. A classe FileInfo possui os mesmos métodos da classe File.
