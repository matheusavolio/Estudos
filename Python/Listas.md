#Listas 

As listas são variáveis compostas que permitem armazenar vários valores em uma mesma estrutura, acessíveis por chaves individuais.

Diferente das #tuplas que são demarcadas por parêntesis e vírgulas e são imutáveis.
As listas são demarcadas por colchetes `[]` e separando seus elementos com vírgulas, e diferente das tuplas, as listas são mutáveis 

Exemplo de mutabilidade:
`my_list = ["hamburguer", "suco", "pizza", "pudim"]
`my_list[0] = "picole"
`print(my_list)
```output
['picole', 'suco', 'pizza', 'pudim']
```

### Métodos das Listas em Python

As listas em Python são uma estrutura de dados flexível que permite armazenar e manipular coleções de itens. Aqui está um resumo detalhado de todos os métodos disponíveis para listas:

#### 1. #append(x)

- **Descrição**: Adiciona um item ao final da lista.
- **Exemplo**:
    
    
    `lista = [1, 2, 3] 
    `lista.append(4) # lista agora é [1, 2, 3, 4]`
    

#### 2. #extend(iterável)

- **Descrição**: Estende a lista adicionando todos os itens do iterável fornecido.
- **Exemplo**:
    
    
    `lista = [1, 2, 3] 
    `lista.extend([4, 5]) # lista agora é [1, 2, 3, 4, 5]`
    

#### 3. #insert(i, x)

- **Descrição**: Insere um item no índice especificado.
- `list.insert(índice, item)
- **Exemplo**:
    
    
    `lista = [1, 2, 3] 
    `lista.insert(1, 'a') # lista agora é [1, 'a', 2, 3]`
    

#### 4. #remove(x)

- **Descrição**: Remove a primeira ocorrência do item especificado.
- **Exemplo**:
    
    
    `lista = [1, 2, 3, 2] 
    `lista.remove(2) # lista agora é [1, 3, 2]`
    

#### 5. #pop`([i])`

- **Descrição**: Remove e retorna o item no índice especificado. Se nenhum índice for especificado, remove e retorna o último item.
- **Exemplo**:
    
    
    `lista = [1, 2, 3] 
    `lista.pop() # Retorna 3 e lista agora é [1, 2]`
    

#### 6.  #clear()`

- **Descrição**: Remove todos os itens da lista.
- **Exemplo**:
    
    `lista = [1, 2, 3] 
    `lista.clear() # lista agora é []`
    

#### 7.  #index`(x[, start[, end]])`

- **Descrição**: Retorna o índice da primeira ocorrência do item especificado. Opcionalmente, pode especificar os índices de início e fim para a busca.
- **Exemplo**:
    
    
    `lista = [1, 2, 3, 2]
	`lista2 = lista.index(2)
	`print(lista2) # Retorna 1`
    

#### 8.  #count`(x)

- **Descrição**: Retorna o número de ocorrências do item especificado na lista.
- **Exemplo**:
    
``    num = list(range(1, 11))
	`num2 = num.count(3)
	`print(num2) # retorna 1
    

#### 9. #sort`(key=None, reverse=False)`

- **Descrição**: Ordena os itens da lista no local (in-place). Pode usar uma função de chave opcional e um parâmetro para ordenar em ordem reversa.
- **Exemplo**:
    
    `lista = [3, 1, 2] 
    `lista.sort() # lista agora é [1, 2, 3]  
    `lista.sort(reverse=True) # lista agora é [3, 2, 1]`
    

#### 10. #reverse()`

- **Descrição**: Inverte os itens da lista no local (in-place).
- **Exemplo**:
    
    
    `lista = [1, 2, 3] 
    `lista.reverse() # lista agora é [3, 2, 1]`
    

#### 11.  #copy()`

- **Descrição**: Retorna uma cópia rasa (shallow copy) da lista.
- **Exemplo**:
    
    
    `lista = [1, 2, 3] 
    `nova_lista = lista.copy() # nova_lista é [1, 2, 3], lista original não é alterada`


	#del `list(x)
-  Remove o índice especificado

`my_list = ["hamburguer", "suco", "pizza", "pudim"]
`del my_list[2]
`print(my_list)

```output
['hamburguer', 'suco', 'pudim']
```



# Exemplo de uso de vários métodos 
`lista = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5] 

`# Adiciona um item ao final 
`lista.append(7) 
`print(lista) # [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5, 7] 

`# Estende a lista com outro iterável 
`lista.extend([8, 9, 7]) 
`print(lista) # [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5, 7, 8, 9, 7] 

`# Insere um item no índice especificado 
`lista.insert(2, 10) 
`print(lista) # [3, 1, 10, 4, 1, 5, 9, 2, 6, 5, 3, 5, 7, 8, 9, 7] 

`# Remove a primeira ocorrência do item 
`lista.remove(5) 
`print(lista) # [3, 1, 10, 4, 1, 9, 2, 6, 5, 3, 5, 7, 8, 9, 7] 

`# Remove e retorna o item no índice especificado 
`print(lista.pop(3)) # 4 
`print(lista) # [3, 1, 10, 1, 9, 2, 6, 5, 3, 5, 7, 8, 9, 7] 

`# Remove todos os itens da lista 
`lista.clear() 
`print(lista) # [] 

`# Cria uma nova lista para outros métodos 
`lista = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5] 

`# Retorna o índice da primeira ocorrência 
`print(lista.index(9)) # 5 

`# Retorna o número de ocorrências do item 
`print(lista.count(5)) # 3 

`# Ordena os itens da lista 
`lista.sort() 
`print(lista) # [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9] 

`# Inverte os itens da lista 
`lista.reverse() 
|`print(lista) # [9, 6, 5, 5, 5, 4, 3, 3, 2, 1, 1] 

`# Retorna uma cópia rasa da lista 
`nova_lista = lista.copy() 
`print(nova_lista) # [9, 6, 5, 5, 5, 4, 3, 3, 2, 1, 1]


# Podemos utilizar o #range para criar listas também
Por exemplo:
`lista = list(range(4, 11))
`print(lista)
```output
[4, 5, 6, 7, 8, 9, 10]
```

# Para saber o tamanho de uma lista, podemos usar a função #len 
`lista = list(range(4, 11))
`print(len(lista))
```output
7
```

`lista = list(range(1, 11))
`print(f"A minha lista é {lista} e ela tem {len(lista)} elementos")`
```output
A minha lista é [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] e ela tem 10 elementos
```


# Criando uma lista de trás pra frente utilizando #for, adicionando um elemento com #append e #insert removendo elementos com #remove, organizando a lista com #sort, utilizando o #if-else para remover um número se ele estiver na lista imprimindo a lista e o comprimento dela com #len 
`lista = list(range(10, 0, -1))
`lista.append(7)
`lista.insert(2, 2)
`lista.remove(2)
`if 54 in lista:`
	`lista.remove(54)`
`else:
	`print("Não achei o número 54")`
`lista.sort(reverse=True)
`print(f"A minha lista é {lista} e ela tem {len(lista)} elementos")
```output
Não achei o número 54
A minha lista é [10, 9, 8, 7, 7, 6, 5, 4, 3, 2, 1] e ela tem 11 elementos
```

# Utilizando uma #lista vazia e pedindo para o usuário digitar dois números após o usuário digitar o primeiro número, utilizo o #append para adicionar esse valor a lista e repito o mesmo comando novamente, apos isso imprimo os resultados que estão na lista e depois imprimo a soma desses elementos utilizando #sum 
`lista = []
`var = int(input("Insira um número: "))
`lista.append(var)
`var = int(input("Insira um número: "))
`lista.append(var)
`print(lista)
`print(sum(lista))
```output
[5, 10]       
15
```


# Repito o mesmo processo acima, porém utilizo o #for para acessar cada valor dentro da lista e imprimir uma mensagem, e por fim imprimo a soma dos elementos da lista
`lista = []
`var = int(input("Insira um número: "))
`lista.append(var)
`var = int(input("Insira um número: "))
`lista.append(var)
`for valor in lista:
    `print(f"Temos o valor {valor}")
`print(f"E a soma deles é {sum(lista)}")
```output
Insira um número: 5
Insira um número: 10
Temos o valor 5    
Temos o valor 10   
E a soma deles é 15
```


# Repito o mesmo processo acima, porém utilizo o #for para acessar cada valor dentro da lista e o #enumerate para acessar o índice desses elementos, e por fim imprimo a soma dos elementos da lista
`lista = []
`var = int(input("Insira um número: "))
`lista.append(var)
`var = int(input("Insira um número: "))
`lista.append(var)
`for c ,valor in enumerate(lista):
    `print(f"Na posição: {c} Temos o valor: {valor}")
`print(f"E a soma deles é {sum(lista)}")
```output
Insira um número: 5
Insira um número: 10
Na posição: 0 Temos o valor: 5 
Na posição: 1 Temos o valor: 10
E a soma deles é 15
```



# Crio uma lista vazia, utilizo um loop for para fazer um loop de 0 até 6 e nessas impressões peço para o usuário digitar um número 6 vezes, e toda vez que ele digita esse número ele é direcionado para a lista utilizando o #append. Ao final desse loop faço um outro for utilizando o #enumerate para obter o índice dos elementos da lista e ímprimo cada elemento com seu índice, e por fim somo todos os elementos com o #sum 
`lista = []
`for c in range(0, 6):
    `lista.append(int(input("Digite um valor: ")))
`for c ,valor in enumerate(lista):
    `print(f"Na posição: {c} Temos o valor: {valor}")
`print(f"E a soma deles é {sum(lista)}")
```output
Digite um valor: 5
Digite um valor: 10
Digite um valor: 15
Digite um valor: 20
Digite um valor: 25
Digite um valor: 30
Na posição: 0 Temos o valor: 5 
Na posição: 1 Temos o valor: 10
Na posição: 2 Temos o valor: 15
Na posição: 3 Temos o valor: 20
Na posição: 4 Temos o valor: 25
Na posição: 5 Temos o valor: 30
E a soma deles é 105
```



# Quando você iguala uma lista como no exemplo abaixo, você não faz uma cópia, e sim uma ligação, portanto se você mexer na lista "b", a lista "a" também será alterada. 
`a = [2, 3, 4, 7]
`b = a
`b[2] = 8
`print(f"Lista a: {a}")
`print(f"Lista b: {b}")
```output
Lista a: [2, 3, 8, 7]
Lista b: [2, 3, 8, 7]
```


# Porém, se eu  colocar um slice dentro de "b" recebe "a" ele não irá criar essa ligação, e sim irá copiar os elementos de dentro da lista "a"
`a = [2, 3, 4, 7]
`b = a[:]
`b[2] = 8
`print(f"Lista a: {a}")
`print(f"Lista b: {b}")
```output
Lista a: [2, 3, 4, 7]
Lista b: [2, 3, 8, 7]
```



`lista = []
`par = []
`ímpar = []
`continuar = "s"
`while continuar != "n":
    `var = int(input(f"Insira um número: "))
    `lista.append(var)
    `continuar = str(input("Você quer continuar? [S/N] ")).lower().strip()
    `if var % 2 == 0:
        `par.append(var)
    `else:
        `ímpar.append(var)
    `if continuar =="n":
        `print(f"Os números que você inseriu foram: {lista}")
        `print(f"Os números pares foram: {par}")
        `print(f"Os números ímpares foram {ímpar}")
        `break





- `continuar = "s"`
    
    - Aqui, uma variável chamada `continuar` é definida e inicializada com o valor `"s"`. Esta variável será usada para controlar o loop `while`.

- `lista = []`
    - Esta linha define uma lista vazia chamada `lista`. Esta lista será usada para armazenar os números inseridos pelo usuário.
- `while continuar != "n":`
    - Esta linha inicia um loop `while` que continuará a executar enquanto o valor de `continuar` não for `"n"`.
- `var = int(input("Insira um número: "))`
    
    - Esta linha solicita ao usuário que insira um número. A função `input` exibe a mensagem `"Insira um número: "` e aguarda a entrada do usuário. O valor inserido é convertido para um inteiro usando a função `int` e armazenado na variável `var`.
5. `if var in lista:`
    
    - Esta linha verifica se o número inserido pelo usuário (`var`) já está presente na lista `lista`. Se estiver, a próxima linha será executada. Caso contrário, o código dentro do `else` será executado.
6. `print(f"Valor duplicado")`
    
    - Se o número inserido (`var`) já estiver na lista, esta linha exibe a mensagem `"Valor duplicado"` para o usuário.
7. `else:`
    
    - Se o número inserido (`var`) não estiver na lista, o código dentro deste bloco `else` será executado.
8. `lista.append(var)`
    
    - Esta linha adiciona o número inserido (`var`) à lista `lista` usando o método `append`.
9. `continuar = str(input(f"Quer continuar? [S/N] ")).lower().strip()`
    
    - Esta linha solicita ao usuário que indique se deseja continuar ou não. A função `input` exibe a mensagem `"Quer continuar? [S/N] "` e aguarda a entrada do usuário. O valor inserido é convertido para uma string (`str`), transformado para letras minúsculas (`lower`) e quaisquer espaços em branco no início ou no final são removidos (`strip`). O resultado é armazenado na variável `continuar`.
10. `if continuar == "n":`
    
    - Esta linha verifica se o valor de `continuar` é `"n"`. Se for, a próxima linha será executada.
11. `print(lista)`
    
    - Se o valor de `continuar` for `"n"`, esta linha imprime a lista `lista` contendo todos os números inseridos pelo usuário.
12. `break`
    
    - Esta linha termina o loop `while`. O programa sai do loop e não executa mais as iterações.

### Funcionamento Geral:

- O programa solicita ao usuário que insira um número e verifica se esse número já está na lista.
- Se o número já estiver na lista, informa que o valor é duplicado.
- Se o número não estiver na lista, ele é adicionado.
- O usuário é então perguntado se deseja continuar inserindo números. Se o usuário digitar `"n"`, o programa exibe a lista de números inseridos e termina. Caso contrário, o loop continua até que o usuário decida parar.




`lista = []
`for c in range(0, 5):
    `n = (int(input("Digite um valor: ")))
    `if c == 0 or n > lista[-1]:
        `lista.append(n)
        `print("Adicionado ao final da lista...")
    `else:
        `pos =  0
        `while pos < len(lista):
            `if n <= lista[pos]:
	            `lista.insert(pos, n)
             `print(f"Adicionado na posição {pos}")
                `break
            `pos+=1
`print("-=-"*30)
`print(f"Os valores digitados foram: {lista}")


1. **Inicialização:**
    
    - `lista = []`: Cria uma lista vazia chamada `lista` para armazenar os valores inseridos.
2. **Loop `for`:**
    
    - `for c in range(0, 5):`: Inicia um loop `for` que executa 5 vezes, com `c` assumindo valores de 0 a 4.
3. **Entrada do Usuário:**
    
    - `n = (int(input("Digite um valor: ")))`: Solicita ao usuário que digite um valor e converte a entrada para um inteiro. O valor é armazenado na variável `n`.
4. **Inserção na Lista:**
    
    - `if c == 0 or n > lista[-1]:`: Verifica se é a primeira iteração (`c == 0`) ou se o valor `n` é maior que o último elemento da lista (`lista[-1]`).
        - `lista.append(n)`: Se a condição for verdadeira, adiciona `n` ao final da lista.
        - `print("Adicionado ao final da lista...")`: Imprime uma mensagem indicando que o valor foi adicionado ao final da lista.
    - `else:`: Se a condição não for verdadeira, executa o bloco `else`.
5. **Inserção em Posição Específica:**
    
    - `pos = 0`: Inicializa a variável `pos` com o valor 0. Esta variável será usada para encontrar a posição correta para inserir `n`.
    - `while pos < len(lista):`: Inicia um loop `while` que executa enquanto `pos` for menor que o comprimento da lista.
        - `if n <= lista[pos]:`: Verifica se `n` é menor ou igual ao elemento da lista na posição `pos`.
            - `lista.insert(pos, n)`: Insere `n` na posição `pos`.
            - `print(f"Adicionado na posição {pos}")`: Imprime uma mensagem indicando a posição onde `n` foi inserido.
            - `break`: Sai do loop `while`.
        - `pos += 1`: Incrementa `pos` em 1 para verificar a próxima posição na lista.
6. **Impressão dos Resultados:**
    
    - `print("-=-"*30)`: Imprime uma linha de separação.
    - `print(f"Os valores digitados foram: {lista}")`: Imprime a lista de valores digitados, que agora está ordenada.

### Resumo do Funcionamento:

- O programa solicita ao usuário que insira 5 valores.
- Cada valor é inserido na lista `lista` de forma que a lista permaneça ordenada.
- Se o valor inserido for maior que o último valor da lista ou se for o primeiro valor, ele é adicionado ao final da lista.
- Caso contrário, o valor é inserido na posição correta para manter a lista ordenada.
- No final, o programa imprime a lista ordenada.





`expr = str(input("Degite a expressão: "))
`pilha = []
`for simb in expr:
    `if simb == "(":
        `pilha.append("(")
    `elif simb == ")":
        `if len(pilha) >0:
            `pilha.pop()
        `else:
            `pilha.append(")")
            `break
`if len(pilha) == 0:
    `print("Sua expressão está válida!")
`else:
    `print("Sua expressão está incorreta!")


- **Entrada do Usuário:**
    
    - `expr = str(input("Digite a expressão: "))`: Solicita ao usuário que digite uma expressão e converte a entrada para uma string, armazenando-a na variável `expr`.
- **Inicialização da Pilha:**
    
    - `pilha = []`: Cria uma lista vazia chamada `pilha`. Esta lista será usada como uma pilha para verificar o balanceamento dos parênteses na expressão.
- **Loop `for` para Análise da Expressão:**
    
    - `for simb in expr:`: Inicia um loop `for` que percorre cada caractere (`simb`) na expressão `expr`.
- **Verificação de Parênteses Abertos:**
    
    - `if simb == "(":`: Verifica se o caractere atual é um parêntese aberto `(`.
        - `pilha.append("(")`: Se for um parêntese aberto, adiciona-o à pilha.
- **Verificação de Parênteses Fechados:**
    
    - `elif simb == ")":`: Verifica se o caractere atual é um parêntese fechado `)`.
        - `if len(pilha) > 0:`: Verifica se a pilha não está vazia.
            - `pilha.pop()`: Se a pilha não estiver vazia, remove o último parêntese aberto adicionado à pilha.
        - `else:`: Se a pilha estiver vazia:
            - `pilha.append(")")`: Adiciona o parêntese fechado à pilha para indicar um erro de balanceamento.
            - `break`: Interrompe o loop, pois a expressão já está incorreta.
- **Verificação Final da Pilha:**
    
    - `if len(pilha) == 0:`: Verifica se a pilha está vazia após o loop.
        - `print("Sua expressão está válida!")`: Se a pilha estiver vazia, significa que todos os parênteses abertos foram corretamente fechados, e a expressão é válida.
    - `else:`: Se a pilha não estiver vazia:
        - `print("Sua expressão está incorreta!")`: Se a pilha não estiver vazia, significa que há um desequilíbrio nos parênteses, e a expressão é inválida.



# Podemos também colocar uma lista dentro de uma outra lista
Por exemplo:

`pessoas = [["Pedro", 25], ["Maria", 19], ["João", 32]]
`lista = []
`lista.append(int(input("Insira um número: ")))
`pessoas.append(lista[:])
`print(pessoas)
```output
Insira um número: 10
[['Pedro', 25], ['Maria', 19], ['João', 32], [10]]
```

No exemplo acima, criamos a lista pessoas com 3 estruturas, após isso criei uma lista vazia chamada lista e pedi para o usuário inserir um número e depois adicionar esse número ao final da lista com o #append 
após isso, adiciono o conteúdo da lista na lista pessoas e por fim imprimo o resultado:

Podemos também acessar os índices de cada lista dentro de uma lista, utilizando o mesmo exemplo acima:

`pessoas = [["Pedro", 25], ["Maria", 19], ["João", 32]]
`lista = []
`lista.append(int(input("Insira um número: ")))
`pessoas.append(lista[:])
`print(pessoas[1][0])
```output
Insira um número: 10
Maria
```
Neste exemplo, acesso a lista 1(a lista da maria) e também acesso o primeiro item da lista maria, tendo como output o item acessado

E se você tentar acessar um índice inexistente na lista, irá ocorrer um erro de `IndexError`

Podemos utilizar o #for para acesar cada elemento das listas, por exemplo:

`galera = [["João", 19], ["Ana", 33], ["Joaquim", 13], ["Maria", 45]]
`for p in galera:
   `print(p[0], p[1])

```output
João 19
Ana 33        
Joaquim 13    
Maria 45    
```
No exemplo acima, para cada iteração do loop for com os itens de dentro da lista, ele irá imprimir o índice 0 e logo em seguida o índice 1 de cada lista de dentro da lista, assim sendo impresso os nomes com suas respectivas idades



Também podemos pedir para o usuário inserir os dados para nós trabalharmos
`galera = []
`dado = []
`for c in range(0 , 3):
    `dado.append(str(input("Isira seu nome: ")))
    `dado.append(int(input("Insira sua idade: ")))
    `galera.append(dado[:])
    `dado.clear()
`for p in galera:
    `print(f"{p[0]} tem {p[1]} anos de idade")
```output
Isira seu nome: Matheus
Insira sua idade: 19
Isira seu nome: Raissa
Insira sua idade: 20
Isira seu nome: Lucas
Insira sua idade: 18
Matheus tem 19 anos de idade
Raissa tem 20 anos de idade 
Lucas tem 18 anos de idade 
```
criamos duas listas vazias, após isso utilizamos um loop #for para pedir para o usuário inserir 3 vezes o nome e a idade, após loop de iteração do usuário, copiamos os elementos inseridos pelo usuário na lista galera e removemos da lista dado, fazendo isso até o fim da iteração. Por fim, fazemos um outro loop for para acessar os elementos das listas dentro da galera e imprimimos o índice 0 e 1 de todas as listas. 


Utilizando o mesmo exemplo acima, vamos supor que agora eu só quero mostrar as pessoas que tem mais de 21 anosgalera = []

`dado = []
`for c in range(0 , 3):
    `dado.append(str(input("Isira seu nome: ")))
    `dado.append(int(input("Insira sua idade: ")))
    `galera.append(dado[:])
    `dado.clear()
`for p in galera:
    `if p[1] > 21:
        `print(p[0], p[1])
```output
Isira seu nome: Matheus
Insira sua idade: 22
Isira seu nome: Raissa
Insira sua idade: 20
Isira seu nome: Lucas
Insira sua idade: 24
Matheus 22
Lucas 24  
```

Seguindo o mesmo exemplo acima, porém agora adicionando um contador para vermos quantas pessoas são maiores de idade e quantas são menores.

`totmaior = 0
`totmenor = 0
`galera = []
`dado = []
`for c in range(0 , 3):
    `dado.append(str(input("Isira seu nome: ")))
    `dado.append(int(input("Insira sua idade: ")))
    `galera.append(dado[:])
    `dado.clear()
`for p in galera:
    `if p[1] > 21:
        `print(f"{p[0]} É maior de idade")
        `totmaior +=1
    `else:
        `print(f"{p[0]} É menor de idade")
        `totmenor +=1
`print(f"Temos {totmaior} pessoas maiores de idade")
`print(f"Temos {totmenor} pessoas menores de idade")
```output
Isira seu nome: Matheus
Insira sua idade: 23
Isira seu nome: Raissa
Insira sua idade: 22
Isira seu nome: Lucas
Insira sua idade: 18
Matheus É maior de idade        
Raissa É maior de idade
Lucas É menor de idade
Temos 2 pessoas maiores de idade
Temos 1 pessoas menores de idade
```



# Exercícios:

`pessoas = []
`dados = []
`maior = menor = 0
`continuar = "s"
`while continuar == "s":
``    dados.append(str(input("Nome: ")))
``    dados.append(float(input("Peso: ")))
``    if len(pessoas) == 0:
`        maior = menor = dados[1]
``    else:
``        if dados [1] > maior:
``            maior = dados[1]
``        if dados[1] < menor:
``            menor = dados[1]
``    pessoas.append(dados[:])
``    dados.clear()
 ``    continuar = str(input("Quer continuar? [S/N] ")).strip().lower()
`print("-=-" *20)
`print(f"Foram feitos {len(pessoas)} cadastros ")
`print(f"O maior peso foi de {maior}kg. Peso de: ", end=" ")
`for p in pessoas:
``    if p[1] == maior:
``        print(f"[{p[0]}]", end=" ")
`print()
`print(f"\nO menor peso foi de {menor}Kg. Peso de: ", end="")
`for p in pessoas:
``    if p[1] == menor:
``        print(f"[{p[0]}]", end=" ")




`pessoas = [] 
`dados = [] 
`maior = menor = 0
`continuar = "s"`

1. `pessoas = []`: Inicializa uma lista vazia chamada `pessoas`, que armazenará os dados das pessoas cadastradas.
2. `dados = []`: Inicializa uma lista vazia chamada `dados`, que armazenará temporariamente o nome e o peso de cada pessoa.
3. `maior = menor = 0`: Inicializa as variáveis `maior` e `menor` com o valor 0. Estas variáveis serão usadas para armazenar os maiores e menores pesos registrados.
4. `continuar = "s"`: Inicializa a variável `continuar` com o valor "s" (sim), indicando que o loop começará executando.



`while continuar == "s":`

5. `while continuar == "s":`: Inicia um loop `while` que continuará executando enquanto `continuar` for igual a "s".



    `dados.append(str(input("Nome: ")))`

6. `dados.append(str(input("Nome: ")))`: Solicita ao usuário que insira um nome e o adiciona à lista `dados` como uma string.



    `dados.append(float(input("Peso: ")))`

7. `dados.append(float(input("Peso: ")))`: Solicita ao usuário que insira um peso e o adiciona à lista `dados` como um valor float.


    `if len(pessoas) == 0:         
	    `maior = menor = dados[1]`

8. `if len(pessoas) == 0:`: Verifica se a lista `pessoas` está vazia.
9. `maior = menor = dados[1]`: Se `pessoas` estiver vazia, define o primeiro peso inserido como ambos `maior` e `menor`.


    `else:       
	    `if dados[1] > maior:            
		    `` maior = dados[1]         
	    `if dados[1] < menor:             
	     `menor = dados[1]`

10. `else:`: Caso a lista `pessoas` não esteja vazia, compara o peso inserido com os valores atuais de `maior` e `menor`.
11. `if dados [1] > maior:`: Se o peso inserido for maior que o valor de `maior`, atualiza `maior` com este novo valor.
12. `if dados[1] < menor:`: Se o peso inserido for menor que o valor de `menor`, atualiza `menor` com este novo valor.



    `pessoas.append(dados[:])`

13. `pessoas.append(dados[:])`: Adiciona uma cópia da lista `dados` à lista `pessoas`.



    `dados.clear()`

14. `dados.clear()`: Limpa a lista `dados` para que ela possa ser reutilizada no próximo loop.



    `continuar = str(input("Quer continuar? [S/N] ")).strip().lower()`

15. `continuar = str(input("Quer continuar? [S/N] ")).strip().lower()`: Solicita ao usuário se deseja continuar inserindo dados. Remove espaços em branco e converte a resposta para minúsculas.



`print("-=-" *20)`

16. `print("-=-" *20)`: Imprime uma linha decorativa.



`print(f"Foram feitos {len(pessoas)} cadastros ")`

17. `print(f"Foram feitos {len(pessoas)} cadastros ")`: Imprime o número total de cadastros realizados.


`print(f"O maior peso foi de {maior}kg. Peso de: ", end=" ")`

18. `print(f"O maior peso foi de {maior}kg. Peso de: ", end=" ")`: Imprime o maior peso registrado e inicia a lista de nomes das pessoas com esse peso.


`for p in pessoas:     
	`if p[1] == maior:        
		`print(f"[{p[0]}]", end=" ") 
`print()`

19. `for p in pessoas:`: Inicia um loop para iterar sobre cada pessoa na lista `pessoas`.
20. `if p[1] == maior:`: Verifica se o peso da pessoa é igual ao maior peso registrado.
21. `print(f"[{p[0]}]", end=" ")`: Se for, imprime o nome da pessoa entre colchetes na mesma linha.
22. `print()`: Adiciona uma nova linha após listar todas as pessoas com o maior peso.



`print(f"\nO menor peso foi de {menor}Kg. Peso de: ", end="")`

23. `print(f"\nO menor peso foi de {menor}Kg. Peso de: ", end="")`: Imprime o menor peso registrado e inicia a lista de nomes das pessoas com esse peso.



`for p in pessoas:     
	`if p[1] == menor:         
		`print(f"[{p[0]}]", end=" ")`

24. `for p in pessoas:`: Inicia um loop para iterar sobre cada pessoa na lista `pessoas`.
25. `if p[1] == menor:`: Verifica se o peso da pessoa é igual ao menor peso registrado.
26. `print(f"[{p[0]}]", end=" ")`: Se for, imprime o nome da pessoa entre colchetes na mesma linha.

Este código coleta o nome e o peso de várias pessoas, registra o maior e o menor peso inserido e exibe esses valores junto com os nomes das pessoas correspondentes.



# Exercício 2:

`num = [[], []]
`for c in range(1, 8):
    `valor = int(input(f"Insira o {c} valor: "))
    `if valor % 2 == 0:
        `num[0].append(valor)
    `else:
        `num[1].append(valor)
`print(f"Os números pares foram {num[0]}")
`print(f"Os números ímpares foram: {num[1]}")



`num = [[], []]`

1. `num = [[], []]`: Inicializa a lista `num` com duas sublistas vazias. A primeira sublista (`num[0]`) será usada para armazenar números pares, e a segunda sublista (`num[1]`) será usada para armazenar números ímpares.



`for c in range(1, 8):`

2. `for c in range(1, 8):`: Inicia um loop `for` que irá iterar de 1 a 7, solicitando ao usuário 7 valores.


    `valor = int(input(f"Insira o {c} valor: "))`

3. `valor = int(input(f"Insira o {c} valor: "))`: Solicita ao usuário que insira um valor, converte-o para inteiro e armazena na variável `valor`.



    `if valor % 2 == 0:        
		`num[0].append(valor)     
	`else:         
		`num[1].append(valor)`

4. `if valor % 2 == 0:`: Verifica se o valor é par.
    - `num[0].append(valor)`: Se o valor for par, adiciona-o à sublista de pares (`num[0]`).
5. `else:`: Caso contrário, o valor é ímpar.
    - `num[1].append(valor)`: Adiciona o valor à sublista de ímpares (`num[1]`).



`print(f"Os números pares foram {num[0]}") 
`print(f"Os números ímpares foram: {num[1]}")`

6. `print(f"Os números pares foram {num[0]}")`: Imprime a sublista de números pares.
7. `print(f"Os números ímpares foram: {num[1]}")`: Imprime a sublista de números ímpares.



#  Exercício 3: 

`matriz = [[0, 0, 0], [0, 0, 0], [0, 0, 0]]`

1. `matriz = [[0, 0, 0], [0, 0, 0], [0, 0, 0]]`: Inicializa uma matriz 3x3 com zeros. A matriz é representada como uma lista de listas, onde cada sublista representa uma linha da matriz.


`for l in range(0, 3):     
	`for c in range(0, 3):         
		`matriz[l][c] = int(input(f"Digite um valor para a posição [{l}, {c}]: "))`

2. `for l in range(0, 3):`: Inicia um loop que itera sobre as linhas da matriz, usando `l` como índice das linhas (0, 1, 2).
3. `for c in range(0, 3):`: Aninhado dentro do primeiro loop, este loop itera sobre as colunas da matriz, usando `c` como índice das colunas (0, 1, 2).
4. `matriz[l][c] = int(input(f"Digite um valor para a posição [{l}, {c}]: "))`: Solicita ao usuário um valor inteiro para a posição `[l, c]` da matriz e armazena esse valor na posição correspondente.



`print("-=-" * 20)`

5. `print("-=-" * 20)`: Imprime uma linha decorativa para separar a entrada de dados da saída de dados.



`for l in range(0, 3):
	`for c in range(0, 3):         
		`print(f"[{matriz[l][c]:^5}]", end=" ")     
		`print()`

6. `for l in range(0, 3):`: Inicia um loop que itera sobre as linhas da matriz novamente para a impressão dos valores.
7. `for c in range(0, 3):`: Aninhado dentro do primeiro loop, este loop itera sobre as colunas da matriz para a impressão dos valores.
8. `print(f"[{matriz[l][c]:^5}]", end=" ")`: Imprime o valor na posição `[l, c]` da matriz com formatação centralizada em um espaço de 5 caracteres. O argumento `end=" "` impede que a impressão vá para uma nova linha após cada valor.
9. `print()`: Após imprimir todos os valores de uma linha, `print()` é chamado sem argumentos para mover a impressão para a linha seguinte.




# Exercício 4:

`matriz = [[0, 0, 0], [0, 0, 0], [0, 0, 0]]
`spar = mai = scol = 0
`for l in range(0, 3):
    `for c in range(0, 3):
        `matriz[l][c] = int(input(f"Digite um valor para a posição [{l}, {c}]: "))
`print("-=-"* 20)
`for l in range(0, 3):
    `for c in range(0, 3):
        `print(f"[{matriz[l][c]:^5}]", end=" ")
        `if matriz[l][c] % 2 == 0:
            `spar+=matriz[l][c]
    `print()
`print("-=-" *20)
`print(f"A soma dos valores pares é: {spar}")
`for l in range(0, 3):
    `scol += matriz [l][2]
`print(f"A soma dos valores da terceira coluna é {scol}")
`for c in range(0, 3):
    `if c == 0:
        `mai = matriz[1][c]
    `elif matriz [1][c] > mai:
        `mai = matriz[1][c]
`print(f"O maior valor da segunda linhar é {mai}")

1. **Inicialização:**
    
    `matriz = [[0, 0, 0], [0, 0, 0], [0, 0, 0]] 
    `spar = mai = scol = 0`
    
    - `matriz` é inicializada como uma matriz 3x3 preenchida com zeros.
    - `spar` será usada para somar os valores pares.
    - `mai` armazenará o maior valor da segunda linha.
    - `scol` será usada para somar os valores da terceira coluna.
2. **Entrada de dados:**
    
    
    `for l in range(0, 3):     
	   `` for c in range(0, 3):         
		    `matriz[l][c] = int(input(f"Digite um valor para a posição [{l}, {c}]: "))`
    
    - Dois loops aninhados percorrem todas as posições da matriz.
    - O usuário insere um valor para cada posição `[l][c]`.
3. **Impressão da matriz e soma dos valores pares:**

    
    `print("-=-" * 20) 
    `for l in range(0, 3):     
	    `for c in range(0, 3):         
		    `print(f"[{matriz[l][c]:^5}]", end=" ")        
			`if matriz[l][c] % 2 == 0:            
				`` spar += matriz[l][c]     
			`print() 
				`print("-=-" * 20)`
    
    - A matriz é impressa de forma formatada.
    - Durante a impressão, os valores pares são somados em `spar`.
4. **Impressão da soma dos valores pares:**
    

    
    `print(f"A soma dos valores pares é: {spar}")`
    
5. **Soma dos valores da terceira coluna:**
    

    
    `for l in range(0, 3):     
	    `scol += matriz[l][2] 
    `print(f"A soma dos valores da terceira coluna é {scol}")`
    
6. **Encontrar o maior valor da segunda linha:**
    

    
    `for c in range(0, 3):
         `if c == 0:         
	        `` mai = matriz[1][c]     
	        `elif matriz[1][c] > mai:         
		       `` mai = matriz[1][c] 
	        `print(f"O maior valor da segunda linha é {mai}")`
    

### Funcionamento:

- O código coleta os valores para preencher a matriz 3x3.
- Ele imprime a matriz e calcula a soma dos valores pares.
- Ele calcula e imprime a soma dos valores da terceira coluna.
- Ele encontra e imprime o maior valor da segunda linha.

# Exercício 5:

`ficha = []
`while True:
    `nome = str(input("Nome do aluno: ")).lower().strip()
    `n1 = float(input("Nota 1: "))
    `n2 = float(input("Nota 2: "))
    `media = (n1 + n2) / 2
    `ficha.append([nome, [n1, n2], media])
    `cont = str(input("Quer continuar? [S/N] ")).lower().strip()
    `if cont == "n":
        `break
`print(f'{"No.":<4}{"NOME":<10}{"MÉDIA":>8}')
`for i, a in enumerate(ficha):
    `print(f"{i:<4}{a[0]:<10}{a[2]:>8}")
`while True:
    `opc = int(input("Mostrar notas de qual aluno? (999 interrompe) "))
    `if opc == 999:
        `print("Finalizando...")
        `break
    `if opc <= len(ficha) -1:
        `print(f"Notas de {ficha[opc][0]} são {ficha[opc][1]}")



`ficha = []`

- Declara uma lista vazia chamada `ficha` que será usada para armazenar as informações dos alunos.

`while True:`

- Inicia um loop infinito. Esse loop só será interrompido quando encontrarmos um `break`.


    `nome = str(input("Nome do aluno: ")).lower().strip()`

- Solicita ao usuário o nome do aluno, converte o input para uma string, transforma todos os caracteres em minúsculas (`.lower()`) e remove espaços em branco no início e no fim (`.strip()`).



    `n1 = float(input("Nota 1: "))    
	`n2 = float(input("Nota 2: "))`

- Solicita ao usuário duas notas do aluno e converte esses inputs para float.


    `media = (n1 + n2) / 2`

- Calcula a média das duas notas.


    `ficha.append([nome, [n1, n2], media])`

- Adiciona uma lista contendo o nome do aluno, uma sub-lista com as duas notas e a média à lista `ficha`.


    `cont = str(input("Quer continuar? [S/N] ")).lower().strip()`

- Pergunta ao usuário se ele quer continuar adicionando alunos. Converte a resposta para minúsculas e remove espaços em branco no início e no fim.



    `if cont == "n":         
	    `break`

- Se a resposta for 'n', o loop é interrompido com o comando `break`.


`print(f'{"No.":<4}{"NOME":<10}{"MÉDIA":>8}')`

- Imprime o cabeçalho da tabela. Usa formatação para alinhar as colunas:
    - `{"No.":<4}`: "No." com alinhamento à esquerda e largura de 4 caracteres.
    - `{"NOME":<10}`: "NOME" com alinhamento à esquerda e largura de 10 caracteres.
    - `{"MÉDIA":>8}`: "MÉDIA" com alinhamento à direita e largura de 8 caracteres.



`for i, a in enumerate(ficha):     
	`print(f"{i:<4}{a[0]:<10}{a[2]:>8}")`

- Itera sobre a lista `ficha` usando `enumerate` para obter o índice (`i`) e os dados do aluno (`a`). Imprime os dados de cada aluno formatados:
    - `i:<4`: índice com alinhamento à esquerda e largura de 4 caracteres.
    - `a[0]:<10`: nome do aluno com alinhamento à esquerda e largura de 10 caracteres.
    - `a[2]:>8`: média do aluno com alinhamento à direita e largura de 8 caracteres.



`while True:`

- Inicia outro loop infinito.


    `opc = int(input("Mostrar notas de qual aluno? (999 interrompe) "))`

- Solicita ao usuário um índice de aluno para mostrar suas notas. Converte a resposta para um inteiro.



    `if opc == 999:         
	    `print("Finalizando...")         
	    `break`

- Se a entrada for 999, imprime "Finalizando..." e interrompe o loop com `break`.



    `if opc <= len(ficha) - 1:
        `print(f"Notas de {ficha[opc][0]} são {ficha[opc][1]}")`

# Detalhamento do trecho: 

`print(f'{"No.":<4}{"NOME":<10}{"MÉDIA":>8}')
`for i, a in enumerate(ficha):
    `print(f"{i:<4}{a[0]:<10}{a[2]:>8}")


#### 1. Cabeçalho da Tabela:


`print(f'{"No.":<4}{"NOME":<10}{"MÉDIA":>8}')`

- **`f'{"No.":<4}{"NOME":<10}{"MÉDIA":>8}'`**: Esta é uma f-string, que permite a inclusão de variáveis e expressões Python dentro de strings usando chaves `{}`.
    
- **`{"No.":<4}`**: `No.` é o rótulo para a coluna de números. `:<4` significa que este texto deve ser alinhado à esquerda (`<`) com uma largura mínima de 4 caracteres.
    
- **`{"NOME":<10}`**: `NOME` é o rótulo para a coluna de nomes. `:<10` significa que este texto deve ser alinhado à esquerda (`<`) com uma largura mínima de 10 caracteres.
    
- **`{"MÉDIA":>8}`**: `MÉDIA` é o rótulo para a coluna de médias. `:>8` significa que este texto deve ser alinhado à direita (`>`) com uma largura mínima de 8 caracteres.
    
- O resultado desta linha será algo como:
    
    Copiar código
    
    `No. NOME      MÉDIA`
    

#### 2. Iteração Sobre a Lista `ficha`:



`for i, a in enumerate(ficha):
	`print(f"{i:<4}{a[0]:<10}{a[2]:>8}")`

- **`for i, a in enumerate(ficha):`**: Este `for` loop itera sobre a lista `ficha`. A função `enumerate` é usada para obter tanto o índice (`i`) quanto o valor (`a`) de cada elemento da lista.
    
    - `i`: O índice do elemento na lista.
    - `a`: O elemento em si, que neste caso é uma lista `[nome, [n1, n2], media]`.
- **`print(f"{i:<4}{a[0]:<10}{a[2]:>8}")`**:
    
    - **`{i:<4}`**: O índice `i` é formatado para ser alinhado à esquerda (`<`) com uma largura mínima de 4 caracteres.
    - **`{a[0]:<10}`**: O nome do aluno `a[0]` é formatado para ser alinhado à esquerda (`<`) com uma largura mínima de 10 caracteres.
    - **`{a[2]:>8}`**: A média `a[2]` é formatada para ser alinhada à direita (`>`) com uma largura mínima de 8 caracteres.
- O resultado será algo como:
    
    Copiar código
    
    `0   joao      7.50 
    `1   maria     8.25`
    

### Exemplos:

Suponhamos que `ficha` contenha os seguintes dados:


`ficha = [     
			`["joao", [7.0, 8.0], 7.5],     
			`["maria", [8.0, 8.5], 8.25] ]`

#### Saída do Cabeçalho:


`print(f'{"No.":<4}{"NOME":<10}{"MÉDIA":>8}')`

- Resultado:
    
    
    `No. NOME      MÉDIA`
    

#### Saída do `for` Loop:


`for i, a in enumerate(ficha):
	`print(f"{i:<4}{a[0]:<10}{a[2]:>8}")`

- Iteração 1 (`i=0`, `a=["joao", [7.0, 8.0], 7.5]`):
    
    - **`i:<4`**: `0` (alinhado à esquerda com 4 caracteres)
    - **`a[0]:<10`**: `joao` (alinhado à esquerda com 10 caracteres)
    - **`a[2]:>8`**: `7.5` (alinhado à direita com 8 caracteres)
- Iteração 2 (`i=1`, `a=["maria", [8.0, 8.5], 8.25]`):
    
    - **`i:<4`**: `1` (alinhado à esquerda com 4 caracteres)
    - **`a[0]:<10`**: `maria` (alinhado à esquerda com 10 caracteres)
    - **`a[2]:>8`**: `8.25` (alinhado à direita com 8 caracteres)
- Resultado Final:
    
    `No. NOME      MÉDIA 
    `0   joao         7.5 
    `1   maria       8.25`

