# Heap

&nbsp;  Tal como o Stack a palvra Heap trata-se de um espaço na memória tempóraria utilizada para armazenar valores da aplicação.

## Características

- Não possui tamanho fixo. Seu tamanho é alterado conforme a necessidade do compilador de armazenar valores.

- Armazena objetos com tempo de vida maior.

- O acesso a valores armazenados na Heap é feita por referências armazenadas na Stack (Ref Types).

- Utiliza Garbage Collector.

## Funcionamento

&nbsp; Ao armazenar um valor na memória Heap o CLR (Common Language Runtime) irá atribuir o objeto a uma parte da memória, e para identificá-lo este espaço da memória receberá um endereço. É importante resaltar que cada objeto possuirá seu próprio endereço na memória.

&nbsp; Valores armazenados na Heap são valores como objetos de classes que vão possuir uma referência na memória Stack. Isto é, ao instanciar um objeto a variável utilizada para armazená-lo estará na memória Stack. Entretanto esta variável armazenará apenas a referência para o endereço na memória Heap onde realmente estará armazenado os membros do objeto, como propriedades e métodos.

Obs: A variável na memória Stack é chamada de ponteiro.

## Garbage Collector

&nbsp; Como o tamanho da memória Heap é controlado pelo CLR assim como o gerenciamento do armazenamento.É preciso que objetos não utilizados sejam retirados da memória para que o espaço seja liberado, evitando assim um Memory Leak.

&nbsp; O Garbage Collector é um mecanismo utilizado pelo CLR para remover da Heap objetos que não possuem mais referências no programa. Para facilitar o entendimento do seu funcionamento é preciso observar um exemplo como o abaixo.

### Exemplo

1º O programa possui uma função X que executa outra função Y, a função Y por sua vez instancia um objeto, utiliza o mesmo internamente no escopo da função e depois ira retorná-lo.

2º Após o objeto ser retornado para a função X os dados do mesmo são salvos no banco de dados através da função SaveToDB.

&nbsp; Após entender o procedimento executado pelo programa, deve-se analisar o comportamento do mesmo na memória.

1º A Stack do programa será formada pela seguinte ordem: função Y, função SaveToDB, função X.

2º A Função X irá chamar a função Y aguardar seu retorno. Depois irá pegar o valor retornado pela função Y e executará a função SaveToDB com o mesmo valor.Por fim a função SaveToDB retornará para a função X que terminará sua execução.

    - As funções serão removidas da Stack na mesma ordem de seu retorno acima.

3º Após o término da função SaveToDB o objeto instanciado pela função Y não é mais referenciado. Logo, o Garbage Collector irá remover o objeto da memória Heap, liberando o espaço da memória.