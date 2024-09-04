# Aula22 - Variáveis e tipos básicos
Em programação, variável é uma porção de memória (RAM) utilizada para armazenar dados durante a execução dos programas

 #### Declaração de variáveis
```java
<tipo> <nome> = <valor inicial>;
				(Opcional)
Uma variável possui:
- Nome
- Tipo
- Valor
- Endereço = siginifica en qual local da memória ram a variável está
```

#### Exemplo
```java
 int idade = 25; // int = número inteiro
 double altura = 1.68; // double = número com ponto flutuante(número decimal)
 char sexo = "F"; // char = receb um único caractere
```

#### Tipos primitivos

#String `-> cadeia de caracteres (palavras ou textos) sempre utilizar aspas simples ou duplas em tipos String`

|                Descrição                | Tipo       | Tamanho     | Valores                                      | Valor Padrão |
| :-------------------------------------: | ---------- | ----------- | -------------------------------------------- | :----------: |
|      **Tipos numéricos Inteiros**       | *#byte*    | ==8 bits==  | `-128 a 127`                                 |    ==0==     |
|      **Tipos numéricos inteiros**       | *#short*   | ==16 bits== | `-32768 a 32767`                             |    ==0==     |
|      **Tipos numéricos Inteiros**       | *#int*     | ==32 bits== | `-2147483648 a 2147483647`                   |    ==0==     |
|      **Tipos numéricos inteiros**       | *#long*    | ==64 bits== | `-9223372036854770000 a 9223372036854770000` |    ==0L==    |
| **Tipos numéricos com ponto flutuante** | *#float*   | ==32 bits== | `-1,4024E-37 a 3,4028E+38`                   |   ==0.0f==   |
| **Tipos numéricos com ponto flutuante** | *#double*  | ==64 bits== | `-4,94E-307 a 1,79E+308`                     |   ==0.0==    |
|        **um caractere unicode**         | *#char*    | ==16 bits== | `'\u0000' a '\uFFFF'`                        | =="\u0000"== |
|            **valor verdade**            | *#boolean* | ==1 bit==   | `{false, true}`                              |  ==false==   |
#### O que são #bits
```python
A quantidade de bits representa o número de valores possíveis diferentes que uma variável pode armazenar

Um bit pode armazenar 2 valores possíveis (0 ou 1)
Cada bit = 2 possibilidades
8 bits -> 2 x 2 x 2 x 2 x 2 x 2 x 2 x 2 = 28 = 256 possibilidades
```

#### Nomes de variáveis no formato Camel Case
- Não pode começar com dígito: sempre começar com uma letra ou ( _ )
- Não pode ter espaço em branco
- Não pode usar acentos ou ( ~ )
- Utilizar o padrão Camel Case

```java
ERRADO:
int 5minutos;
int salário;
int salario do funcionario;

CORRETO
int _5minutos;
int salario;
int salarioDoFuncionario;
```

#### O que é #CamelCase 

Camel Case é uma convenção de nomenclatura em Java (e em muitas outras linguagens de programação) onde as palavras são unidas sem espaços ou pontuações, e cada palavra subsequente começa com uma letra maiúscula. Essa convenção é amplamente utilizada para nomear variáveis, métodos e objetos, contribuindo para um código mais legível e padronizado.

Existem dois tipos principais de Camel Case:

1. **Lower Camel Case**: A primeira letra da primeira palavra é minúscula, e as primeiras letras das palavras subsequentes são maiúsculas. Exemplo: `minhaVariavel`, `calcularSoma`. Esse formato é comum para nomes de variáveis e métodos.
    
2. **Upper Camel Case (Pascal Case)**: Todas as palavras começam com uma letra maiúscula, incluindo a primeira. Exemplo: `MinhaClasse`, `CalcularSoma`. Esse formato é frequentemente usado para nomear classes e interfaces.
    

A utilização do Camel Case ajuda a manter consistência no código, facilita a leitura e a compreensão do propósito de variáveis, métodos e classes.

#ResumoAula22
-  Conceito informal 
-  Declaração de variáveis -> `<tipo> <nome> = valor; 
-  Tipos primitivos
	- Números inteiro -> byte, short, int, long
	- Números com ponto flutuante(decimais) -> float, double
	- Valor verdade -> boolean (true or false)
	- Um caractere Unicode -> char
-  Tipo String -> cadeia de caracteres (palavras, textos)
-  Nomes de variáveis / padrão Camel Case
