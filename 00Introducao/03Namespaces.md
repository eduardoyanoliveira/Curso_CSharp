# Namespaces

Em C#, um namespace é um mecanismo de controle de visibilidade, usado para definir um escopo. Uma namespace conterá um conjunto de classes, tipos semânticamente correlatas.

## Como definir um Namespace ?

Um namespace pode ser declarado com a palavra chave "namespace" seguida de um nome válido em C#.

* Exemplo:

```
namespace MysticClasses
{
    public class Mage
    {
        public string Name;
        public float Magika;
    }

    public class BattleMage
    {
        public string Name;
        public string Strength;
    }
}
```

## Como utilizar uma Namespace?

Utilize a diretiva using para informar que um arquivo está usando uma Namespace. Após isto será possível acessar itens dentro da namespace no arquivo usando a seguinte sintaxe:

```
using MysticClasses;

MysticClasses.Mage mage = new MysticClasses.Mage();

```

### Obs:

Este tópico pode parecer um tanto quanto avançado, entretanto o mesmo está inserido nesta fase para prover um conhecimento básico a possíveis sitações futuras.