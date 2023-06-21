# Nomes

&nbsp; Nomes são utilizados por toda parte na programação, desde variáveis até pastas e arquivos. Por causa de sua grande presença dentro de uma aplicação, os nomes exercem um papel importantissímo na legibilidade de um código. Nomes pouco descritivos podem transformar um código de alta qualidade em um código "sujo".

## Nomes deve revelar seu propósito

&nbsp; Escolher bons nomes leva tempo, mas economiza ainda mais. O nome de uma variável, função ou classe deve responder as seguintes questões.

    - Por que existe? (Ex: Por que a variável existe)
    - O que faz? (Ex: O que a variável faz)
    - Como é usada? (Ex: Como a variável é utilizada)

&nbsp; Se um nome requer um comentário, ele não revela seu propósito.

### Exemplo

```
    let d; // Tempo decorrido
```

&nbsp; No exemplo acima o nome "d" não indica a ideia de tempo decorrido.Neste caso, deve-se escolher um nome que especifique seu uso para a mensuração e a unidade usada.

### Exemplo

```
    let elapsedTimeInDays;
    let daysSinceCreation;
```