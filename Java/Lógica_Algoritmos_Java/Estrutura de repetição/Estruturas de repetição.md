# Aula45 - Estrutura de repetição enquanto (while)

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

#### Exercício 1:

#### Exercício 2:

![[testeDeMesa02.png]]
