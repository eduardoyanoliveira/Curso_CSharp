# Mais regras de nomeação

## Nomes passéveis de busca

&nbsp; Nomes devem ser passíveis de busca. Nomes de uma só letra podem se tronar um grande problema ao tentar encontrá-los em um escopo muito grande.O tamanho do nome deve ser proporcional ao tamanho de seu escopo.

&nbsp; Outro exemplo são constantes não atribuídas a variáveis. o número 7 não significa nada e é quase impossível de ser encontrado, por outro lado a variável constante Max_Product_Quantity_Per_Order é facilmente interpretada e encontrada em uma pesquisa.

## Uma palavra por conceito

&nbsp; Deve-se escolher uma palavra por conceito abstrato e continuar com a mesma. Por exemplo, o uso de fetch,retrieve e get como métodos equivalentes de classes diferentes. Como lembrar qual método pertence a cada classe?

&nbsp; É estritamente importante manter as convenções de nomes utilizados na aplicação. Tais convenções facilita o uso e manutenção do código por programadores da aplicação, tal como a adesão de novos programadores ao código.

## Uma palavra deve possuir apenas um sentido

&nbsp; Um exemplo de palavra com sentido multiplos é o uso da palavra Log como método em várias classes para retornar o log de alteração do objeto, e o uso da mesma palavra Log como método em uma classe específica utilizada para printar o objeto na tela. Neste caso deve-se utilizar uma palavra diferente como Print para o método da classe que printa o objeto na tela.

## Deve-se utilizar nomes a partir do Domínio da solução

&nbsp; Os nomes do domínio da solução são nomes em qual os programadores estão familiarizados, tornando o entendimento do código simples, pois não será necessário que o programador contate um especialista do domínio para entender certo nome.Portanto deve-se preferir o uso de termos de Informática, nomes de algoritimos, nomes de padrões, termos matemáticos, etc.

## Nomes de domínio do problema

&nbsp; Caso não seja possível a utilização de nomes do domínio da solução, deve-se utilizar nomes do domínio do problema. De tal forma, o programador ao menos poderá contatar um especialista no domínio para esclarecer tais nomes.

## Contextos significativos

&nbsp; Para facilitar o entendimento de certo nomes, normalmente tais nomes são colocados dentro de métodos, classes e namespaces coesos. Entretanto, muita das vezes não é possível que um nome esteja fisícamente em um contexto adequado. Para adcionar um contexto a um nome pode-se utilizar um prefixo. 

### Exemplo

&nbsp;O nome da variável <i>description</i> por se só não diz nada, porém ao adicionar o prefixo "prod" é possível inferir que a variável trata-se da descrição do produto. (<i>prodDescription</i>)

&nbsp; É importante resaltar que a adição de contextos desnecessários deve ser evitada. Utilizando o exemplo acima, caso a variável <i>description</i> já estivesse dentro da classe Product, adicionar o prefixo "prod" apenas poluiria o código. 

