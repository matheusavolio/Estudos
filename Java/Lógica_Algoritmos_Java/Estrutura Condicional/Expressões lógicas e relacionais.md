# Aula33 - #ExpressõesRelacionais 

Expressões comparativas são aquelas expressões que comparam uma coisa com outra, e o resultado dessa comparação sempre será um #boolean #TrueOrFalse 

| Operador |  Significado   |
|:--------:|:--------------:|
|    >     |     Maior      |
|    <     |     Menor      |
|    >=    | Maior ou igual |
|    <=    | Menor ou Igual |
|    ==    |     igual      |
|    !=    |   diferente    |
Exemplos:
```java
x = 5 // atribuição
x > 0 // output True
x == 3 // output False
10 <= 30 // true
x != 2 // true
```
# Aula34 - #ExpressõesLógicas
expressões lógicas, assim como as relacionais, quando avaliadas resultam em um #boolean #TrueOrFalse 

| Operador | Significado |
| :------: | :---------: |
|    &&    |      E      |
|  \| \|   |     OU      |
|    !     |     Não     |

---
---
#### Ideia por trás do "E/&&":
Você pode obter uma habilitação de motorista se:

- For aprovado no exame psicotécnico
- E/&&
- For aprovado no exame de legislação
- E/&&
- For aprovado no exame de direção
A expressão && serve para verificar várias condições
> [!Atenção] 
> Todas as condições precisam ser verdadeiras!

Exemplo 1:
```java
int x = 5;
x <= 20 && x == 10 // output false
```
Exemplo 2:
```java
x > 0 && x != 3 // output true
```
Exemplo 3:
```java
x <= 20 &7 x == 10 && x != 3 // false
```
### Tabela verdade do &&

|  A  |  B  | A && B |
|:---:|:---:|:------:|
|  F  |  F  |   F    |
|  F  |  V  |   F    |
|  V  |  F  |   F    |
|  V  |  V  |   V    |

---
---
### Ideia por trás do "OU/||"
Você pode estacionar na vaga especial se:
- For idoso(a)
- OU/||
- For uma pessoa com deficiência
- OU/||
- For uma gestante
Serve para verificar várias condições
> [!Atenção]
> Pelo menos uma condição deve ser verdadeira

Exemplo 1:
```java
int x = 5;
x == 10 || z <= 20 // output true
```
Exemplo 2:
```java
int x = 5;
x > 0 || X != 3 // output true 
```
Exemplo 3:
```java
int x = 5;
x <= 0 || x != 3 || x != 5 // output true
```
### Tabela verdade do ||

|  A  |  B  | A \|\| B |
| :-: | :-: | :------: |
|  F  |  F  |    F     |
|  F  |  V  |    V     |
|  V  |  F  |    V     |
|  V  |  V  |    V     |

---
---
### Ideia por trás do "NÃO/!"
Você tem direito a receber uma bolsa de estudos se você:
- NÃO/!
- Possuir renda maior que U$3000.00

João - U$5000.00
José - U$2000.00
> [!Atenção] 
> O operador NÃO/! inverte a condição

Exemplo 1:
```java
int x = 5;
!(x == 10); // output true
```
Exemplo 2:
```java
int x = 5;
! (x >= 2); output false
```
_Exemplo_ 3:
```java
int x = 5;
!(x <= 20 && x == 10); // output true
```
### Tabela verdade do !

|  A  | !A  |
| :-: | :-: |
| _F_ |  V  |
|  V  |  F  |

---
---

#ResumoExpressõesLogicasRelacionais
- Expressões relacionais
	- >
	- <
	- >=
	- <=
	- ==
	- !=
- Expressões lógicas
	- && (E)
	- || (OU)
	- ! (NÃO)
- Tabela Verdade