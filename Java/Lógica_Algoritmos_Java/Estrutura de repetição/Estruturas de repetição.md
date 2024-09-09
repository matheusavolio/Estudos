# Aula45 - Estrutura de repetição enquanto                 ( #while)

#### O que é
 while é uma estrutura de controle que se repete enquanto um bloco de comandos `enquanto`  uma condição for verdadeira

#### Quando usar
Quando não se sabe previamente a quantidade de repetições que será realizada

#### Sintaxe básica:
```java
while (condição){  // se true após a repetição, continuar o loop
	comando 1      // se false, encerra o loop
	comando 2
} 
```

> [!Atenção] 
> Enquanto a condição não se tornar falsa, o loop irá continuar se repetindo até que em algum momento ela se torne falsa, se ela não se tornar falsa em momento algum, ela entrará em loop infinito.

#### Exemplo:
```java
x = sc.nextInt();
        while (x != 0){
            soma += x;
            x = sc.nextInt();
        }
```
No exemplo acima, o bloco while irá se repetir até que a condição se torne false, no caso quando x for = a 0, enquanto isso não acontecer, vai continuar pedindo um, número para o usuário e guardando e somando os números digitados em soma.`

---
---
# Aula46 - Teste de mesa while


# Exercícios teste de mesa

#### Exercício 2:

![[TesteMesaWhile.png]]

---
---

# Aula50 - Estrutura de repetição ( #for)


> [!Conceito] 
> É uma estrutura de controle que repete um bloco de comandos `para` um certo `intervalo` de valores

> [!Quando usar] 
> Quando se sabe previamente a quantidade de repetições, ou o intervalo de valores


#### Sintaxe básica:
```java
   Executa
   somente na
   primeira
     vez    true - continua
	     	false - sai      Executa toda vez depois de voltar
for (início; condição ; incremento){
comando 1
comando 2
}
```

#### Exemplo: 

Fazer um programa que lê um valor inteiro N e depois N números inteiros. Ao final, mostra a soma dos N números lidos
```java
Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int soma = 0;

// em quanto o i for menor do que  n, irá continuar executando os comandos do bloco
// a cada novo loop, o i recebe +1, o loop irá parar de ser executado quando o i == n
        for (int i=0; i < n; i++){
            int x = sc.nextInt();
            soma += x;

        }
        System.out.println(soma);
        sc.close();
```
_Perceba que a estrutura "para" é ótima para se fazer uma repetição baseada em uma CONTAGEM:_
```java
for (int i=0; i<5; i++) { 
	System.out.println("Valor de i: " + i); 
	}

OUTPUT:
Valor de i: 0 
Valor de i: 1 
Valor de i: 2 
Valor de i: 3 
Valor de i: 4
```
Contagem regressiva:
```java
for (int i=4; i>=0; i--) { 
	System.out.println("Valor de i: " + i); 
	}
OUTPUT
Valor de i: 4 
Valor de i: 3 
Valor de i: 2 
Valor de i: 1 
Valor de i: 0
```

# Teste de mesa for

![[TesteDeMesaFor.png]]

---
---
# Aula55 - faça-enquanto ( #doWhile)
É uma estrutura de repetição menos utilizada, mas se encaixa melhor ao problema
O bloco de comandos executa pelo menos uma vez, pois a condição é verificada no final.

#### Sintaxe básica:
```java
do{
	comando 1
	comando 2
} while (condição);
```

#### Exemplo:
Fazer um programa para ler uma temperatura em Celsius e mostrar o equivalente em Fahrenheit. Perguntar se o usuário deseja repetir (s/n). Caso o usuário digite "s", repetir o programa. 
```java
char resp;
      do{
		System.out.print("Digie a temperatura em celcius: ");
         double c = sc.nextDouble();
         double f = 9.0 * c / 5.0 + 32.0;
         System.out.printf("Equivalente em Fahrenheit: %.1f\n", f);
         System.out.print("Quer continuar? [S/N]");
         resp = sc.next().charAt(0);
      } while (resp != 'n');
      sc.close();
```
O programa acima, vai ficar repetindo até o usuário digitar "N", enquanto ele não digitar, vai continuar pedindo para ele inserir uma temperatura em graus, imprimindo essa temperatura em fahrenheit e pergunta se deseja continuar novamente, até ser digitado "N".