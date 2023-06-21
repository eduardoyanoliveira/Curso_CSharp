# Dictionary (Dicionários)

&nbsp; Dicionários são estruturas de dados comumente utilizadas na programação. O dicionário ao contrário da maioria das estruturas de dados possui um formato de chave e valor, o que faz o mesmo assimilar-se aos dicionários linguísticos, onde se pesquisa por uma palavra chave para encontrar seu significado(valor).

## Características 

* Não admite repetição da chave. Caso um valor seja atribuído com uma chave existente, o valor da mesma será substituído.

* Tal como os HashSet, o acesso a inserção e remoção são rápidos.

## Sintaxe

&nbsp; Para declarar um dicionário em c# é necessário seguir as etapas abaixo:

1º Utilize a palavra reservada Dictionary seguida pelos sinais de menor e maior.

2º Dentro dos sinais de menor e maior deve-se colocar ambos os tipos de dados da chave e valor separado por vírgula. Isto é, um dicionário não pode possuir chaves de diferentes tipos e valores de mais de um tipo. 

    - Exemplo: Dictionary<string, int>

3º Em seguida é necessário definir o nome para identificar o dicionário na memória. (nome da variável)

4º Por final, tal como outras estruturas de dados já apresentadas em artigos anteriores. Deve-se utilizar a palavra reservada "new" seguida por novamente a palavra Dictionary e seus tipos entre sinais de maior e menor, e deve-se abrir e fechar parênteses para indicar que uma nova instância de dictionary está sendo criada.

### Exemplo

```csharp
    Dictionary<string, string> test = new Dictionary<string, string>();
```


## Adicionar valores a um Dicionário

&nbsp; Existe duas formas de acionar um par de chave e valor a um dicionário. A primeira maneira é utilizando o método "Add" recebendo como primeiro parâmetro o valor da chave e segundo o valor própriamente dito.

### Exemplo

&nbsp; O Exemplo abaixo mostra a criação de um dicionário cuja ambos chave e valor são do tipo string. O mesmo é utilizado para armazenar o nome de uma pessoa e seu email.

```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.Add("maria","maria@gmail.com" );

```

&nbsp; A Segunda maneira de adicionar um par de chave e valor ao dicionário seria utilizando a seguinte sintaxe.

1º Deve-se escrever o nome da variável cuja o dicionário está armazenado, seguido por colchetes.

2º Dentro dos colchetes deve-se colocar o valor que será utilizado como chave do dicionário.

3° Por final, utiliza-se o sinal de atribuição "=" seguido pelo valor a ser atribuído a está chave do dicionário.

    - Obs: Utilizando está sintaxe é possível alterar o valor de uma chave já existente no dicionário.


### Exemplo:


```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.["maria"] = "maria@gmail.com";

```

## Remover valor do dicionário

&nbsp; Para remover a chave e seu respectivo valor do dicionário, é necessário que se utilize o método "Remove" recebendo como parâmetro o valor da chave a ser removida.


```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.["maria"] = "maria@gmail.com";
    emails["yan"] = "yan@gmail.com";

    emails.Remove("yan"); // Removerá a chave "yan" do dicionário

```

## Iterar sobre chaves e valores de um dicionário.

&nbsp; Para iterar sobre chaves e valores de um dicionário, pode-se utilizar a estrutura de repetição "foreach". No entanto, ao contrário de outras estruturas de dados que posseum índice com valor único, no caso do dicionário deve-se utilizar o KeyValuePair<> com os tipos de dados da chave e valor para criar a variável de controle que representará a o valor atual da repetição.

### Exemplo

```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.Add("maria","maria@gmail.com" );
    emails["Yan"] = "yan@gmail.com";


    foreach(KeyValuePair<string, string> item in emails){
        Console.WriteLine(item);
    };

    /* ---- Output ----
        [maria, maria@gmail.com]
        [Yan, yan@gmail.com]
    */
```

## Limpar dicionário. (Remover todas as chaves e valores)

&nbsp; Utilize o método Clear para remover todos os valores de um dicionário.

### Exemplo


```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.Add("maria","maria@gmail.com" );
    emails["Yan"] = "yan@gmail.com";

    emails.Clear();

    foreach(KeyValuePair<string, string> item in emails){
        Console.WriteLine(item);
    };

    /* ---- Output ----
        
    */
```

## Verificar quantidade de elementos de um dicionário

&nbsp; Deve-se atentar ao método utilizado para verificar a quantidade de elementos de um dicionário, pois, ao contrário da maioria das estruturas de dados indexáveis que utilizam o método ou propriedade "Length", o dicionário utilizará o metódo "Count".

### Exemplo:

```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.Add("maria","maria@gmail.com" );
    emails["Yan"] = "yan@gmail.com";

    Console.WriteLine(emails.Count()); // Output: 2
```

## Verificar se o dicionário possui uma chave ou um valor.

&nbsp; Para verificar se o dicionário possui uma chave pode-se utilizar o método "ContainsKey", enquanto o método "ContainsValue" é utilizado para verificar se um dicionário possui um valor.

### Exemplo

```csharp
    Dictionary<string, string> emails = new Dictionary<string, string>();

    emails.Add("maria","maria@gmail.com" );
    emails["Yan"] = "yan@gmail.com";

    Console.WriteLine(emails.ContainsKey("maria")); // Output: True
    Console.WriteLine(emails.ContainsValue("joao@gmail.com")); // Output: False
```
