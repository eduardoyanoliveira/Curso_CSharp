# Compilação vs Interpretação:

&nbsp; Ao escrever um programa, o desenvolvedor cria arquivos de código fonte, tais códigos que não são compreendidos pelo computador. Para que o computador entenda os comandos passados pelo programador, o código fonte deve ser transcrito para a linguagem compreendida pela máquina. <br>
&nbsp; Exitem duas Formas muito comuns para transformar o código fonte em um código de máquina a <strong>Compilação</strong> e a <strong>Interpretação</strong>.

* ## Compilação:

&nbsp; A compilação sempre involverá um compilador que transformará o arquivo do código fonte de uma linguagem de alto nível em um arquivo de código equivalente que é entendido pelos processadores.<br>
&nbsp; Uma outra forma de entender este processo é pensar é um exemplo do mundo real, onde um arquivo é escrito por um falante de alemão por exemplo (neste caso o programador), que irá iniciar o processo de tradução (compilação) enviando o arquivo para um tradutor (compilador) que transcreverá o arquivo para uma linguagem entendida pelo leitor (processadores). 

### Como funciona a compilação?

O compilador cumprirá duas funções para realizar o processo de compilação:<br>
    
    - Análise: Entender a estrutura e o significado que estará      descrito por uma linguaguem de alto nível.
    
    - Síntese: O compilador irá sintetizar o código para uma linguagem de baixo nível ( como assembly ou código de máquina), ou seja, irá de fato traduzir o código.

Ao final do processo de compilação, um arquivo executável ou uma biblioteca será gerada pelo compilador. 

#### Obs:

&nbsp; No processo de compilação o código pode ser reorganizado e aprimorado para que o processo de síntase seja feito de maneira otimizado. No entanto o código do arquivo criado pelo programador nunca será alterado. (As alterações ocorrem em tempo de compilação).


* ## Interpretação:

&nbsp; A Interpretação por sua vez utiliza um interpretador, que também é um programa que auxilia no processo de traduzir o código de alto nível para uma linguagem de alto nível. Porém, ao contrário do compilador que realiza o processo de uma vez só quando o programador executa a compilação, o interpretador realizará a tradução durante a execução da solução (programa).

## Principais diferenças entre Compilação e Interpretação.

* A Compilação gerá um arquivo executável compreendido pelo sistema operacional. Logo a máquina que executará o programa não necessitará da instalação da linguagem de programação.

* Ao compilar um programa, o arquivo executável gerado pelo mesmo somente será compatível com o OS (sistema operacional) atual. Para executar o programa em outro OS será necessário compilá-lo novamente para o OS desejado.

* Já o interpretador, pela sua natureza, atua de forma independente, não sendo necessária a mudança, ou seja, você pode ter qualquer OS. Basta ter o programa instalado na máquina que ele fará a tradução sem maiores problemas.

* A compilação destaca-se pela velocidade na execução, uma vez que o arquivo executável já está escrito em uma linguagem entendida pela máquina.

* Por possuir diversas etapas de validação e otimização, a compilação tende a reduzir o número de falhas na execução.

* Pelo Interpretador operar em runtime (Tempo de execução), ele permite que o desenvolvedor consiga modificar estruturas existentes em tempo de execução.


### Exemplos de linguagens compiladas:

- C
- C++

### Exemplos de linguagens interpretadas:

- PHP
- JavaScript
- Python

#### Sumário:

* Linguagem de alto nível: Linguaguems que aproximam-se das linguagens usadas pelo ser humano. Exemplos (Python, C#, JavaScript).

* Linguagem de baixo nível: Linguaguems que são de difícil compreensão pelo o ser humano, porém são entendidas pelas máquinas.

