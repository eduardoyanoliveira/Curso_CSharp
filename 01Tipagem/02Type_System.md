# Type System

&nbsp; O Artigo anterior informa que as tipagens estão incumbidas a cada linguaguem que determinará como seu sistema de tipagem ou Type System funcionará. Ao analisar diferentes linguagens de programação é possível verificar alguns comportamentos comuns entre os Types System de cada linguagem.<br>

&nbsp; Alguns termos comumente utilizados para cartegorizar os sistemas de tipagens são:

    * Tipagem dinâmica
    * tipagem estática
    * Linguagem fortemente tipada
    * Linguagem fracamente tipada



## Tipagem dinâmica:

&nbsp; Tipagem dinâmica é nome utilizado para categorizar linguagens onde o tipo de dado não precisa ser infromado ao criar uma variável ou <i> objeto </i>.Isto só é possível porque a tipagem (type checking) é inferida em tempo de execução pelo interpretador.Logo, ao criar uma variável em Python ou JavaScript por exemplo e atribuir a mesma o valor 100 o interpretador irá inferir que trata-se de uma variável que armazena um numero inteiro.(int em Python e number em Javascript). <br>

&nbsp; A Tipagem dinâmica é normalmente utilizada em linguagens interpretadas.


## Tipagem estática:

&nbsp; A Tipagem estática categoriza linguagens onde o tipo de dado deve ser informado na declaração da variável. Uma das características da tipagem estática é que a mesma permite que o intelisense da IDE acuse erros durante o processo de desenvolvimento reduzindo a possibilidade de erros em tempo de execução.

## Fortemente tipada vs Fracamente tipada:

&nbsp; Linguagens de tipagem fraca fazem conversões entre tipos não relacionados implicitamente; enquanto que linguagens fortemente tipadas não permitem conversões implícitas entre tipos não relacionados.

## Tipagem em C#

&nbsp; C# é uma linguagem fortemente tipada. Cada variável e constante tem um tipo, assim como cada expressão que avalia um valor. Cada declaração de método especifica um nome, o tipo e o tipo (valor, referência ou saída) para cada parâmetro de entrada e para o valor de retorno. A biblioteca de classes .NET define tipos numéricos internos e tipos complexos que representam uma ampla variedade de construções. Isso inclui o sistema de arquivos, conexões de rede, coleções e matrizes de objetos e datas. Um programa C# típico usa tipos da biblioteca de classes e tipos definidos pelo usuário que modelam os conceitos específicos do domínio do problema do programa.

As informações armazenadas em um tipo podem incluir os seguintes itens:

    * O espaço de armazenamento que uma variável do tipo requer.
    * Os valores máximos e mínimos que ele pode representar.
    * Os membros (métodos, campos, eventos e assim por diante) que ele contém.
    * O tipo base do qual ele herda.
    * A(s) interface(s) que ele implementa.
    * Os tipos de operações que são permitidas.

O compilador usa informações de tipo para garantir que todas as operações executadas em seu código sejam de tipo seguro. Por exemplo, se você declarar uma variável do tipo int, o compilador permitirá que você use a variável em operações de adição e subtração. Se você tentar realizar essas mesmas operações em uma variável do tipo bool, o compilador gera um erro.