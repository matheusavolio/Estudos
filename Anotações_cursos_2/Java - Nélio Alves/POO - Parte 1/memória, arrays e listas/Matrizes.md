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
int n = sc.nextInt();  
int[][] mat = new int[n][n];  
  
for (int i=0;i<mat.leght;i++) { // percorre as linhas  
    for (int j = 0; j<mat[i].lenght; j++) { // percorre as colunas  
    mat[i][j] = sc.nextInt();  
    }  
}  
System.out.println("Main diagonal: ");  
for (int i=0;i<n;i++) {  
    System.out.print(mat[i][i] + " ");// imprime os números da diagonal
}  
int count = 0;  
for (int i=0;i<n;i++){  
    for (int j=0;j<n;j++){ 
        if (mat[i][j]<0){  
            count ++;  
        }  
    }  
}  
System.out.println();  
System.out.println("Negative numbers: " + count);
```

A função #lenght também se aplica a matrizes
