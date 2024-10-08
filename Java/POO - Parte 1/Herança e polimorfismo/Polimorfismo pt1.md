# Aula134 - Introdução ao polimorfismo

#### *Pilares da POO*
- Encapsulamento
- Herança
- Polimorfismo

####  #Polimorfismo:
- Em Programação Orientada a Objetos, polimorfismo é recurso que permite que variáveis de um mesmo tipo mais genérico possam apontar para objetos de tipos específicos diferentes, tendo assim comportamentos diferentes conforme cada tipo
- Poli -> muitos, Morfismo -> formas, Polimorfismo -> Muitas Formas
- variáveis do mesmo tipo se comportam de vários tipos diferentes

```java
Account x = new Account(1020, "Alex", 1000.0);
Account y = new SavingsAccount(1023, "Maria", 1000.0, 0.01);

x.withDraw(50.0);
y.withDraw(50.0);
```
Acima temos duas variáveis do tipo Account, porém a variável `x` foi instanciada com o tipo `Account` enquanto a variável `y` o tipo `SavingsAccount`, então iremos ter objetos de tipos diferentes na memória, porém, as variáveis que irão apontar para esses objetos são do mesmo tipo.
Então quando eu chamar o método `withDraw()` os dois irão ter comportamentos diferentes.

![[polimorfismo1.jpg]]
Quando eu chamar o `x.withDraw()` a partir da variável `x` eu vou estar executando o saque da classe `Account`, porém, quando eu chamar o `y.withDraw` eu vou estar chamando a operação da classe `SavingsAccount` 

O polimorfismo significada "Muitas formas", chamamos a mesma operação em variáveis do mesmo tipo, porém elas tiveram comportamentos diferentes, conforme os objetos que elas apontam.

#### *Importante*:
- A associação do tipo específico com o tipo genérico é feita em tempo de execução ( #Upcasting )
	- Instanciamos o `SavingsAccount` e atribuímos ela a variável `y` feita em tempo de execução, o compilador não sabe qual o tipo específico da variável `y`, ele vai chamar o método adequado com base no objeto que foi instanciado, e esse instanciação é feita em tempo de execução por meio de um upcasting.
- O compilador não sabe qual tipo específico a chamada do método `withDraw` está sendo feita(ele só sabe que são duas variáveis tipo `Account`)

### Aula135 - Exercício resolvido #polimorfismo


![[polimorfismo2.jpg]]
![[polimorfismo3.1.jpg]]

## Aula136 - Exercício de fixação

![[fixação polimorf_2.jpg]]


![[fixação polimorf.jpg]]

