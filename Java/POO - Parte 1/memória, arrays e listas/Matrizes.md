# Aula103 - #Matrizes

- Em programação, "*Matriz*" é o nome dado a arranjos bidimensionais
	- *Atenção:* A matriz é um vetor que "contém" outros vetores
- *Arranjo (array)* é uma estrutura de dados:
	- Homogênea (dados do mesmo tipo)
	- Ordenada (elementos acessados por meio de índices (linhas e colunas))
	- Alocada de uma vez só, em um bloco contíguo de memória
- *Vantagens:*
	- Acesso imediato aos elementos pelo seus índices
- *Desvantagens:*
	- Tamanho fixo
	- Dificuldade para se realizar inserções e deleções
                ![[Matriz.jpg]]

---
---

# Aula104 - Exemplo:

### *Sintaxe básica de uma #matriz*
```java
tipoPrimitivo[][] nomeMatriz = new tipoPrimitivo [tamanho][tamanho]
```

*Exemplo de sintaxe bidimensional:*
```java
int[][] mat = new int[n][n];
```

Suponhamos que o valor de `n` seja `3`, a memória ficaria assim:
![[Matriz2.jpg]]

*Enunciado:*
Fazer um programa para ler um número inteiro N e uma matriz de ordem N contendo números inteiros. Em seguida, mostrar a diagonal principal e a quantidade de valores negativos da matriz
*Exemplo:*

| Input:  |       Output:        |
| :-----: | :------------------: |
|    3    |                      |
| 5 -3 10 |    Main diagonal:    |
| 15 8 2  |        5 8 -4        |
| 7 9 -4  | Negative numbers = 2 |

*Código:*
```java

```
