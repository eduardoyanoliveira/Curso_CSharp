# Tipos de Testes

&nbsp; Dentro dos testes automatizados existem três tipos de testes:

- Unit Test (Teste unitário).

- Integration Test (Teste de integração).

- End-To-End Test (Teste ponta a ponta).

* ## Unit Test

&nbsp; Os testes unitários como o nome sugere, testam uma unidade da aplicação isoladamente. Isto é, no teste unitário depedências externas como banco de dados, servidor, cache e outras não fazem parte do teste.

### Características

- Criação barata. (O Teste é simples de ser criado)

- Execução rápida.

- Não entrega uma confiança total na acertividade de um processo, pois o mesmo não testa o processo por completo apenas uma pequena unidade.

* ## Integration Test

&nbsp; Ao contrário dos testes unitários, os testes de integração testa uma unidade do código com suas dependências externas.

### Características

- Leva mais tempo do que testes unitários para executar, pois normalmente involvem operações pesadas, tal como input e output.

* ## End-To-End Test

&nbsp; Testes de ponta à ponta são responsáveis por testar um processo isolado desde a interface gráfica (UI) até a infraestrutura do banco de dados.

### Características

- Normalmente muito devagar.

- Fragilidade. Os testes de ponta á ponta podem ser quebrados por pequenas modificações no código.