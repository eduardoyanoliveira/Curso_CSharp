# Interfaces

&nbsp; Na programação orientade a objetos, uma interface representa um contrato que uma classe ou <i> struct </i> deve seguir.

### Exemplo

&nbsp; Em um programa que possua autenticação, pode-se declarar uma interface que faça toda classe de autenticação ser obrigada a receber como propriedades os dados do usuário e também criar um método que utilize os dados do usuário para realizar a autenticação. <br>

## Problema

&nbsp; O Exemplo acima pode parecer um pouco desnecessário, uma vez que o programa so possua uma classe de autenticação. Entretanto, é comum que programas mudem a lógica e ferramentas utilizadas neste processo. Também é plausível supor que está classe de autenticação esteja vinculada a outras classes. Por exemplo uma classe responsavél pelo login. Logo, se a classe de autenticação for alterada, a classe de login também deverá ser alterada, porque ambas estão fortemente acopladas. O problema é ainda maior no mundo real, onde uma classe pode estar acopladas a várias outras, levando quase ao impossível a alteração e manutenção da mesma.

## Solução

&nbsp; Como o próprio exemplo acima sugere. A solução para o problema é utilizar interfaces, de tal forma que, a classe login não dependa mais da classe de autenticação e sim da interface que é apenas uma abstração. 

### Obs

- A dependência entre classes citada acima, é muito comum em sistemas complexos e pode ser dada por diferentes tipos de relacionamentos entre as mesmas. Este tema será abordado em próximos artigos, porém a fins de exemplificação, uma classe pode receber uma instância de outra classe como propriedade, o que configura o relacionamento de Composição. 

## Sintaxe

&nbsp; Para informar ao compilador que uma classe implementa uma interface, deve-se informar a frente do nome da classe em sua declaração, o símbolo de dois pontos seguidos pelo nome da interface.

### Exemplo: Classe implementando interface

&nbsp; O Exemplo abaixo trata-se de um jogo, onde todo personagem deve conter métodos responsáveis por efetuar o deslocamente em todoas as quatro direções (frente, trás, direita, esquerda). Para garantir que está obrigatóriedade seja cumprida, as classes de personagens devem implementar a interface IAnimated.

```
    Player p = new Player();
    p.MoveFoward(); //Output: Você está andando para frente
    p.MoveBack(); //Output: Você está andando para trás
    p.MoveLeft(); //Output: Você está andando para a esquerda
    p.MoveRight(); //Output: Você está andando para a direita

    Console.WriteLine(); 

    NPC npc = new NPC("BlackSmith");
    npc.MoveFoward(); //Output: BlackSmith está andando para frente
    npc.MoveBack(); //Output: BlackSmith está andando para trás
    npc.MoveLeft(); //Output: BlackSmith está andando para a esquerda
    npc.MoveRight(); //Output: BlackSmith está andando para a direita


    interface IAnimated {
        void MoveFoward();
        void MoveBack();
        void MoveRight();
        void MoveLeft();
        
    };

    class Player : IAnimated
    {
        public void MoveBack()
        {
            Console.WriteLine($"Você está andando para trás");
        }

        public void MoveFoward()
        {
            Console.WriteLine($"Você está andando para frente");
        }

        public void MoveLeft()
        {
            Console.WriteLine($"Você está andando para a esquerda");
        }

        public void MoveRight()
        {
            Console.WriteLine($"Você está andando para a direita");
        }
    }


    class NPC : IAnimated
    {
        public string Name {get; set;}

        public NPC(string name){
            Name = name;
        }

        public void MoveBack()
        {
            Console.WriteLine($"{Name} está andando para trás");
        }

        public void MoveFoward()
        {
            Console.WriteLine($"{Name} está andando para frente");
        }

        public void MoveLeft()
        {
            Console.WriteLine($"{Name} está andando para a esquerda");
        }

        public void MoveRight()
        {
            Console.WriteLine($"{Name} está andando para a direita");
        }
    }

```

&nbsp; No exemplo acima ambas as classes Player e NPC implementam a interface IAnimated. Logo caso necessário seria possível intercambiá-las em um código que dependa apenas da interface IAnimated, aumentando assim a coesão do programa.

Obs:

- Ainda é possível que uma classe implemente multiplas interfaces utilizando para isto a separação por vírgulas.
