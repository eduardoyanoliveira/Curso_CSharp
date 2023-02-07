# Sobrescrção

&nbsp; No artigo anterior sobre herança, é citado que uma subclasse pode alterar o comportamento de um método herdado.Este processo é chamado de sobescrição, e para realizá-lo o método da superclasse deve utilizar a palavra "virtual" para indicar que trata-se de método que possívelmente pode ser sobscrito. Já na subclasse, deve-se implementar um método com o mesmo nome, porém utilizando a palavra reservada "override" que indica uma sobrescrição.

## Caso de uso

&nbsp; A sobrescrição é utilizada quando um método já foi implementado na superclass, porém deve possuir comportamento diferente na subclass.

### Exemplo

&nbsp; Este exemplo trata-se de um Programa de desconto que possui a Classe BaseDiscount que é herdada pela classe CustomDiscount. A classe BaseDiscount possui um método Calc que calcula o disconto pela porcentagem informada, e a classe CustomDiscount calcula o disconto sobescrevendo o método Calc colocando além da porcentagem informada como disconto, um disconto fixo.

```csharp
    BaseDiscount bd = new BaseDiscount();
    CustomDiscount cd = new CustomDiscount(100.00);

    Console.WriteLine(bd.Calc(1000.00, 0.05)); //Output: 950
    Console.WriteLine(cd.Calc(1000.00, 0.05));  //Output: 850

    class BaseDiscount {
        
        public virtual double Calc(double total, double percent){
            return total -= total * percent;
        } 
    }

    class CustomDiscount: BaseDiscount {

        public double FixedDiscount {get; private set;} 

        public CustomDiscount(double fixedDiscount){
            FixedDiscount = fixedDiscount;
        }

        public override double Calc(double total, double percent){
            double result = total - total * percent;
            return result - FixedDiscount;
        } 
    }
```

## base

&nbsp; No exemplo citado acima é possível perceber uma repetição de código, onde a subclasse CustomDiscount primeiro realiza a mesma implementação que foi feita na superclasse, para depois dar o disconto de valor fixo.<br>

&nbsp; A repetição de códogo deve ser evitada ao máximo, pois a mesma quebra um princípio de um bom código. O princípio DRY (Don't Repeat Yourself).

&nbsp; Para reaproveitar a implementação do código já utilizado na superclasse, pode-se utilizar a palavra reservada "base" para acessar o método da superclasse. A palavra "base" representará a prórpia superclasse dentro da subclasse.

### Exemplo

```csharp
    BaseDiscount bd = new BaseDiscount();
    CustomDiscount cd = new CustomDiscount(100.00);

    Console.WriteLine(bd.Calc(1000.00, 0.05)); //Output: 950
    Console.WriteLine(cd.Calc(1000.00, 0.05));  //Output: 850

    class BaseDiscount {
        
        public virtual double Calc(double total, double percent){
            return total -= total * percent;
        } 
    }

    class CustomDiscount: BaseDiscount {

        public double FixedDiscount {get; private set;} 

        public CustomDiscount(double fixedDiscount){
            FixedDiscount = fixedDiscount;
        }

        public override double Calc(double total, double percent){
            /* ----------  Uso da palavra base --------- */
            double result = base.Calc(total,percent);
            return result - FixedDiscount;
        } 
    }
```

## sealed (Selar)

&nbsp; A palavra sealed em C# pode ser utilizada para impedir que uma classe seja herdada, ou que um método que é uma sobescrição seja sobescrito em uma nova subclasse.

* ### sealed class

&nbsp; Para selar uma classe utilize a palavra sealed antes da palavra class na criação da classe.

* ### seald override

&nbsp; Para selar um método, deve-se utilizar a palavra "sealed" antes da palavra "override". Somente métodos que são sobrescrições podem ser selados.
