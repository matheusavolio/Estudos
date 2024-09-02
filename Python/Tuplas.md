# As #tuplas são estrutruas compostas e imutáveis que permitem armazenar vários valores em uma mesma estrutura, acessíveis por chaves individuais `()`  

Nas #variáveis você pode armazenar um valor, por exemplo:
`lanche = "hamburguer"


# porém, podemos utilizar #tuplas para armazenar vários valores em uma mesma estrutura
por exemplo:
`lanche = "hamburguer", "refrigerante", "batata frita"
`print(lanche)
```output:
"hamburguer", "refrigerante", "batata frita"
```


Podemos #iterar sobre as #tuplas como no #Fatiamento de #strings
para acessar qualquer índice, por exemplo:
`lanche = "hamburguer", "refrigerante", "batata frita"
`print(lanche[0])
```output: 
"hamburguer"
```

não podemos nos esquecer dos #slice : `start:end:jump

`lanche = "hamburguer", "refrigerante", "batata frita", "sorvete"
`print(lanche[0:3])`  # começa no índice 0 e para no 3.  
```output: 
"hamburguer", "refrigerante", "batata frita"
```

no exemplo acima, utilizamos o #slice para iterar sobre a tupla, lembrando que quando você seleciona o #stop do índice ele fará o output só até o índice anterior.

Exemplo:
`lanche = "hamburguer", "refrigerante", "batata frita", "sorvete"
`print(lanche[1:])`  # começa no índice 1 e para no último índice.  
```output: 
"refrigerante", "batata frita", "sorvete"
```

`lanche = "hamburguer", "refrigerante", "batata frita", "sorvete"
`print(lanche[::2])`  # começa no primeiro índice e para no último, pulando de 2 em 2 
```output: 
"hamburguer", "batata frita"
```

Para podermos imprimir o conteúdo da tupla de traz para frente, podemos utilizar o #slice  negativo, por exemplo:
`lanche = "hamburguer", "suco", "pizza", "pudim"
`print(lanche[::-1])

```output
('pudim', 'pizza', 'suco', 'hamburguer')
```

Também podemos utilizar o #slice negativo no #for 
`lanche = "hamburguer", "suco", "pizza", "pudim"
`for c in lanche[::-1]:
    `print(c)
```output
pudim
pizza
suco
hamburguer  
```


Também podemos utilizar o #len para imprimir quantos elementos tem dentro da #tupla 
`lanche = "hamburguer", "refrigerante", "batata frita"
`print(len(lanche))
```output: 
3
```

Podemos também usar #EstruturasDeRepetição dentro das tuplas, exemplo com #for:
``lanche = "hamburguer", "refrigerante", "batata frita"
`for c in lanche:
   `` print(c)
```output: 
`hamburguer
`refrigerante`
`batata frita```
```


# As tuplas são imutáveis, não é possível remover  um elemento de dentro de uma tupla
Por exemplo:
`lanche = "hamburguer", "suco", "pizza", "pudim"
`lanche[1] = "Refrigerante"
`print(lanche[1])
```ouput 
será um erro de TypeError``` 
```


e podemos retirar as aspas e vírgulas do ouput das tuplas da seguinte maneira;
`lanche = "hamburguer", "suco", "pizza", "pudim"
`for c in lanche:
    `print(c, end=" ")
   utilizamos o for c para percorrer a tupla, e a cada vez percorrida, irá imprimir seu índice na sequência, e utilizei o end=" " para imprimir todos na mesma linha


outro méotodo:

`lanche = "hamburguer", "suco", "pizza", "pudim", "batata frita"
`for c in range(0, len(lanche)):
    `print(lanche[c])

ira começar no índice 0
o #len, serve para que o fim do loop seja o total de seu índice
irá ser impresso o output ao invés dos números de 0 a 4, será impresso os elementos de dentro da tupla

e para mostrar a posição dos elementos dentro da tupla:
`lanche = "hamburguer", "suco", "pizza", "pudim", "batata frita"
`for c in range(0, len(lanche)):
    `print(f"comi {lanche[c]}, na posição {c}")
 ```output
comi hamburguer na posição 0
comi suco na posição 1        
comi pizza na posição 2       
comi pudim na posição 3       
comi batata frita na posição 4
``` 

outra forma de acessar o índice junto do elemento, é utilizar o #enumerate:
`lanche = "hamburguer", "suco", "pizza", "pudim", "batata frita"
`for pos, comida in enumerate(lanche)
    `print(f"comi {comida}, na posição {pos}")
 ```output
comi hamburguer, na posição 0
comi suco, na posição 1        
comi pizza, na posição 2       
comi pudim, na posição 3       
comi batata frita, na posição 4
```

E para colocar a tupla em ordem, podemos utilizar o método #sorted:
`lanche = "hamburguer", "suco", "pizza", "pudim", "batata frita"
`print(sorted(lanche))
```output
['batata frita', 'hamburguer', 'pizza', 'pudim', 'suco']
```

Podemos #concatenar as tuplas atribuindo elas a uma nova variavel e depois utilizando um sinal de +
`a = 2, 5 , 4
`b = 5, 8, 1, 2
`c = a + b
`print(c)
```output
(2, 5, 4, 5, 8, 1, 2)
```
a ordem é influenciada com base na sua posição entre o +, por exemplo:
`a = 2, 5 , 4
`b = 5, 8, 1, 2
`c = b + a
`print(c)
```output
(5, 8, 1, 2, 2, 5, 4)
```
Podemos utilizar o método #count dentro das tuplas também, por exemplo:
`a = 2, 5 , 4
`b = 5, 8, 1, 2
`c = b + a
`print(c.count(5))
```output
2
```
Além do count, podemos utilizar o #index para descobrir em qual índice está um elemento, por exemplo: 
`a = 2, 5 , 4
`b = 5, 8, 1, 2
`c = b + a
`print(c.index(8))
```output
1
```
Dentro de uma tupla, pode ser colocado números inteiros, strings, float, por exemplo:
`pessoa = "Matheus", 19, "M", 98.10
`print(pessoa)
```output
('Matheus', 19, 'M', 98.1)
```
Também podemos pedir para o usuário inserir os dados e depois adicionar eles as tuplas:
`pessoa = str(input("Insira seu nome: "))
`idade = int(input("Insira sua idade: "))
`tupla = pessoa, idade
`print(tupla)
```output
Insira seu nome: Matheus
Insira sua idade: 19
('Matheus', 19)
```

As tuplas são imútaveis, porém podemos apagar elas:
`pessoa = "Matheus", 19, "M", 98.10
`del(pessoa)
`print(pessoa)
```output
Erro de NameError
```

Explicação do #len dentro do #for 

`lanche = "hamburguer", "suco", "pizza", "pudim"
`for c in range(0, len(lanche)):
    `print(lanche[c])
    
1. **Declaração da Tupla `lanche`**:
    
    
    `lanche = "hamburguer", "suco", "pizza", "pudim"`
    
    - Aqui, uma tupla chamada `lanche` é criada com quatro elementos: `"hamburguer"`, `"suco"`, `"pizza"`, `"pudim"`.
    - As tuplas são imutáveis, ou seja, não podem ser alteradas após a criação.


2. **Início do Loop `for`**:
    
    `for c in range(0, len(lanche)):`
    
    - Este loop `for` irá iterar sobre um intervalo de valores, de `0` até `len(lanche) - 1`.
    - `len(lanche)` retorna o comprimento da tupla, que neste caso é `4`.
    - Portanto, `range(0, len(lanche))` gera a sequência `[0, 1, 2, 3]`.

3. **Impressão de cada Elemento da Tupla**: 

    
    `print(lanche[c])`
    
    - Dentro do loop, `lanche[c]` acessa o elemento da tupla no índice `c`.
    - A função `print()` imprime este elemento.

```output
hamburguer
suco
pizza
pudim
```

# Exercício 1:

`num1 = "zero", "um", "dois", "tres", "quatro", "cinco", "seis", "sete", "oito", `"nove", "dez", "onze", "doze", "treze", "quatorze", "quinze", "dezesseis", "dezessete", `"dezoito", "dezenove", "vinte"
`while True:
    `num2 = int(input("Insira um número entre 0 e 20: "))
    `if num2 >20 or num2 < 0:
        `print("Tente novamente!")
    `else:
        `print("-=-"*10)    
        `print(f"Você digitou o {num1[num2]}")
        `print("Programa encerrado. Volte sempre!")
        `print("-=-"*10)
        `break



`num1 = "zero", "um", "dois", "tres", "quatro", "cinco", "seis", "sete", "oito", "nove", "dez", "onze", "doze", "treze", "quatorze", "quinze", "dezesseis", "dezessete", "dezoito", "dezenove", "vinte"`
Aqui, estamos criando uma tupla chamada `num1` que contém as representações textuais dos números de 0 a 20.


`while True:`
Estamos iniciando um laço `while` infinito, que só será interrompido com um comando `break`.


    `num2 = int(input("Insira um número entre 0 e 20: "))`
Dentro do laço, pedimos ao usuário que insira um número entre 0 e 20. O valor inserido é convertido para um inteiro e armazenado na variável `num2`.


    `if num2 > 20 or num2 < 0:       
		print("Tente novamente!")`
Aqui, verificamos se o número inserido está fora do intervalo permitido (0 a 20). Se estiver, imprimimos a mensagem "Tente novamente!".



    `else:         
	    print("-=-" * 10)         
	    print(f"Você digitou o {num1[num2]}")         
	    print("Programa encerrado. Volte sempre!")         
	    print("-=-" * 10)         
	    break`
Se o número estiver dentro do intervalo permitido, entramos no bloco `else`:

1. `print("-=-" * 10)`: Imprime uma linha de separação decorativa.
2. `print(f"Você digitou o {num1[num2]}")`: Utilizamos o número inserido (`num2`) como índice para acessar a tupla `num1` e imprimir o nome correspondente ao número.
3. `print("Programa encerrado. Volte sempre!")`: Imprime uma mensagem de encerramento.
4. `print("-=-" * 10)`: Imprime outra linha de separação decorativa.
5. `break`: Sai do laço `while`, encerrando o programa.

### Explicação Completa

Este programa solicita ao usuário que insira um número entre 0 e 20. Se o número estiver fora desse intervalo, o programa pede para tentar novamente. Quando um número válido é inserido, o programa imprime o nome correspondente ao número, uma mensagem de encerramento e termina.

Vamos pensar que o usuário vai inserir o número 19, esse será o output:
```output
Insira um número entre 0 e 20: 19
-=--=--=--=--=--=--=--=--=--=-   
Você digitou o dezenove
Programa encerrado. Volte sempre!
-=--=--=--=--=--=--=--=--=--=-   
```

# Exercício 2:

` from random import randint
`n = (randint(1, 10), randint(1, 10), randint(1, 10),
     `randint(1, 10), randint(1, 10))
`for c in range(0, len(n)):
    `print(n[c], end=" ")
`print(f"\nO maior número sorteado foi: {max(n)}")
`print(f"O menor número sorteado foi: {min(n)}")   



`from random import randint`
Aqui, importamos a função `randint` do módulo `random`, que nos permite gerar números inteiros aleatórios.



`n = (randint(1, 10), randint(1, 10), randint(1, 10),     
	`randint(1, 10), randint(1, 10))`
Nesta linha, criamos uma tupla `n` que contém cinco números inteiros aleatórios entre 1 e 10. A função `randint(1, 10)` é chamada cinco vezes para gerar esses números.



`for c in range(0, len(n)):     
	`print(n[c], end=" ")`
Usamos um laço `for` para iterar sobre os índices da tupla `n`. O laço percorre os valores de `0` até `len(n) - 1`, que é o comprimento da tupla menos 1.

- `range(0, len(n))`: Gera uma sequência de números de `0` a `len(n) - 1`.
- `print(n[c], end=" ")`: Imprime o elemento da tupla `n` no índice `c`, seguido de um espaço em branco em vez de uma nova linha.


`print(f"\nO maior número sorteado foi: {max(n)}")`
Aqui, usamos a função `max` para encontrar o maior número na tupla `n` e imprimimos o resultado.


`print(f"O menor número sorteado foi: {min(n)}")`
Da mesma forma, usamos a função `min` para encontrar o menor número na tupla `n` e imprimimos o resultado.

### Explicação Completa

Este programa gera uma tupla de cinco números inteiros aleatórios entre 1 e 10. Em seguida, ele imprime cada número da tupla em uma linha, seguido por uma mensagem indicando o maior e o menor número sorteados.

Aqui está um exemplo de execução do programa:

```output
4 7 1 10 3  
O maior número sorteado foi: 10 
O menor número sorteado foi: 1`
```


# Exercício 3:


``num = (int(input("Digite um número: ")),
    `int(input("Digite outro número: ")),
    `int(input("Digite mais um número: ")),
    `int(input("Digite o último número: ")))
`print(f"Você digitou os valores {num}")
`print(f"Você digitou o número 9: {num.count(9)} vezes")
`if 3 in num:
    `print(f"O valor 3 apareceu na {num.index(3)+1}º posição")
`else:
    `print("O valor 3 não foi digitado em nenhuma posição.")
`print("Os valores pares foram: ", end=" ")
`for n in num:
    `if n % 2 == 0:
        `print(n, end=" ")



`num = (int(input("Digite um número: ")),
	`int(input("Digite outro número: ")),     
	`int(input("Digite mais um número: ")),     
	`int(input("Digite o último número: ")))`
Aqui, estamos criando uma tupla `num` que contém quatro números inteiros fornecidos pelo usuário. Usamos a função `input()` para solicitar cada número e `int()` para convertê-los em inteiros.


`print(f"Você digitou os valores {num}")`
Imprimimos a tupla `num`, mostrando os valores digitados pelo usuário.


`print(f"Você digitou o número 9: {num.count(9)} vezes")`
Usamos o método `count()` para contar quantas vezes o número 9 aparece na tupla `num` e imprimimos o resultado.



`if 3 in num:     
	`print(f"O valor 3 apareceu na {num.index(3)+1}º posição") 
`else:     
	`print("O valor 3 não foi digitado em nenhuma posição.")`
Aqui, verificamos se o número 3 está presente na tupla `num` usando a expressão `3 in num`. Se estiver presente, usamos o método `index()` para encontrar a posição do primeiro 3 na tupla e imprimimos essa posição (somamos 1 porque os índices em Python começam em 0). Se o 3 não estiver presente, imprimimos uma mensagem informando isso.


`print("Os valores pares foram: ", end=" ") 
	`for n in num:     
	`if n % 2 == 0:         
		`print(n, end=" ")`
Nesta parte, iteramos sobre cada número na tupla `num` usando um laço `for`. Para cada número `n`, verificamos se ele é par (ou seja, se `n % 2 == 0`). Se for, imprimimos o número seguido de um espaço em branco.



Este programa solicita ao usuário quatro números inteiros e os armazena em uma tupla. Em seguida, ele realiza as seguintes operações:

1. Imprime todos os números digitados.
2. Conta quantas vezes o número 9 foi digitado e imprime o resultado.
3. Verifica se o número 3 está presente na tupla e, se estiver, imprime sua posição. Caso contrário, informa que o 3 não foi digitado.
4. Itera sobre a tupla e imprime todos os números pares.

```output
Digite um número: 2 
Digite outro número: 9 
Digite mais um número: 3 
Digite o último número: 6
Você digitou os valores (2, 9, 3, 6) 
Você digitou o número 9: 1 vezes 
O valor 3 apareceu na 3º posição 
Os valores pares foram: 2 6
```




# Exercício 4:

`tupla = ("Lápis", 1.75,
         `"Borracha", 2.00,
         `"Caderno", 15.90,
         `"Estojo", 25.00,
         `"Transferidor", 4.20,
         `"Compasso", 9.99,
         `"Mochila", 120.32,
          `"Canetas", 22.30,
          `"Livro", 34.90 )
`for pos in range(0, len(tupla)):
    `if pos % 2 == 0:
        `print(f"\n{tupla[pos]:.<20}", end="")
    `else:
        `print(f"R$ {tupla[pos]:.2f}")


# Análise: 

`tupla = ("Lápis", 1.75,
	`"Borracha", 2.00,           
	`"Caderno", 15.90,           
	`"Estojo", 25.00,           
	`"Transferidor", 4.20,           
	`"Compasso", 9.99,           
	`"Mochila", 120.32,         
	`"Canetas", 22.30,           
	`"Livro", 34.90)`
Aqui, criamos uma tupla chamada `tupla` que contém pares de valores: o nome de um item (como uma string) e seu preço (como um float).



`for pos in range(0, len(tupla)):`
Usamos um laço `for` para iterar sobre os índices da tupla `tupla`. A função `range(0, len(tupla))` gera uma sequência de números de `0` até `len(tupla) - 1`.

    `if pos % 2 == 0:`
Dentro do laço, verificamos se o índice `pos` é par usando `pos % 2 == 0`. Isso nos ajuda a identificar os nomes dos itens, que estão nas posições pares da tupla.



        `print(f"\n{tupla[pos]:.<20}", end="")`
Se o índice for par, imprimimos o nome do item. Usamos a formatação `f"\n{tupla[pos]:.<20}"` para imprimir o nome do item seguido de pontos (`.`) até que a string tenha 20 caracteres. O `\n` adiciona uma nova linha antes de imprimir o item, e `end=""` evita que o `print` acrescente uma nova linha ao final.



    `else:        
	     print(f"R$ {tupla[pos]:.2f}")`
Se o índice for ímpar, imprimimos o preço do item. Usamos a formatação `f"R$ {tupla[pos]:.2f}"` para garantir que o preço seja exibido com duas casas decimais.

### Explicação Completa

Este programa percorre uma tupla contendo pares de itens e seus preços. Para cada par, ele imprime o nome do item alinhado à esquerda e preenchido com pontos até completar 20 caracteres, seguido pelo preço do item formatado com duas casas decimais.


```output
Lápis...............R$ 1.75 
Borracha............R$ 2.00 
Caderno.............R$ 15.90 
Estojo..............R$ 25.00 
Transferidor........R$ 4.20 
Compasso............R$ 9.99 
Mochila.............R$ 120.32 
Canetas.............R$ 22.30 
Livro...............R$ 34.90
```


# Exercício 5

`tupla = ("Caderno", "Lapis", "Isqueiro", "Cigarro", "Cachorro", "Gato", 
	`"Papagaio", "Cidade" )
`for p in tupla:
    `print(f"\nNa palavra {p} temos: ", end="")
    `for letra in p:
        `if letra.lower() in "aeiou":
            `print(letra, end=" ")





`tupla = ("Caderno", "Lapis", "Isqueiro", "Cigarro", "Cachorro", "Gato", "Papagaio", "Cidade")`
Aqui, criamos uma tupla `tupla` que contém várias palavras.


`for p in tupla:`
Usamos um laço `for` para iterar sobre cada palavra na tupla `tupla`. A variável `p` representa cada palavra individualmente durante a iteração.


    `print(f"\nNa palavra {p} temos: ", end="")`
Para cada palavra `p`, imprimimos a frase "Na palavra {p} temos: " e iniciamos a linha sem adicionar uma nova linha ao final (`end=""`), para que possamos continuar imprimindo na mesma linha.


    `for letra in p:`
Usamos um segundo laço `for` para iterar sobre cada letra da palavra `p`.


        `if letra.lower() in "aeiou":`
Verificamos se a letra, convertida para minúscula (`letra.lower()`), está na string `"aeiou"`, que contém todas as vogais.


            `print(letra, end=" ")`
Se a letra for uma vogal, ela é impressa seguida por um espaço, novamente sem adicionar uma nova linha ao final (`end=""`).

### Explicação Completa

Este programa percorre uma tupla de palavras, imprimindo cada palavra seguida pelas vogais que ela contém. O uso de `letra.lower()` garante que a verificação de vogais seja insensível a maiúsculas e minúsculas. A saída é formatada para que todas as vogais de uma palavra sejam impressas na mesma linha, logo após a palavra.

```output
Na palavra Caderno temos: a e o      
Na palavra Lapis temos: a i 
Na palavra Isqueiro temos: I u e i o 
Na palavra Cigarro temos: i a o      
Na palavra Cachorro temos: a o o     
Na palavra Gato temos: a o 
Na palavra Papagaio temos: a a a i o 
Na palavra Cidade temos: i a e  
```

