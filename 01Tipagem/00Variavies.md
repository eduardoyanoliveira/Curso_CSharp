# O que são variáveis? 

&nbsp;No dia a dia da programação nos deparamos com diversos problemas, e por várias vezes precisamos de valores para resolve-los. <br>

## Exemplo: 

&nbsp; Precisa-se criar um programa que de acordo com o nome inserido pelo usuário, o mesmo retorne a palavra "oi" seguida pelo nome do usuário.<br>

## Entendendo o problema

&nbsp; Aqui o problema está entorno ao armazenamento do nome do usuário. Ao executar uma linha de código o computador não armazenará os valores que são inseridos (inputados) externamente. Após um breve análise deste problema torna-se claro a necessidade de armazenar temporariamente valores dentro de um programa.

## Armazenando valores

&nbsp; Na programação quando necessário o armazenamento de valores utiliza-se as variáveis. Variáveis podem ser entendidas como containers criados dentro da memória da máquina, onde cada container é responsável por armazenar um valor, que pode ou não variar. <br>

## Sintaxe (Como criar variáveis C#)

&nbsp; Uma variável é apenas um nome escolhido pelo programador que receberá um valor que pode ou não ser atribuido no momento da criação da variável. <br>
Para realizar uma atribuição o programador deve utilizar o sinal de igual, e no caso do C# para o compilador/interpretador identificar a variável a mesma deve ser antecedida pelo <i><strong>modificador de acesso</strong></i> e <i><strong>tipo</strong></i>.

### Ex:

```
    public int idade = 30;
```

### Obs:

    * Tipos e modificadores de acesso será abordados próximos artigos.

## Regras de Variáveis

&nbsp; A regra para nomear uma variável é que o nome dela sempre comece por uma letra ou _. No meio do nome podem-se usar números, mas não se devem usar caracteres especiais e também não pode ser uma palavra reservada. Entende-se por palavras reservadas os comandos do C# e que são facilmente identificadas quando digitadas, por ficarem da cor azul. Exemplos de palavras que não podem ser utilizadas são: if, for, while, string e etc.

## Como uma variável no C# funciona por trás dos panos?

    1º  Ao ser criada o computador reservará um espaço na memória com um endereço randômico e com o mesmo nome da variável.

    2º Ao ser inicializada (quando o valor é atribuído pela primeira vez), o computador armazenará no endereço da memória criada o valor.

    3º No processo de interpretação caso o interpretador identifique que a variável não está sendo referenciada em mais nenhum lugar do código, a mesma será excluída para liberar espaço na memória RAM. (Este processo é realizado pelo Garbage Collector)
          