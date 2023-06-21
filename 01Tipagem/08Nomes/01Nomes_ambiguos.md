# Nomes ambíguos

&nbsp; Nomes que estão sujeito a interpretação ou que possua significado ambíguo podem gerar problemas ao leitor do código.

## Nomes associativos

&nbsp; Dentro da categoria de nomes ambíguos estão os nomes associativos. Isto é, nomes que o leitor pode associar a coisas comum no universo da programação, porém tais nomes não estão necessáriamente referindo-se a possível associação.

### Exemplo

&nbsp; Nomear uma coleção de produtos como productList pode levar uma interpretação incorreta por outros programadores. Isto acontece porque a palavra List normalmente está relacionada ao tipo List em algumas línguaguens de programação. Logo, o leitor pode associar que a variável productList é do tipo List, mesmo que o tipo da variável seja um array, set, etc. Neste caso seria mais apropriado declarar a variável com o nome "products".

## Nomes de alta semelhança

&nbsp; Outro exemplo de nomes ambíguos, são nomes muitos semelhantes que possam gerar a mesma interpretação em ambos nomes, ou nomes que requerem muita atenção para que sua distinção seja realizada.

### Exemplo

&nbsp; Um exemplo de nomes semelhantes pode ser dado ao analisar duas coleções, sendo ambas as relacionadas aos endereços de cliente.

```
    let customerAddresses;
    let addressesOfCostumer;
```

&nbsp; No exemplo acima é impossível saber qual das coleções armazenam os endereços do cliente. Também é pouco provável que o leitor saiba o real uso de ambas coleções.

## Nomes confusos

&nbsp; Outro tipo de nome a ser evitado são os nomes confusos. Um exemplo de nome confuso é utilizar a letra "O" ou a letra "l" em uma variável. O leitor do código pode inferir que trata-se dos números zero e um.

