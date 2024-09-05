# Aula25 - Processamento de dados em Java, Casting

O processamento de dados( chamado de Casting ) e não só em Java, mas em qualquer linguagem, ele é feito por meio do comando de atribuição `=` que é lido como "receve"
Sintaxe:
```java
<variável> = <expressão>;
```
E a regra da expressão funciona assim:
1) A expressão é calculada
2) E o resultado da expressão é armazenado na variável
---
Exemplo:
```java
int x, y;
x = 5;
y = 2 * x;
System.out.println(x);
System.out.println(y);

double b, B, h, area;
b = 6.0;
B = 8.0;
h = 5.0;
area = (b + B) / 2.0 * h;
System.out.println(area);
----------------------
OUTPUT
5
10
35.0
```
`Boa prática `-> Sempre indique o tipo do número, se a expressão for de ponto flutuante (não inteira).
`Para double use: .0 
`Para float use: f`

```java
// se o código for impresso desse jeito, o output 
// será 2, e não 2,5. Isso acontece por qua as              
// variáveis a e b foram declaradas como int

int a, b; 
double resultado; 
a = 5; 
b = 2; 
resultado = a / b;
System.out.println(resultado);
------------------------------
OUTPUT
 2 
----------------    
int a, b; 
double resultado; 
a = 5; 
b = 2; 
resultado = (double) a / b; 
System.out.println(resultado);
------------------------------
OUTPUT
2,5
// e para resolver isso, declaramos na expressão a                                      // palavra (double), assim o output será um número                                      // decimal
```


#### #Casting 
É a conversão explícita de um tipo para outro. É necessário quando o compilador não é capaz de “adivinhar” que o resultado de uma expressão deve ser de outro tipo
