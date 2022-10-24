# Pirâmide de Testes (Test Pyramid)

&nbsp; A pirâmide de testes é um conceito que representa como os testes devem ser distribuídos em uma aplicação.
Este conceito é representado da seguinte forma:

## Base - Unit Test

&nbsp; A Base dos testes de uma aplicação deve ser os testes unitários. A maior parte dos testes da aplicação.

## Centro - Integration Test

&nbsp; No centro da pirâmide de testes está os testes de integração. Como os testes de unidade nem sempre passam muita confiabilidade a um recurso, os testes de integração devem ser aplicados em larga escala na aplicação. Entretanto a diferença entre a quantidade de testes unitários e testes de integração é notável, sendo assim normalmente os testes unitários são encontrados em maior quantidade no sistema.

## Top - End-to-End

&nbsp; No topo da pirâmede está os testes de ponta à ponta. Este tipo de teste deve ser empregado em uma quantidade muito menor que os testes de integração. Normalmente não existem testes end-to-end para cada caso de uso de um recurso.

###  Obs

&nbsp; A pirâmide de testes é apenas um conceito, não deve ser seguido restritivamente.