# Exceptions (Exceções)

&nbsp; Exceções em C# refere-se a erros que acontecem em tempo de execução de uma aplicação. Normalmente estes erros são resultado que ações do desenvolvedor ou do usuário da aplicação.

## Características

- No .Net, exceção é um objeto herdado da classe System.Exception.

- Uma Exceção será propagada na pilha de métodos até o ponto de entrada do programa.

    - Linguagens como C#, Java, Node utilizam em sua arquitetura uma área chamada callstack, onde cada método executado chamará outro método e assim por diante, resultando em uma pilha.Na pilha de métodos o ultimo método será o primeiro a ser executado no sistema e para que a execução do mesmo termine todos os métodos acima na pilha devem retornar.


## Exceções do .Net

&nbsp; As exceções do .Net, são classificadas como SystemExceptions. Isto é, erros lançado por conta de algum erro do programador, como por exemplo:

- IndexOutOfRangeException => Acontece quando o pragama tenta acessar um índice inexistente em uma lista(List) ou array.

- DivideByZeroException  => Acontece quando o programa tenta dividir um número por zero.

&nbsp; É importante observar que qualquer tipo de exceção deve terminar com o sufixo Exception, para que facilitar o entendimento de que se trata de uma exceção.

## Exceções da Aplicação

&nbsp; Exceções da aplicação são exceções customizadas criada pelo programador, as mesmas devem ser do tipo ApplicationException.