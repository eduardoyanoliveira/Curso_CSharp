# Encapsulamento

&nbsp; O encapsulamento é um dos quatro pilares da programação orientada a objetos, este pilar que diz que atributos, métodos e até classes devem serem protegidos do código que os utilizam.

&nbsp; Na Programação orientada a objetos linguagens como Java, C, e C# utilizam os modificadores de acesso a seguir para limitar o acesso a classes e membros de classes.

- public -> Permite que a classe, metódo, atributo seja acessado por todos.
- protected -> Acesso somente a própria classe e subclasses dentro ou fora do projeto.
- protected internal -> Acesso a todos, exceto classes de outro projeto.
- private protected -> Acesso apenas a própria classe e subclasses dentro do próprio projeto.
- internal -> Acesso a todos, porém apenas dentro do próprio projeto.
- private -> Acesso somente dentro da própria classe.

## Atributos

### Exemplo 

&nbsp;  Um programa possui uma classe Cliente, onde cada cliente (instâcia) possui um CPF. Neste caso é necessário previnir que o CPF de um cliente seja alterado, pois segundo a regra do sistema, ao invés de alterar o CPF de um cliente, caso necessário o usuário deve crirar outro cliente do zero. (Apesar de ser um exemplo está regra ajuda a eveitar varios problemas reias).

## Métodos

### Exemplo

&nbsp; Uma classe possui um metódo de criptografia, que ao salvar um cliente no banco de dados o sistema irá criptografa-ló
e a buscar o cliente no banco de dados a classe irá descriptográfa-ló. Porém ambos os metódos de criptografia e descriptograifa não devem ser mostrado a outros programadores que venham a consumir a classe, porque desta forma apenas programadores que darão manutenção nesta classe. Assim evitando que todos os programadores da empresa tenhão conhecimento das regras da criptografia.

## Classes

### Exemplo

&nbsp; Neste exemplo ao invés de metódos de criptografias dentro da classe como citado acima, é criado
uma classe com os metódos estáticos: criptografar e desincriptografar. (Este processo é feito para não ter que criar os metódos de criptografia em cada classe e todas possam usar o mesmo padrão). <br>

&nbsp; O problema agora é que não é desejado que a classe Criptografia seja lida por outros programadores e que eles apenas possam utiliza-lá, sem saber o que tem por debaixo dos panos. <br>
Para Resolver este problema deve-se utilizar a palavra reservada "private" na declaração da classe, transformando a mesma em uma classe privada.  





