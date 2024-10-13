## Aula87 - Tipos referência vs tipo valor

#### #classes são tipos referências, variáveis cujo tipo são classes não devem ser entendidas como caixas, mas sim "tentáculos"(ponteiros) para caixas 

Classes são referências que apontam aonde está o objeto na memória, como se fosse um ponteiro que mostra em qual parte da memória essa classe está.
![[Classes_referencias 1.jpg]]

---
---

#### Valor #null 
Tipos de referência aceitam o valor "null", que indica que a variável aponta para ninguém 

---
---
#### Tipos primitivos são tipos valor
Em Java, tipos primitivos são tipos valor. Tipos valor são CAIXAS e não ponteiros

![[primitvos_caixas 1.jpg]]


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
Todos os tipos acima, são "caixas" no stack da memória

---
---
#### Tipos primitivos e inicialização
- Demo:

```java
int p;
System.out.println(p) // erro, pois a variável não foi iniciada

```

---
---

#### Valores padrão
- Quando alocamos ( #new) qualquer tipo estruturado (classe ou array) são atribuídos valores padrão aos seus elementos
	- números: 0
	- boolean: false
	- char: caractere código 0
	- objeto: null

![[memória 1.jpg]]

#### Resumo Tipos referências e tipo valor

|                                        CLASSE                                        |                                   TIPO PRIMITIVO                                   |
| :----------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------: |
|                      Vantagem: Usufrui de todos os recursos OO                       |                    Vantagem: é mais simples e mais performático                    |
|                               Variáveis são ponteiros                                |                                Variáveis são caixas                                |
| Objetos precisam ser instanciados usando new, ou apontar para um objeto ja existente |              Não instancia. Uma vez declarados estão prontos para uso              |
|                                  aceita valor null                                   |                               Não aceita valor null                                |
|                      Y = X "Y passa apontar para onde X aponta"                      |                          Y = X "Y recebe uma cópia de X"                           |
|                    Objetos instanciados na área da memória #heap                     |                  "Objetos" instanciados na área da memória #stack                  |
| Objetos não utilizados são desalocados em um momento próximo pelo garbage collector  | "Objetos" são desalocados imediatamente quando seu escopo de execução é finalizado |

---
---



