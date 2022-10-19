# Métodos 

&nbsp; Métodos são funções que existem dentro de uma classe, e estarão presentes para cada instância criada. Métodos são ações ou processos que se espera em todas as instâncias da classe. <br>

### Exemplo

&nbsp; Em um programa de zoologico deve-se controlar a alimentação dos animais. Todas as vezes que um animal alimenta, deve-se registrar no programa. Para descrever os animais no programa, é criado  a classe Animal, e para registrar que o animal está se alimentando é criado um método dentro da classe, pois é sabido que todo animal irá se alimentar de alguma forma.

```
    Animal lion = new Animal();
    lion.name = "Leo";

    lion.Feed(); //Output: "Leo está se alimentando."

    class Animal {
        public string name;
        
        public void Feed(){
            Console.WriteLine($"{name} está se alimentando.");
            return;
        }
    };
```

Obs:

- O tipo de retorno "void" utilizado no método Feed dentro da classe, indica que a função não retornar nenhum valor.

## Métodos com parâmetros

&nbsp; Os métodos também podem receber parâmetros externos que serão passados quando o método for executado.

### Exemplo

```
    Calc c = new Calc();

    Console.WriteLine(c.Sum(10.5 , 3.5)); //Output: 14

    class Calc {
        public double Sum(double numbOne, double numbTwo){
            double result = numbOne + numbTwo;
            return result;
        }
    };
```