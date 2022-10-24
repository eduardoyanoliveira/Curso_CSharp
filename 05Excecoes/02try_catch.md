# Try Catch, Tratando exceções

&nbsp; Ao ser lançada uma exceção o programa irá interromper sua execução, de tal forma que o usuário não consiguirá realizar mais nenhuma operação. Para evitar que isto aconteça, o programador deve estar conciente que a exceção pode acontecer em determinado momento de código e tratá-la.

&nbsp; Para tratar um exceção o deve-se utilizar a estrutura de código try-catch da seguinte forma:

1º Utilize a palavra reservada "try" seguida de um bloco de código indicado por chaves.

2º Dentro do bloco try deve ser inserido o código em que uma determinada exceção pode ocorrer.

3º Encadeado ao bloco try deve-se utilizar a um bloco iniciado com a palavra "catch". O bloco catch receberá entre parênteses uma variável de controle com o tipo da exceção que se espera que aconteça.

4º Dentro do bloco catch deve-se inserir o código a ser executado caso o erro aconteça.

### Exemplo

&nbsp; O programa a seguir solicita dois números para o usuário para efetuar uma divisão. Caso o usuário informe o divisor como zero, o programa tratará a exceção retornando uma mensagem ao usuário de operação inválida.

```
    System.Console.WriteLine("Digite um número para ser o dividendo: ");
    int numb1 = int.Parse(Console.ReadLine());

    System.Console.WriteLine("Digite o valor do divisor: ");
    int numb2 = int.Parse(Console.ReadLine());

    try
    {
    Console.WriteLine($"O resultado da divisão é {numb1 / numb2}");
    }
    catch (System.DivideByZeroException e)
    {
        System.Console.WriteLine($"Operação inválida: {e.Message}");
        // Output: Operação inválida: Attempted to divide by zero.
    }
```

&nbsp; O bloco catch pode ser encadeado com outros blocos catch caso exista mais de um tipo de erro que o código possa gerar.


## finally

&nbsp; O Bloco finally é deve ser inserido ao final do encadeamento de blocos catch e será responsável por executar um código que deve ser executado caso ocorra ou não erro.<br>
&nbsp; O bloco finally é comumente utilizado em operaçõe de Input e Output que involva componentes externos ao .Net, porque para realizar este tipo de operação deve-se abrir uma conexão com o destino da operação, como banco de dados e arquivos.Entretanto, caso o programador não finalize a conexão ao termíno da operação um erro será gerado no programa.