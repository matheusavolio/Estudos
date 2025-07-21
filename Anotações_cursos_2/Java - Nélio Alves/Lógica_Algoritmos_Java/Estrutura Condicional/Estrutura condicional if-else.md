# Aula35 - if-else
### Conceito
Estrutura condicional é uma estrutura de controle que permite definir que um certo bloco de comandos somente será executado dependendo de uma condição

![[Diagram 1.svg]]

Se essa condição for True, será executado o bloco 1, se for False, será executado o bloco 2

---
---
### Sintaxe da estrutura condicional composta:
```java
if (<condição1){
	<comando 1>
	<comando 2>
}
else if(condição 2){
	<comando 3>
}   <comando 4>      // se condicao 1 == true: executa somente o bloco do if
else{               //se condicao 1 == false e condicao 2 == true: executa bloco else if
    <comando 5>       // se condicao 1 e 2 == false: executa bloco else
	<comando 6>
}
```

Exemplo 1:
```java
x = 10;
y = 15;
soma = x + y;               
if (soma > 20){
	System.out.println("A soma é maior do que 20"); // output: True - executa o bloco if
}          
else{
	System.out.println("A soma é menor do que 20");
}
```
Exemplo 2:
```java
x = 10;
y = 15;
soma = x + y;               
if (soma > 20){
	System.out.println("A soma é maior do que 20");
}          
else{
	System.out.println("A soma é menor do que 20"); // output: False - executa o bloco                                                      //  else
}
``` 
Exemplo 3:
```java
x = 10;
y = 15;
soma = x + y;               
if (soma > 20){
	System.out.println("A soma é maior do que 20");
}  
else if(soma == 25){
	System.out.println("A soma é igual a 25"); // output: True - executa bloco else
}
else{
	System.out.println("A soma é menor do que 20");
```
---
---
### Estrutura condicional aninhada

```java
if ( condição 1 ){ 
	comando 1 
	comando 2 
} 
else { 
	if( condição 2 ) { 
		comando 3 
		comando 4 
	} 
	else { 
		comando 5 
		comando 6 
		}
}
```
Exemplo:
```java
x = 10;
y = 15;
soma = x + y;               
if (soma > 20){
	if (soma == 25){
	System.out.println("A soma é igual a 25");
	}
	else if(soma == 30){
	System.out.println("A soma é igual a 30");
	}
}
else{
	System.out.println("A soma é menor do que 20");
}
```
