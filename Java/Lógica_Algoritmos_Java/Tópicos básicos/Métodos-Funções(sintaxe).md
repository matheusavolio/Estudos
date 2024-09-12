#Métodos-Funções(sintaxe)

# Aula61 - sintaxe das funções

#### Conceito:
- Representam um processamento que possui um significado
	- Math.sqrt(double) // calcula raiz quadrada de um valor
	- System.out.println(string)
- Principais vantagens: modularização, delegação e reaproveitamento
- Dados de entrada e saída
	- Funções podem receber dados de entrada (parâmetros ou argumentos)
	- Funções podemos ou não retornar uma saída
- Em POO, funções em classes recebem o nome de "métodos"


#### public, static e void na criação de métodos

|                        public                        |                                 static                                 |                           void                           |
| :--------------------------------------------------: | :--------------------------------------------------------------------: | :------------------------------------------------------: |
| para que a função fique dísponível em outras classes | Para que a função possa ser chamada independente de se criar um objeto | Serve para fazer uma ação sem precisar retornar um valor |

#### Exemplo:
Fazer um programa para ler três números inteiros e mostrar na tela o maior deles.

Pode ser feito assim, porém, podemos delegar isso a um método
```java
		System.out.println("Enter three numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();
        if (a > b && a > c){
            System.out.println("Higher = " + a);
        }
        else if (b > c){
            System.out.println("Higher = " + b);
        }
        else{
            System.out.println("Higher = " + c);
        }
```
#### Agora, utilizando métodos
A chamada principal, ficaria assim: 
```java
Scanner sc = new Scanner(System.in);
        System.out.println("Enter three numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();
        
        int higher = max(a, b, c);
        
        showResult(higher);
        
        sc.close();   
```

> [Explicação] 
> As variáveis `a`, `b` e `c` são atribuídas ao método `max`, que no caso são seus parâmetros, e esse resultado foi atribuído a uma variável chamada `higher`, que foi utilizado como parâmetro do método `showResult`  





#### Método para descobrir o maior valor
```java
                        // parâmetros
public static int max(int x, int y, int z) {
        int aux;
        if (x > y && x > z){
            aux = x;
            }
        else if (y > z){
            aux = y;
        }
        else{
        aux = z;
        }
        return aux; // retorna o valor de aux
    }
```

#### Método para imprimir uma mensagem junto do maior valor do método acima
```java
// não precisa retornar nada   // parâmetros   
public static void showResult(int value){
        System.out.println("Higher = " + value); // imprime a mensagem junto do valor

    }
```
