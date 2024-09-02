
#MapaMentalListas #ListasAninhadas

### Mapa Mental: Listas em Python

---

#### 1. **Conceito de Listas**

- Estrutura de dados que armazena uma coleção de itens.
- Itens podem ser de tipos diferentes (inteiros, strings, etc.).
- Listas são mutáveis (podem ser modificadas após a criação).

---

#### 2. **Criação de Listas**

- **Sintaxe Básica**: `minha_lista = [1, 2, 3, 4]`
- **Listas Vazias**: `lista_vazia = []`
- **Listas com Diferentes Tipos**: `lista_mista = [1, 'texto', 3.14]`

---

#### 3. **Acesso aos Elementos**

- **Índices**: `minha_lista[0]` (acessa o primeiro elemento)
- **Índices Negativos**: `minha_lista[-1]` (acessa o último elemento)
- **Fatiamento**: `minha_lista[1:3]` (acessa elementos do índice 1 ao 2)

---

#### 4. **Modificação de Listas**

- **Alterar Elementos**: `minha_lista[1] = 'novo_valor'`
- **Adicionar Elementos**:
    - `append()`: `minha_lista.append('novo_item')`
    - `extend()`: `minha_lista.extend([5, 6])`
    - `insert()`: `minha_lista.insert(1, 'item')`
- **Remover Elementos**:
    - `remove()`: `minha_lista.remove('item')`
    - `pop()`: `minha_lista.pop()` (remove o último item ou item específico com `pop(índice)`)
    - `del`: `del minha_lista[2]` (remove o item no índice 2)

---

#### 5. **Métodos e Funções Comuns**

- **`len()`**: `len(minha_lista)` (retorna o número de itens)
- **`sorted()`**: `sorted(minha_lista)` (retorna uma nova lista ordenada)
- **`reverse()`**: `minha_lista.reverse()` (inverte a ordem dos itens na lista)
- **`index()`**: `minha_lista.index('item')` (retorna o índice do primeiro item encontrado)
- **`count()`**: `minha_lista.count('item')` (conta o número de ocorrências do item)

---

#### 6. **Compreensões de Lista**

- **Sintaxe Básica**: `[expressão for item in iterável]`
- **Exemplo**: `quadrados = [x**2 for x in range(10)]` (cria uma lista de quadrados dos números de 0 a 9)
- **Com Condição**: `[x for x in range(10) if x % 2 == 0]` (cria uma lista com números pares)

---

#### 7. **Listas Aninhadas**

- **Criação**: `lista_aninhada = [[1, 2], [3, 4], [5, 6]]`
- **Acesso**: `lista_aninhada[0][1]` (acessa o segundo elemento da primeira lista)

---

#### 8. **Iterando sobre Listas**

- **`for` Loop**:
    
    `for item in minha_lista:     
	    `print(item)`
    
- **`enumerate()`**:
        
    `for índice, item in enumerate(minha_lista):     
	    `print(índice, item)`
    

---

#### 9. **Listas e Funções**

- **Funções Incorporadas**: `sum()`, `max()`, `min()`
- **Funções Personalizadas**:
    
    
    `def processar_lista(lista):    
    `` return [x*2 for x in lista]`
    

---

#### 10. **Considerações de Desempenho**

- **Complexidade**:
    - Acesso: O(1)
    - Inserção/Remoção no final: O(1) médio
    - Inserção/Remoção no início/meio: O(n)



1. Cria uma lista com diferentes tipos de elementos.
2. Modifica a lista, adiciona e remove elementos.
3. Usa métodos e funções para manipular a lista.
4. Utiliza compreensões de lista.
5. Trabalha com listas aninhadas.
6. Itera sobre a lista e utiliza funções incorporadas.


`# 1. Criação de Listas 
`minha_lista = [1, 'texto', 3.14, [5, 6]]  
`print("Lista Original:", minha_lista)  

`# 2. Modificação de Listas 
`# Adicionar elementos 
`minha_lista.append(42)               # Adiciona um número 
`minha_lista.insert(1, 'novo_item')  # Insere um item na posição 1 
`print("Lista após adição:", minha_lista)  

`# Remover elementos 
`minha_lista.remove('texto')         # Remove o item 'texto' 
`item_removido = minha_lista.pop()   # Remove o último item e o armazena 
`del minha_lista[2]                  # Remove o item no índice 2 
`print("Lista após remoção:", minha_lista) 
`print("Item removido com pop():", item_removido)  

`# 3. Métodos e Funções Comuns 
`print("Comprimento da lista:", len(minha_lista)) 
`print("Lista ordenada:", sorted([4, 1, 3, 2])) 
`minha_lista.reverse()              # Inverte a ordem dos itens 
`print("Lista invertida:", minha_lista) 
`print("Índice de 42:", minha_lista.index(42) if 42 in minha_lista else 'Não encontrado') 
`print("Contagem de 42:", minha_lista.count(42))  

`# 4. Compreensões de `Lista 
`quadrados = [x**2 for x in range(10)] # Cria uma lista de quadrados 
`pares = [x for x in range(10) if x % 2 == 0]  # Cria uma lista de números pares print("Quadrados:", quadrados) 
`print("Pares:", pares)  

`# 5. Listas Aninhadas lista_aninhada = [[1, 2], [3, 4], [5, 6]] 
`print("Lista Aninhada:", lista_aninhada) 
`print("Elemento específico:", lista_aninhada[1][0])  # Acessa o primeiro elemento da segunda lista  

`# 6. Iterando sobre Listas 
`print("Iterando sobre minha_lista:") 
`for item in minha_lista:     
	`print(item)  

`print("Iterando com enumerate:") 
`for índice, item in enumerate(minha_lista):     
	`print(f"Índice {índice}: {item}")  

`# 7. Funções Personalizadas 
`def processar_lista(lista):     
	`return [x*2 if isinstance(x, int) else x for x in lista]  
	
`print("Lista processada:", processar_lista(minha_lista))  


`# 8. Considerações de Desempenho # Acesso, inserção e remoção foram abordados acima. Acesso é O(1), inserção/removal é O(n) para operações em meio da lista.`

### Explicação do Exemplo:

1. **Criação de Listas**: Criamos uma lista com diferentes tipos de elementos.
2. **Modificação de Listas**: Adicionamos e removemos elementos da lista.
3. **Métodos e Funções Comuns**: Usamos funções como `len()`, `sorted()`, `reverse()`, `index()`, e `count()`.
4. **Compreensões de Lista**: Criamos listas de quadrados e números pares usando compreensões.
5. **Listas Aninhadas**: Trabalhamos com listas dentro de listas e acessamos um elemento específico.
6. **Iterando sobre Listas**: Iteramos usando loops `for` e `enumerate()`.
7. **Funções Personalizadas**: Criamos uma função que duplica valores inteiros na lista.



# #ListasAninhadas

#### 1. **Conceito de Listas Aninhadas**

- Listas dentro de outras listas.
- Permitem criar estruturas de dados mais complexas, como matrizes e tabelas.

---

#### 2. **Criação de Listas Aninhadas**

- **Sintaxe Básica**: `lista_aninhada = [[1, 2], [3, 4], [5, 6]]`
- **Exemplo**:
    

    
    `matriz = [     
    `[1, 2, 3],     
    `[4, 5, 6],     
    `[7, 8, 9] ]`
    

---

#### 3. **Acesso a Elementos**

- **Acesso Simples**: `lista_aninhada[i][j]`
    - `lista_aninhada[0][1]` acessa o segundo item da primeira sub-lista.
- **Exemplo**:
    
    
`print(matriz[1][2])  # Acessa o elemento na segunda linha e terceira coluna (6)`
    

---

#### 4. **Modificação de Elementos**

- **Alterar Elementos**: `lista_aninhada[i][j] = novo_valor`
- **Exemplo**:
    

    
    `matriz[0][0] = 10  # Altera o primeiro elemento da primeira linha para 10 print(matriz)  # [[10, 2, 3], [4, 5, 6], [7, 8, 9]]`
    

---

#### 5. **Iterando sobre Listas Aninhadas**

- **Iteração com `for` Loop**:

    
    `for sub_lista in lista_aninhada:     
	    `for item in sub_lista:         
		    `print(item)`
    
- **Exemplo**:
    
    
    `for linha in matriz:     
	    `for valor in linha:         
		   `` print(valor, end=' ')     
		`print()`
    

---

#### 6. **Listas Aninhadas e Compreensões de Lista**

- **Sintaxe Básica**: `[item for sub_lista in lista_aninhada for item in sub_lista]`
- **Exemplo**:
    
    
    `lista_planada = [item for sub_lista in matriz for item in sub_lista] print(lista_planada)  # [10, 2, 3, 4, 5, 6, 7, 8, 9]`
    

---

#### 7. **Operações com Listas Aninhadas**

- **Adição de Sub-listas**:
    
    
    `matriz.append([10, 11, 12]) print(matriz)`
    
- **Remoção de Sub-listas**:
    
    `matriz.pop(0)  # Remove a primeira sub-lista print(matriz)`
    

---

#### 8. **Exemplos Avançados**

- **Matriz de Transposição**:

    
    `matriz = [     
    `[1, 2, 3],     
    `[4, 5, 6],    
    `[7, 8, 9] ]
	`transposta = [[linha[i] for linha in matriz] for i in range(3)
    `print(transposta)  # [[1, 4, 7], [2, 5, 8], [3, 6, 9]]`
    
- **Transformação de Listas Aninhadas**:
    
    
    `def dobrar_elementos(matriz):    
	    `` return [[item * 2 for item in linha] for linha in matriz]  
    `matriz_dobrada = dobrar_elementos(matriz) 
    `print(matriz_dobrada)  # [[2, 4, 6], [8, 10, 12], [14, 16, 18]]`
    

---

### Exemplos de Código

**Criação e Acesso**:



`lista_aninhada = [[1, 2], [3, 4], [5, 6]] 
`print(lista_aninhada[1][0])  # Saída: 3`

**Modificação**:


`lista_aninhada[2][1] = 7 
`print(lista_aninhada)  # [[1, 2], [3, 4], [5, 7]]`

**Iteração**:



`for sub_lista in lista_aninhada:     
	`for item in sub_lista:         
		`print(item, end=' ')     
	`print()`

**Compreensão**:


`flattened = [item for sub_lista in lista_aninhada for item in sub_lista] print(flattened)  # [1, 2, 3, 4, 5, 7]`



# Exemplo Completo:

`lista = []
`mai = 0
`men = 0
`for c in range(0, 5):
    `lista.append(int(input(f"Insira um número para a posição {c}: ")))
    `if c == 0:
        `mai = men = lista[c]
    `else:
        `if lista[c] > mai:
            `mai = lista[c]
        `if lista[c] < men:
            `men = lista[c]
`print(f"Você digitou os valores {lista} ")
`print(f"O maior valor digitado foi: {mai} nas posições: ", end="")
`for i, v in enumerate(lista):
    `if v == mai:
        `print(f"{i}...", end="")
`print(f"\nO menor valor digitado foi: {men} nas posições: ", end="")
`for i, v in enumerate(lista):
    `if v == men:
        `print(f"{i}...", end="")

```ExemploDeOutput
Insira um número para a posição 0: 10
Insira um número para a posição 1: 80
Insira um número para a posição 2: 20
Insira um número para a posição 3: 60
Insira um número para a posição 4: 12
Você digitou os valores [10, 80, 20, 60, 12]     
O maior valor digitado foi: 80 nas posições: 1...
O menor valor digitado foi: 10 nas posições: 0...
```


`# Cria uma lista vazia para armazenar os números lista = []`

1. **Inicialização da Lista:**
    - `lista = []`: Inicializa uma lista vazia onde os números inseridos pelo usuário serão armazenados.



`# Inicializa as variáveis para armazenar o maior e o menor valor mai = 0 men = 0`

2. **Inicialização das Variáveis `mai` e `men`:**
    - `mai = 0`: Inicializa a variável `mai` para armazenar o maior valor encontrado.
    - `men = 0`: Inicializa a variável `men` para armazenar o menor valor encontrado.
    - Ambos são inicializados com 0, mas os valores reais serão atualizados conforme os números são inseridos.


`# Loop para inserir 5 números na lista 
`for c in range(0, 5):     
	`lista.append(int(input(f"Insira um número para a posição {c}: ")))`

3. **Loop de Inserção de Dados:**
    - `for c in range(0, 5):`: Inicia um loop que itera 5 vezes (de 0 a 4).
    - `lista.append(int(input(f"Insira um número para a posição {c}: ")))`: Solicita ao usuário para inserir um número e o adiciona à lista `lista`. O número é convertido para um inteiro com `int()`.


    `# Atualiza os valores de maior e menor conforme os números são inseridos     if c == 0:         
	    `mai = men = lista[c]`

4. **Inicialização de `mai` e `men` na Primeira Iteração:**
    - `if c == 0:`: Verifica se é a primeira iteração do loop.
    - `mai = men = lista[c]`: Na primeira iteração, `mai` e `men` são definidos como o valor do primeiro número inserido. Isso garante que ambos comecem com um valor válido.



    `else:         
	    `# Atualiza o maior valor se necessário         
	    `if lista[c] > mai:
	        `` mai = lista[c]`

5. **Atualização do Maior Valor:**
    - `else:`: Para todas as iterações subsequentes (exceto a primeira).
    - `if lista[c] > mai:`: Verifica se o número atual é maior que o maior valor encontrado até agora.
    - `mai = lista[c]`: Se a condição for verdadeira, atualiza `mai` com o novo maior valor.



        `# Atualiza o menor valor se necessário         
        `if lista[c] < men:
	     `` men = lista[c]`

6. **Atualização do Menor Valor:**
    - `if lista[c] < men:`: Verifica se o número atual é menor que o menor valor encontrado até agora.
    - `men = lista[c]`: Se a condição for verdadeira, atualiza `men` com o novo menor valor.



`# Exibe a lista de valores inseridos 
`print(f"Você digitou os valores {lista} ")`

7. **Impressão da Lista de Valores:**
    - `print(f"Você digitou os valores {lista} ")`: Imprime a lista completa de valores inseridos.



`# Exibe o maior valor e suas posições 
`print(f"O maior valor digitado foi: {mai} nas posições: ", end="")`

8. **Início da Impressão do Maior Valor:**
    - `print(f"O maior valor digitado foi: {mai} nas posições: ", end="")`: Imprime o maior valor encontrado e começa a imprimir as posições onde esse valor aparece. O parâmetro `end=""` evita a quebra de linha após a impressão.



`for i, v in enumerate(lista):     
	`if v == mai:         
	`print(f"{i}...", end="")`

9. **Loop para Encontrar e Imprimir Posições do Maior Valor:**
    - `for i, v in enumerate(lista):`: Itera sobre a lista `lista` com índices (`i`) e valores (`v`).
    - `if v == mai:`: Verifica se o valor atual é igual ao maior valor encontrado.
    - `print(f"{i}...", end="")`: Se a condição for verdadeira, imprime o índice onde o maior valor aparece. O parâmetro `end=""` evita a quebra de linha após cada índice.



`# Exibe o menor valor e suas posições 
`print(f"\nO menor valor digitado foi: {men} nas posições: ", end="")`

10. **Início da Impressão do Menor Valor:**
    - `print(f"\nO menor valor digitado foi: {men} nas posições: ", end="")`: Imprime o menor valor encontrado e começa a imprimir as posições onde esse valor aparece. O parâmetro `end=""` evita a quebra de linha após a impressão. A quebra de linha `\n` é usada para separar a impressão do maior valor da impressão do menor valor.



`for i, v in enumerate(lista):     
	`if v == men:         
		`print(f"{i}...", end="")`

11. **Loop para Encontrar e Imprimir Posições do Menor Valor:**
    - `for i, v in enumerate(lista):`: Itera sobre a lista `lista` com índices (`i`) e valores (`v`).
    - `if v == men:`: Verifica se o valor atual é igual ao menor valor encontrado.
    - `print(f"{i}...", end="")`: Se a condição for verdadeira, imprime o índice onde o menor valor aparece. O parâmetro `end=""` evita a quebra de linha após cada índice.

### Resumo

- **Inicialização e Entrada de Dados:** O código inicializa uma lista e preenche com números inseridos pelo usuário, enquanto atualiza o maior e o menor valor encontrados.
- **Impressão dos Resultados:** Após a entrada dos dados, o código imprime o maior e o menor valor encontrados, bem como suas posições na lista.

O código é bem estruturado e realiza as operações desejadas de forma eficiente. O uso de `enumerate()` facilita a iteração com índices e valores, e o formato das saídas é claro e informativo.



# #EncontrandoMaiorEMenor

`if c == 0: 
	`mai = men = lista[c] 
`else: 
	`if lista[c] > mai: 
		`mai = lista[c] 
	`if lista[c] < men: 
		`men = lista[c]

### Explicação Detalhada

#### Contexto

O bloco de código é executado dentro de um loop `for` que itera sobre uma lista de 5 números inseridos pelo usuário. O objetivo é identificar e atualizar o maior e o menor valor encontrados na lista à medida que os números são inseridos.

#### Bloco `if c == 0:`


`if c == 0:     
	`mai = men = lista[c]`

1. **Condição `if c == 0`:**
    
    - `if c == 0:`: Verifica se a iteração atual do loop é a primeira (c = 0). Isso ocorre apenas uma vez, na primeira iteração do loop.
2. **Inicialização de `mai` e `men`:**
    
    - `mai = men = lista[c]`:
        - Na primeira iteração (c = 0), `mai` e `men` são inicializados com o valor do primeiro número inserido (ou seja, `lista[c]`).
        - Isso é necessário porque, antes da primeira iteração, `mai` e `men` ainda não têm valores definidos. Definir ambos como o primeiro valor garante que comparações subsequentes possam ser feitas corretamente.

#### Bloco `else:`


`else:     
``	if lista[c] > mai:         
		`mai = lista[c]     
	`if lista[c] < men:         
		`men = lista[c]`

3. **Condição `else`:**
    
    - `else:`: Este bloco é executado em todas as iterações do loop a partir da segunda (c = 1 até c = 4).
4. **Atualização do Maior Valor:**
    
    - `if lista[c] > mai:`: Verifica se o valor atual (`lista[c]`) é maior do que o maior valor encontrado até agora (`mai`).
    - `mai = lista[c]`: Se a condição for verdadeira, o maior valor encontrado (`mai`) é atualizado para o valor atual (`lista[c]`).
5. **Atualização do Menor Valor:**
    
    - `if lista[c] < men:`: Verifica se o valor atual (`lista[c]`) é menor do que o menor valor encontrado até agora (`men`).
    - `men = lista[c]`: Se a condição for verdadeira, o menor valor encontrado (`men`) é atualizado para o valor atual (`lista[c]`).

### Resumo

- **Primeira Iteração (`c == 0`):**
    
    - `mai` e `men` são inicializados com o valor do primeiro número inserido na lista. Isso define a base para as comparações futuras.
- **Iterações Subsequentes (`c > 0`):**
    
    - **Maior Valor:** Compara o valor atual com `mai` e atualiza `mai` se o valor atual for maior.
    - **Menor Valor:** Compara o valor atual com `men` e atualiza `men` se o valor atual for menor.

------------------------------------------------------------------------
------------------------------------------------------------------------


`turma = input("Insira o nome e número da turma: ").strip()
`alunos = []
`while True:
    `print("-"*35)
    `nome = str(input("Insira o nome do aluno: ")).lower().strip()
    `n1 = float(input("Insira a primeira nota: "))
    `n2 = float(input("Insira a segunda nota: "))
    `n3 = float(input("Insira a última nota: "))
    `print("-"*35)
    `media = (n1 + n2 + n3) / 3
    `if media >= 6:
        `situacao = "Aprovado!"
    `elif media >= 3 and media < 6:
        `situacao = "Recuperação!"
    `else:
        `situacao = "Reprovado!"
    `alunos.append([nome, [n1, n2, n3], [media], situacao])
    `continuar = str(input("Quer inserir mais alunos? [S/N] "))
    `if "n" in continuar:
        `break
`print(f'{"No.":<5}{"NOME":<10}{"MÉDIA":>6}{"SITUAÇÂO":>14}')
`print("-"*6, f"Boletim da turma: {turma}", "-"*6)
`for i, a in enumerate(alunos):
    `print(f"{i:<5}{a[0]:<10}{a[2][0]:>6}{a[3]:>14}")
`print("-"*35)
```ExemploDeOutput
Insira o nome e número da turma: 2A
-----------------------------------
Insira o nome do aluno: matheus
Insira a primeira nota: 9
Insira a segunda nota: 9
Insira a última nota: 9
-----------------------------------
Quer inserir mais alunos? [S/N] s  
-----------------------------------
Insira o nome do aluno: raissa
Insira a primeira nota: 5
Insira a segunda nota: 5
Insira a última nota: 5
-----------------------------------
Quer inserir mais alunos? [S/N] s  
-----------------------------------
Insira o nome do aluno: lucas
Insira a primeira nota: 2
Insira a segunda nota: 2
Insira a última nota: 2
-----------------------------------
Quer inserir mais alunos? [S/N] n  
------ Boletim da turma 2A ------  
No.  NOME       MÉDIA      SITUAÇÂO
0    matheus      9.0     Aprovado!
1    raissa       5.0  Recuperação!
2    lucas        2.0    Reprovado!
-----------------------------------
```

------------------------------------------------------------------------
------------------------------------------------------------------------

`# Solicita o nome e número da turma ao usuário e remove espaços desnecessários 
`turma = input("Insira o nome e número da turma: ").strip()`

1. **Entrada de Dados da Turma:**
    - `input("Insira o nome e número da turma: ")`: Solicita que o usuário insira o nome e número da turma.
    - `.strip()`: Remove quaisquer espaços em branco no início e no final da string.


`# Cria uma lista vazia para armazenar os dados dos alunos 
`alunos = []`

2. **Inicialização da Lista de Alunos:**
    - `alunos = []`: Inicializa uma lista vazia que será usada para armazenar os dados dos alunos.


`# Inicia um loop infinito para inserção de dados, que será interrompido pelo comando 'break' 
`while True:     
	`print("-" * 35)`

3. **Início do Loop Infinito:**
    - `while True:`: Inicia um loop infinito que continuará até encontrar o comando `break`.
    - `print("-" * 35)`: Imprime uma linha de separação composta por 35 hífens.



    `# Solicita o nome e as notas do aluno     
    `nome = str(input("Insira o nome do aluno: ")).lower().strip()     
    `n1 = float(input("Insira a primeira nota: "))     
    `n2 = float(input("Insira a segunda nota: "))     
    `n3 = float(input("Insira a última nota: "))     
    `print("-" * 35)`

4. **Entrada de Dados dos Alunos:**
    - `nome = str(input("Insira o nome do aluno: ")).lower().strip()`: Solicita o nome do aluno, converte para minúsculas e remove espaços em branco no início e no final.
    - `n1 = float(input("Insira a primeira nota: "))`: Solicita a primeira nota do aluno e converte para um número de ponto flutuante.
    - `n2 = float(input("Insira a segunda nota: "))`: Solicita a segunda nota do aluno e converte para um número de ponto flutuante.
    - `n3 = float(input("Insira a última nota: "))`: Solicita a terceira nota do aluno e converte para um número de ponto flutuante.
    - `print("-" * 35)`: Imprime outra linha de separação.


    `# Calcula a média das três notas     
    `media = (n1 + n2 + n3) / 3`

5. **Cálculo da Média:**
    - `media = (n1 + n2 + n3) / 3`: Calcula a média das três notas inseridas.


    `# Verifica a situação do aluno com base na média calculada     
    `if media >= 6:        
     `situacao = "Aprovado!"     
	 `elif media >= 3 and media < 6:         
     `situacao = "Recuperação!"     
    `else:         
     `situacao = "Reprovado!"`

6. **Determinação da Situação do Aluno:**
    - `if media >= 6:`: Se a média for maior ou igual a 6, define a situação como "Aprovado!".
    - `elif media >= 3 and media < 6:`: Se a média for entre 3 (inclusive) e 6 (exclusive), define a situação como "Recuperação!".
    - `else:`: Se a média for menor que 3, define a situação como "Reprovado!".


    `# Adiciona os dados do aluno à lista 'alunos'     
    `alunos.append([nome, [n1, n2, n3], [media], situacao])`

7. **Armazenamento dos Dados do Aluno:**
    - `alunos.append([nome, [n1, n2, n3], [media], situacao])`: Adiciona os dados do aluno (nome, notas, média e situação) como uma lista dentro da lista `alunos`.



    `# Verifica se o usuário deseja continuar inserindo mais alunos     
    `continuar = str(input("Quer inserir mais alunos? [S/N] ")).strip().lower()   
    `if "n" in continuar:         
	    `break`

8. **Verificação de Continuação:**
    - `continuar = str(input("Quer inserir mais alunos? [S/N] ")).strip().lower()`: Solicita ao usuário se deseja continuar inserindo mais alunos, remove espaços em branco e converte a resposta para minúsculas.
    - `if "n" in continuar:`: Se a resposta contiver "n", o loop é interrompido com `break`.


`# Imprime o cabeçalho da tabela com alinhamento especificado 
`print(f'{"No.":<5}{"NOME":<10}{"MÉDIA":>6}{"SITUAÇÂO":>14}') 
`print("-" * 6, f"Boletim da turma: {turma}", "-" * 6)`

9. **Impressão do Cabeçalho da Tabela:**
    - `print(f'{"No.":<5}{"NOME":<10}{"MÉDIA":>6}{"SITUAÇÂO":>14}')`: Imprime o cabeçalho da tabela formatado.
    - `print("-" * 6, f"Boletim da turma: {turma}", "-" * 6)`: Imprime uma linha de separação e o título do boletim da turma.



`# Itera sobre a lista 'alunos' com índice e os dados do aluno 
`for i, a in enumerate(alunos):`     
	`print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")`

10. **Impressão dos Dados dos Alunos:**
    - `for i, a in enumerate(alunos):`: Itera sobre a lista `alunos` com índice `i` e os dados do aluno `a`.
    - `print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")`: Imprime os dados de cada aluno (índice, nome, média formatada com duas casas decimais, situação) de acordo com o cabeçalho.

`print("-" * 35)`

11. **Impressão da Linha Final de Separação:**
    - `print("-" * 35)`: Imprime uma linha de separação final.


# Explicação detalhada do seguinte bloco do código:
`for i, a in enumerate(alunos): 
	`print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")

1. **teração sobre a Lista de Alunos:**
    
    
    `for i, a in enumerate(alunos):`
    
    - `for i, a in enumerate(alunos):`: Esta linha inicia um loop `for` que itera sobre a lista `alunos`.
    - `enumerate(alunos)`: A função `enumerate()` é usada para obter tanto o índice (`i`) quanto o valor (`a`) de cada item na lista `alunos` durante a iteração. O índice é um número inteiro que representa a posição do item na lista (começa do zero), e o valor é a lista de dados do aluno.
2. **Desestruturação dos Dados do Aluno:**
    
    
    `print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")`
    
    - `print(...)`: Esta linha imprime uma string formatada que inclui os dados do aluno.
3. **Formato da String:**
    
    - **Índice (`i`):**
        - `{i:<5}`: Este é um campo de formatação para o índice do aluno. `<5` indica que o índice deve ser alinhado à esquerda e ocupar um espaço mínimo de 5 caracteres. Se o índice for menor que 5 caracteres, o espaço restante será preenchido com espaços em branco.
    - **Nome do Aluno (`a[0]`):**
        - `{a[0]:<10}`: Este é um campo de formatação para o nome do aluno. `<10` indica que o nome deve ser alinhado à esquerda e ocupar um espaço mínimo de 10 caracteres. Se o nome for menor que 10 caracteres, o espaço restante será preenchido com espaços em branco.
    - **Média (`a[2][0]`):**
        - `{a[2][0]:>6.2f}`: Este é um campo de formatação para a média do aluno. `a[2][0]` refere-se à média armazenada na lista de dados do aluno (`a`).
        - `>6`: Indica que a média deve ser alinhada à direita e ocupar um espaço mínimo de 6 caracteres.
        - `.2f`: Indica que a média deve ser formatada como um número de ponto flutuante com duas casas decimais.
    - **Situação (`a[3]`):**
        - `{a[3]:>14}`: Este é um campo de formatação para a situação do aluno. `a[3]` refere-se à situação (como "Aprovado!", "Recuperação!", ou "Reprovado!").
        - `>14`: Indica que a situação deve ser alinhada à direita e ocupar um espaço mínimo de 14 caracteres.

### Resumo do Bloco

O bloco de código faz o seguinte:

- Itera sobre a lista `alunos`, onde cada item é uma lista contendo o nome, notas, média e situação de um aluno.
- Para cada aluno, imprime uma linha de dados formatados.
    - O índice do aluno (`i`) é exibido alinhado à esquerda com um mínimo de 5 caracteres.
    - O nome do aluno (`a[0]`) é exibido alinhado à esquerda com um mínimo de 10 caracteres.
    - A média do aluno (`a[2][0]`) é exibida alinhada à direita com um mínimo de 6 caracteres, formatada com duas casas decimais.
    - A situação do aluno (`a[3]`) é exibida alinhada à direita com um mínimo de 14 caracteres.



# Projetinho calculo de notas 1.0
#ListasAninhadas #If-Elif-Else #OperadoresAritméticos #OperadoresLógicos #Fatiamento 
#LOOP #While-for 


```python
`turma = input("Insira o nome e número da turma: ").strip()
`alunos = []
`while True:
    `print("-"*35)
    `nome = str(input("Insira o nome do aluno: ")).lower().strip()
    `n1 = float(input("Insira a primeira nota: "))
    `n2 = float(input("Insira a segunda nota: "))
    `n3 = float(input("Insira a última nota: "))
    `print("-"*35)
    `media = (n1 + n2 + n3) / 3
    `if media >= 6:
        `situacao = "Aprovado!"
    `elif media >= 3 and media < 6:
        `situacao = "Recuperação!"
    `else:
        `situacao = "Reprovado!"
    `alunos.append([nome, [n1, n2, n3], [media], situacao])
    `continuar = str(input("Quer inserir mais alunos? [S/N] "))
    `if "n" in continuar:
        `break
`print(f'{"No.":<5}{"NOME":<10}{"MÉDIA":>6}{"SITUAÇÂO":>14}')
`print("-"*6, f"Boletim da turma: {turma}", "-"*6)
`for i, a in enumerate(alunos):
    `print(f"{i:<5}{a[0]:<10}{a[2][0]:>6}{a[3]:>14}")
`print("-"*35)
```

```python
OUTPUT
Insira o nome e número da turma: 2A
-----------------------------------
Insira o nome do aluno: matheus
Insira a primeira nota: 9
Insira a segunda nota: 9
Insira a última nota: 9
-----------------------------------
Quer inserir mais alunos? [S/N] s  
-----------------------------------
Insira o nome do aluno: raissa
Insira a primeira nota: 5
Insira a segunda nota: 5
Insira a última nota: 5
-----------------------------------
Quer inserir mais alunos? [S/N] s  
-----------------------------------
Insira o nome do aluno: lucas
Insira a primeira nota: 2
Insira a segunda nota: 2
Insira a última nota: 2
-----------------------------------
Quer inserir mais alunos? [S/N] n  
------ Boletim da turma 2A ------  
No.  NOME       MÉDIA      SITUAÇÂO
0    matheus      9.0     Aprovado!
1    raissa       5.0  Recuperação!
2    lucas        2.0    Reprovado!
-----------------------------------
```

```python
ANÁLISE

`# Solicita o nome e número da turma ao usuário e remove espaços desnecessários 
`turma = input("Insira o nome e número da turma: ").strip()`

1. **Entrada de Dados da Turma:**
    - `input("Insira o nome e número da turma: ")`: Solicita que o usuário insira o nome e número da turma.
    - `.strip()`: Remove quaisquer espaços em branco no início e no final da string.


`# Cria uma lista vazia para armazenar os dados dos alunos 
`alunos = []`

2. **Inicialização da Lista de Alunos:**
    - `alunos = []`: Inicializa uma lista vazia que será usada para armazenar os dados dos alunos.


`# Inicia um loop infinito para inserção de dados, que será interrompido pelo comando 'break' 
`while True:     
	`print("-" * 35)`

3. **Início do Loop Infinito:**
    - `while True:`: Inicia um loop infinito que continuará até encontrar o comando `break`.
    - `print("-" * 35)`: Imprime uma linha de separação composta por 35 hífens.



    `# Solicita o nome e as notas do aluno     
    `nome = str(input("Insira o nome do aluno: ")).lower().strip()     
    `n1 = float(input("Insira a primeira nota: "))     
    `n2 = float(input("Insira a segunda nota: "))     
    `n3 = float(input("Insira a última nota: "))     
    `print("-" * 35)`

4. **Entrada de Dados dos Alunos:**
    - `nome = str(input("Insira o nome do aluno: ")).lower().strip()`: Solicita o nome do aluno, converte para minúsculas e remove espaços em branco no início e no final.
    - `n1 = float(input("Insira a primeira nota: "))`: Solicita a primeira nota do aluno e converte para um número de ponto flutuante.
    - `n2 = float(input("Insira a segunda nota: "))`: Solicita a segunda nota do aluno e converte para um número de ponto flutuante.
    - `n3 = float(input("Insira a última nota: "))`: Solicita a terceira nota do aluno e converte para um número de ponto flutuante.
    - `print("-" * 35)`: Imprime outra linha de separação.


    `# Calcula a média das três notas     
    `media = (n1 + n2 + n3) / 3`

5. **Cálculo da Média:**
    - `media = (n1 + n2 + n3) / 3`: Calcula a média das três notas inseridas.


    `# Verifica a situação do aluno com base na média calculada     
    `if media >= 6:        
     `situacao = "Aprovado!"     
	 `elif media >= 3 and media < 6:         
     `situacao = "Recuperação!"     
    `else:         
     `situacao = "Reprovado!"`

6. **Determinação da Situação do Aluno:**
    - `if media >= 6:`: Se a média for maior ou igual a 6, define a situação como "Aprovado!".
    - `elif media >= 3 and media < 6:`: Se a média for entre 3 (inclusive) e 6 (exclusive), define a situação como "Recuperação!".
    - `else:`: Se a média for menor que 3, define a situação como "Reprovado!".


    `# Adiciona os dados do aluno à lista 'alunos'     
    `alunos.append([nome, [n1, n2, n3], [media], situacao])`

7. **Armazenamento dos Dados do Aluno:**
    - `alunos.append([nome, [n1, n2, n3], [media], situacao])`: Adiciona os dados do aluno (nome, notas, média e situação) como uma lista dentro da lista `alunos`.



    `# Verifica se o usuário deseja continuar inserindo mais alunos     
    `continuar = str(input("Quer inserir mais alunos? [S/N] ")).strip().lower()   
    `if "n" in continuar:         
	    `break`

8. **Verificação de Continuação:**
    - `continuar = str(input("Quer inserir mais alunos? [S/N] ")).strip().lower()`: Solicita ao usuário se deseja continuar inserindo mais alunos, remove espaços em branco e converte a resposta para minúsculas.
    - `if "n" in continuar:`: Se a resposta contiver "n", o loop é interrompido com `break`.


`# Imprime o cabeçalho da tabela com alinhamento especificado 
`print(f'{"No.":<5}{"NOME":<10}{"MÉDIA":>6}{"SITUAÇÂO":>14}') 
`print("-" * 6, f"Boletim da turma: {turma}", "-" * 6)`

9. **Impressão do Cabeçalho da Tabela:**
    - `print(f'{"No.":<5}{"NOME":<10}{"MÉDIA":>6}{"SITUAÇÂO":>14}')`: Imprime o cabeçalho da tabela formatado.
    - `print("-" * 6, f"Boletim da turma: {turma}", "-" * 6)`: Imprime uma linha de separação e o título do boletim da turma.



`# Itera sobre a lista 'alunos' com índice e os dados do aluno 
`for i, a in enumerate(alunos):`     
	`print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")`

10. **Impressão dos Dados dos Alunos:**
    - `for i, a in enumerate(alunos):`: Itera sobre a lista `alunos` com índice `i` e os dados do aluno `a`.
    - `print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")`: Imprime os dados de cada aluno (índice, nome, média formatada com duas casas decimais, situação) de acordo com o cabeçalho.

`print("-" * 35)`

11. **Impressão da Linha Final de Separação:**
    - `print("-" * 35)`: Imprime uma linha de separação final.


# Explicação detalhada do seguinte bloco do código:
`for i, a in enumerate(alunos): 
	`print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")

1. **teração sobre a Lista de Alunos:**
    
    
    `for i, a in enumerate(alunos):`
    
    - `for i, a in enumerate(alunos):`: Esta linha inicia um loop `for` que itera sobre a lista `alunos`.
    - `enumerate(alunos)`: A função `enumerate()` é usada para obter tanto o índice (`i`) quanto o valor (`a`) de cada item na lista `alunos` durante a iteração. O índice é um número inteiro que representa a posição do item na lista (começa do zero), e o valor é a lista de dados do aluno.
2. **Desestruturação dos Dados do Aluno:**
    
    
    `print(f"{i:<5}{a[0]:<10}{a[2][0]:>6.2f}{a[3]:>14}")`
    
    - `print(...)`: Esta linha imprime uma string formatada que inclui os dados do aluno.
3. **Formato da String:**
    
    - **Índice (`i`):**
        - `{i:<5}`: Este é um campo de formatação para o índice do aluno. `<5` indica que o índice deve ser alinhado à esquerda e ocupar um espaço mínimo de 5 caracteres. Se o índice for menor que 5 caracteres, o espaço restante será preenchido com espaços em branco.
    - **Nome do Aluno (`a[0]`):**
        - `{a[0]:<10}`: Este é um campo de formatação para o nome do aluno. `<10` indica que o nome deve ser alinhado à esquerda e ocupar um espaço mínimo de 10 caracteres. Se o nome for menor que 10 caracteres, o espaço restante será preenchido com espaços em branco.
    - **Média (`a[2][0]`):**
        - `{a[2][0]:>6.2f}`: Este é um campo de formatação para a média do aluno. `a[2][0]` refere-se à média armazenada na lista de dados do aluno (`a`).
        - `>6`: Indica que a média deve ser alinhada à direita e ocupar um espaço mínimo de 6 caracteres.
        - `.2f`: Indica que a média deve ser formatada como um número de ponto flutuante com duas casas decimais.
    - **Situação (`a[3]`):**
        - `{a[3]:>14}`: Este é um campo de formatação para a situação do aluno. `a[3]` refere-se à situação (como "Aprovado!", "Recuperação!", ou "Reprovado!").
        - `>14`: Indica que a situação deve ser alinhada à direita e ocupar um espaço mínimo de 14 caracteres.

### Resumo do Bloco

O bloco de código faz o seguinte:

- Itera sobre a lista `alunos`, onde cada item é uma lista contendo o nome, notas, média e situação de um aluno.
- Para cada aluno, imprime uma linha de dados formatados.
    - O índice do aluno (`i`) é exibido alinhado à esquerda com um mínimo de 5 caracteres.
    - O nome do aluno (`a[0]`) é exibido alinhado à esquerda com um mínimo de 10 caracteres.
    - A média do aluno (`a[2][0]`) é exibida alinhada à direita com um mínimo de 6 caracteres, formatada com duas casas decimais.
    - A situação do aluno (`a[3]`) é exibida alinhada à direita com um mínimo de 14 caracteres.
```
