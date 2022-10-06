# Linguagens pré-compiladas:

&nbsp; O artigo anterior descreve a necessidade de transcrever um programa feito em linguagem de alto nível para linguagem de baixo nível para que o mesmo possa ser executado pelo processador. <br>
&nbsp; O mesmo artigo descreve duas formas de realizar o processo de tradução do código, a Compilação e a Interpretação. Todavia existe uma outra forma de realizar tal porcesso, forma está utilizada pelas linguagens C# e Java por exemplo. A abordagem referida neste caso seria a pré-compilação.

## Como funciona a pré-compilação?

&nbsp; Neste caso, o compilador irá gerar um arquivo agnóstico ao Sistema Operacional, permitindo que o mesmo sejá utilizado em qualquer OS. <br> 
&nbsp; O Arquivo gerado pelo compilador neste processo é chamado de Bytecode ou CIL (Common Intermediate Language).Para que o mesmo possa ser executado o computador deverá possuir a instalação de uma máquina virtual especifíca para o Sistema Operacional que fará o processo de execução do Bytecode. A máquina virtual é chamada de CLR (Common Language Runtime). No caso do C# será provávelmente o DOTNET CLR específico do Sistema Operacional.

### Obs:

A interpretação realizada pela máquina virtual é chamada de <i>Compilação Just-in-time</i>.

## Quais as vantagens da pré-compilação:

* O código será otimizado tal como no processo de recompilação.

* Não será necessário recompilar o código para rodar em um ambiente de execução diferente.