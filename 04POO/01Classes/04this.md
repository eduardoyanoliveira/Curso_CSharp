# this

&nbsp; A palavra reservada this apresenta algumas funcionalidades na linguagem C#. Sua definição principal é que a mesma é utilizada para referir-se a instância da classe. <br>

## Diferenciando Atributos dos construtores das propriedades da classe.

&nbsp; O primeiro uso dado a palavra this é para diferenciar os valores recebidos como atributos de um construtor e as propriedades da classe. No artigo anterior sobre construtores, é apresentado que o nome do atributo recebido deve ser diferente do nome da propriedade, para que o compilador consiga fazer está diferenciação. No entanto, é possível que ambos atributo e propriedade possuam o mesmo nome, desde que a palavra this seja utilizada como prefixo da propriedade.

### Exemplo

```
    Person p = new Person("Yan", 24, 1.71);

    Console.WriteLine(p); //Output: "meu nome é Yan, minha idade é 24 anos e minha altura é 1,71 cm"

    class Person {
        public string name;
        public int age;
        public double height;
        
        public Person(string name, int age, double height){
            this.name = name;
            this.age = age;
            this.height = height;
        }

        public override string ToString(){
            return $"meu nome é {name}, minha idade é {age} anos e minha altura é {Height} cm";
        }
    };
```

## Referenciando construtores

&nbsp; Também é possível utilizar a palavra reservada "this" para referenciar um construtor já declarado na criação de outro. De tal forma que permita que o código utilizado em um construtor seja aproveitado em outro.<br>

&nbsp; O compilador compreenderá sobre qual construtor a palavra reservada this refere-se pelo número de atributos que o mesmo recebe. 

### Exemplo

```
    Employee emp = new Employee("Yan", 24, 3000.00);

    Console.WriteLine(emp); //Output: "meu nome é Yan, minha idade é 24 anos e meu salário é R$ 3000.00 ."

    class Employee {
        public string name;
        public int age;
        public double salary;
        
        public Employee(string name, int age){
            this.name = name;
            this.age = age;
        }

        public Employee (string name, int age, double salary) : this (name, age){
            this.salary = salary;
        }

        public override string ToString(){
            return $"meu nome é {name}, minha idade é {age} anos e meu salário é R${salary} .";
        }
    };
```

### Passando this como argumento de um método

&nbsp; "this" pode ser passado como argumento de um método da própria classe. Neste caso representará o próprio objeto.


