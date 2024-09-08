# Aula38 - Operadores de atribuição cumulativa 

#### #atribuiçãoCumulativa

| Operadores | Resultado |
| ---------- | --------- |
| a += b     | a = a + b |
| a -= b     | a = a - b |
| a *= b     | a = a * b |
| a /= b     | a = a / b |
| a %= b     | a = a % b |


#### Exemplo:
Uma operadora de telefonia cobra R$ 50.00 por um plano básico que dá direito a 100 minutos de telefone. Cada minuto que exceder a franquia de 100 minutos custa R$ 2.00. Fazer um programa para ler a quantidade de minutos que uma pessoa consumiu, daí mostrar o valor a ser pago. 

| Entrada |         Saída          |
| :-----: | :--------------------: |
|   22    | Valor a pagar: R$50.00 |
|   103   | Valor a pagar: R$56.00 |

```java
ATRIBUIÇÇÃO CUMULATIVA
int minutos = sc.nextInt();
        double conta = 50.0;
        if (minutos > 100){
            conta += (minutos - 100) * 2.0;
        }
```

```java
ATRIBUIÇÃO NORMAL
int minutos = sc.nextInt();
        double conta = 50.0;
        if (minutos > 100){
            conta = conta + (minutos - 100) * 2.0;

        }
```
---
---

# Aula39 - switch-case

> [!Atenção]
> Estrutura switch-case Quando se tem várias opções de fluxo a serem tratadas com base no valor de uma variável, ao invés de várias estruturas if-else encadeadas, alguns preferem utilizar a estrutura switch-case.

#### #SintaxeSwitchCase 
```java
switch ( expressão ) { 
	case valor1: 
		comando1 
		comando2 
		break; 
	case valor2: 
		comando3 
		comando4 
		break; 
	default: 
		comando5 
		comando6 
		break; }
```
#### Exemplo: 

Fazer um programa para ler um valor inteiro de 1 a 7 representando um dia da semana (sendo 1=domingo, 2=segunda, e assim por diante). Escrever na tela o dia da semana correspondente, conforme exemplos.

| Entrada | Saída                         |
| ------- | ----------------------------- |
| 1       | Dia da semana: domingo        |
| 4       | Dia da semana: quarta         |
| 9       | Dia da semana: valor inválido |

```java
UTILIZANDO IF-ELSE
        if (x == 1) {
            dia = "domingo";
        } else if (x == 2) {
            dia = "segunda";
        } else if (x == 3) {
            dia = "terca";
        } else if (x == 4) {
            dia = "quarta";
        } else if (x == 5) {
            dia = "quinta";
        } else if (x == 6) {
            dia = "sexta";
        } else if (x == 7) {
            dia = "sabado";
        } else {
            dia = "valor invalido";
        }
```
```java
UTILIZANDO switch-case
        switch (x) {
            case 1:
                dia = "domingo";
                break;
            case 2:
                dia = "segunda";
                break;
            case 3:
                dia = "terca";
                break;
            case 4:
                dia = "quarta";
                break;
            case 5:
                dia = "quinta";
                break;
            case 6:
                dia = "sexta";
                break;
            case 7:
                dia = "sabado";
                break;
            default:
                dia = "valor invalido";
                break;
            }

```

---
---
# Aula40 - Expressão condicional ternária

> [!Atenção]
> Estrutura opcional ao if-else quando se deseja decidir um VALOR com base em uma condição
#### Sintaxe #expressãoTernária
```java
( condição ) ? valor_se_verdadeiro : valor_se_falso
```
#### Exemplos:
```java
( 2 > 4 ) ? 50 : 80 // output 80

( 10 != 3 ) ? "Maria" : "Alex" // output Maria
```

#### Descobrir se um número é par ou ímpar expCondicional padrão
```java
n1 = sc.nextInt();
        if (n1 % 2 == 0){
            System.out.println("Par");
        }
        else{
            System.out.println("Ímpar");
        }
```


#### Descobrindo se um número é par ou ímpar expTernária
```java
int num = sc.nextInt();
        String parImpar = (num % 2 == 0) ? "Par" : "Ímpar";
```


# Aula41 - Escopo e inicialização
#### Checklist 
-  Escopo de uma variável: é a região do programa onde a variável é válida, ou seja, onde ela pode ser referenciada. 
- Uma variável não pode ser usada se não for iniciada.

> [!Atenção]
> escopo e inicialização em nível de estrutura de controle.


