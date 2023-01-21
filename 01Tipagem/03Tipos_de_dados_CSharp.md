# Tipos de Dados usados no C#

&nbsp; Este artigo apresenta apenas os tipos de dados básicos mais utilizados no CSharp.

* int => número inteiro positivo ou negativo.
```
    int numb = 150463;
    int numb2 = -351678;
```
* long => número inteiro positivo ou negativo de maior amplitude do que int.

```
    long numb = 2147483648L;
    long numb2 = -2147483648L;
```

#### Obs:

Por convenção ao atribuir o valor ao tipo long é utilizado a letra "L" no final do número.(Não obrigatório)

* float => número de ponto flutuante positivo ou negativo.

```
    float numb = 4.5f;
    float numb2 = -7.9f;
```

#### Obs:

Para Indicar que trata-se de um float deve-se adicionar a letra "f" no final do número.(Obrigatório)


* double => número de ponto flutuante positivo ou negativo de maior amplitude do que float.

```
    double numb = 4.5;
    double numb2 = -7.9;
```

#### Obs:

Tipos númericos possuem um limete de valor mínimo e máximo, para descobri-los utilize as propriedades MinValue e MaxValue respectivamente.

```
    /* A Função Console.WriteLine escreve um valor no console */
    Console.WriteLine(int.MinValue);
    Console.WriteLine(float.MaxValue);

```

* bool => valor lógico verdadeiro ou falso.

```
    bool isActive = true;
    bool isOff = false;
```

* Char => armazena um caracter unicode.(Armazena um unico caracter).

```
    char gender = "M";
```

* string => representa um encadeamento de caracteres. Para criá-las utilize sempre aspas duplas entorno dos caracteres desejados.

```
    string name = "Yan"
```

#### Obs:

O tipo String não é um tipo básico, o mesmo receberá um artigo próprio.
