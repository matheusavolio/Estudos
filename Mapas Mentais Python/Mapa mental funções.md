### Funções em Python

1. **Definição de Função**
    
    - **Definindo uma Função:**
        
        - `def nome_da_funcao(parametros):`
	        - `Bloco de Código`
        - Exemplo:
            
            `def saudacao(nome):     
	            `print(f"Olá, {nome}!")`
            
    - **Chamando uma Função:**
        
        - `nome_da_funcao(argumentos)`
        - Exemplo:
            
            `saudacao("João")`
            
2. **Parâmetros e Argumentos**
    
    - **Parâmetros Padrão:**
        
        - `def nome_da_funcao(parametro=valor):`
        - Exemplo:
            
            `def saudacao(nome="Mundo"):     
	            `print(f"Olá, {nome}!")`
            
    - **Argumentos Nomeados:**
        
        - `nome_da_funcao(parametro=valor)`
        - Exemplo:
            
            `saudacao(nome="Ana")`
            
    - **Argumentos Posicionais e Nomeados:**
        
        - Exemplo:

            
            `def pessoa(nome, idade):
               ``  print(f"Nome: {nome}, Idade: {idade}")  
            `pessoa("Carlos", idade=30)`
            
    - **Parâmetros Arbitrários:**
        
        - `def nome_da_funcao(*args, **kwargs):`
        - Exemplo:
            

            
            `def listar_nomes(*nomes):     
	            `for nome in nomes:         
	            `print(nome)  
	        `listar_nomes("Ana", "Pedro", "Carlos")`
            
3. **Valores de Retorno**
    
    - **Retornando um Valor:**
        
        - `return valor`
        - Exemplo:
            
            `def soma(a, b):     
	           `` return a + b  
	        `resultado = soma(5, 3) 
	        `print(resultado)`
            
    - **Retorno Múltiplo:**
        
        - `return valor1, valor2`
        - Exemplo:
            
            `def dividir(a, b):
                 `return a // b, a % b  
            `quociente, resto = dividir(10, 3) 
            `print(f"Quociente: {quociente}, Resto: {resto}")`
            
4. **Funções Anônimas (Lambda)**
    
    - **Definindo uma Função Lambda:**
        
        - `lambda parametros: expressao`
        - Exemplo:
            
            `quadrado = lambda x: x * x 
            `print(quadrado(4))`
            
    - **Usando Lambda com Funções de Ordem Superior:**
        
        - Exemplo:
            
            
            `lista = [1, 2, 3, 4] 
            `lista_quadrados = list(map(lambda x: x * x, lista)) print(lista_quadrados)`
            
5. **Funções Recursivas**
    
    - **Definindo uma Função Recursiva:**
        - A função chama a si mesma.
        - Exemplo:
            
            
            `def fatorial(n):     
	        `if n == 0:         
			    `return 1    
		    `else:         
			    `return n * fatorial(n - 1)  print(fatorial(5))`
        
6. **Documentação e Docstrings**
    
    - **Adicionando Docstrings:**
        - `"""Descrição da Função"""`
        - Exemplo:

            
            `def saudacao(nome):     
	            `"""Exibe uma mensagem de saudação para o nome fornecido."""     print(f"Olá, {nome}!")  
	        `print(saudacao.__doc__)`
            
7. **Funções e Escopo**
    
    - **Escopo Local e Global:**
        - Variáveis definidas dentro da função têm escopo local.
        - Variáveis definidas fora da função têm escopo global.
        - Exemplo:
            
            
            `x = 10  
            `def funcao():     
	            `x = 5     
	            `print(x)  
            `funcao() 
            `print(x)`
            
8. **Funções de Ordem Superior**
    
    - **Funções que Aceitam Outras Funções como Argumentos:**
        
        - Exemplo:
            
            
            `def aplicar(funcao, valor):     
	            `return funcao(valor)  
	        `def dobrar(x):     
		        `return x * 2  
		    `resultado = aplicar(dobrar, 5)
		    `print(resultado)`
            
    - **Funções que Retornam Outras Funções:**
        
        - Exemplo:
            
            `def criar_multiplicador(fator):
               ``  return lambda x: x * fator  
            `dobrar = criar_multiplicador(2) 
            `print(dobrar(10))`


# Exemplo 1:

```python

`def somar(a, b):     
	"""Função que retorna a soma de dois números."""     
	resultado = a + b     
	return resultado  
x = 10 
y = 5 
soma = somar(x, y) 
print(f"A soma de {x} e {y} é {soma}.")`
```
#### Explicação

- **Definição da Função**: A função `somar(a, b)` é definida com dois parâmetros, `a` e `b`. Dentro da função, a soma desses dois parâmetros é armazenada na variável `resultado`.
- **`return resultado`**: A função usa a instrução `return` para enviar o valor da soma para o ponto onde a função foi chamada.
- **Chamada da Função**: A função é chamada com os valores `x` e `y` como argumentos, e o valor retornado é armazenado na variável `soma`.
- **Impressão do Resultado**: Finalmente, o resultado da soma é exibido usando a função `print`.

Esse é um exemplo básico de como criar uma função que realiza uma operação e retorna o resultado.

# Exemplo 2:

```python

`total = 0  # Variável global  
def somar(a, b):     
	"""Função que retorna a soma de dois números."""     
	global total     
	total = a + b  # Modifica a variável global     
	return total  
x = 10 
y = 15 
soma = somar(x, y) 
print(f"A soma de {x} e {y} é {soma}.") 
print(f"O valor total global agora é {total}.")`
```
#### Explicação

- **Variável Global**: `total = 0` é uma variável global, ou seja, está disponível em todo o programa.
- **Uso de `global`**: Dentro da função `somar(a, b)`, a declaração `global total` é usada para indicar que a variável `total` dentro da função se refere à variável global definida fora da função.
- **Modificação da Variável Global**: A variável `total` global é modificada dentro da função para armazenar a soma dos valores `a` e `b`.
- **Chamada da Função**: A função é chamada com `x` e `y` como argumentos, e o valor retornado é armazenado em `soma`.
- **Impressão do Resultado**: Além de imprimir a soma, o código também mostra como o valor da variável global `total` foi atualizado.

Esse exemplo demonstra como uma função pode alterar variáveis globais e como o escopo global pode ser manipulado dentro de funções.


# Exemplo 3:

```python

`total_global = 0  # Variável global  
def calcular_media(valores):     
	"""     Calcula a média de uma lista de números.     
	 Args:         
	 valores (list): Uma lista de números inteiros ou flutuantes.      
	 Returns:         
	 float: A média dos números na lista.     """     
	 soma_local = 0  # Variável local     
	 global total_global
	           
	 for valor in valores:  # Estrutura de repetição         
		 soma_local += valor  # Somando os valores 
		          
	total_global = soma_local  # Atualizando a variável global     
	media = soma_local / len(valores)  # Calculando a média     
	return media  
notas = [7.5, 8.0, 6.5, 9.0] 
media_notas = calcular_media(notas) 
print(f"A média das notas é {media_notas:.2f}.") 
print(f"A soma total global é {total_global}.")`
```
#### Explicação

- **Docstring**: A função `calcular_media(valores)` tem uma docstring, que é uma string de documentação que explica o propósito da função, os argumentos que ela aceita (`valores`, que é uma lista) e o que ela retorna (a média dos números na lista).
- **Variável Local**: `soma_local` é uma variável local usada apenas dentro da função `calcular_media`. Ela armazena a soma dos valores na lista.
- **Estrutura de Repetição**: Um laço `for` é usado para iterar sobre cada elemento da lista `valores` e somá-los em `soma_local`.
- **Escopo Global**: A variável `total_global` é declarada como global dentro da função, e seu valor é atualizado com a soma de todos os valores na lista.
- **Cálculo da Média**: A média é calculada dividindo a `soma_local` pelo número de elementos na lista (`len(valores)`).
- **Uso de `return`**: A função retorna a média calculada.
- **Chamada da Função**: A função `calcular_media` é chamada com a lista `notas`, e o valor retornado é armazenado em `media_notas`.
- **Impressão do Resultado**: O programa imprime a média das notas com duas casas decimais e também exibe o valor da variável global `total_global`, que foi atualizado com a soma dos valores da lista.

Esse exemplo combina vários conceitos: escopo global e local, uma docstring para documentação, estruturas de repetição para iterar sobre uma lista, e uma função que realiza uma operação complexa retornando um resultado.


# Exemplo 4:
```python

def media(n1=0, n2=0):
    soma = n1 + n2
    mediaTot = soma / 2
    return mediaTot

def situacao(media):
    if media >= 7:
        return "Aprovado"
    elif media >= 3 and media < 7:
        return "Recuperação"
    else:
        return "Reprovado"

n1 = float(input("Nota 1: "))
n2 = float(input("Nota 2: "))
n = media(n1, n2)
print(f"A média do aluno foi {n:.2f} e a situação foi {situacao(n)}")
```

### Definição da Função `media`


```python
`def media(n1=0, n2=0):     
	soma = n1 + n2     
	mediaTot = soma / 2     
	return mediaTot
````

- **`def media(n1=0, n2=0):`**: Define a função `media` que calcula a média de dois números. Os parâmetros `n1` e `n2` têm valores padrão de 0. Se não forem fornecidos argumentos, esses valores padrão serão utilizados.
- **`soma = n1 + n2`**: Calcula a soma dos dois números.
- **`mediaTot = soma / 2`**: Calcula a média dos dois números dividindo a soma por 2.
- **`return mediaTot`**: Retorna o valor da média calculada para o ponto onde a função foi chamada.

### Definição da Função `situacao`



```python
`def situacao(media):     
	if media >= 7:         
		return "Aprovado"      
	elif media >= 3 and media < 7:         
		return "Recuperação"     
	else:         
		return "Reprovado"`
```

- **`def situacao(media):`**: Define a função `situacao` que recebe a média como argumento e retorna uma string indicando a situação do aluno.
- **`if media >= 7:`**: Se a média for maior ou igual a 7, retorna `"Aprovado"`.
- **`elif media >= 3 and media < 7:`**: Se a média for maior ou igual a 3 e menor que 7, retorna `"Recuperação"`.
- **`else:`**: Para qualquer outra média (menos de 3), retorna `"Reprovado"`.

### Entrada do Usuário e Cálculo


```python
n1 = float(input("Nota 1: ")) 
n2 = float(input("Nota 2: ")) n = media(n1, n2)
````

- **`n1 = float(input("Nota 1: "))`**: Solicita ao usuário que insira a primeira nota e converte a entrada para um número de ponto flutuante.
- **`n2 = float(input("Nota 2: "))`**: Solicita ao usuário que insira a segunda nota e converte a entrada para um número de ponto flutuante.
- **`n = media(n1, n2)`**: Chama a função `media` com as duas notas fornecidas e armazena o resultado (a média) na variável `n`.

### Exibição do Resultado

```python
`print(f"A média do aluno foi {n:.2f} e a situação foi {situacao(n)}")`
```
`
- **`print(f"A média do aluno foi {n:.2f} e a situação foi {situacao(n)}")`**: Exibe a média do aluno com duas casas decimais (`{n:.2f}`) e a situação do aluno retornada pela função `situacao`.

### Explicação Detalhada

1. **Entrada e Cálculo**: O código solicita duas notas ao usuário e usa a função `media` para calcular a média dessas notas. A função `media` realiza a soma das duas notas e divide o resultado por 2 para encontrar a média.
    
2. **Determinação da Situação**: Após calcular a média, a função `situacao` é chamada com a média como argumento. A função `situacao` avalia a média e retorna a situação do aluno com base nos critérios definidos (Aprovado, Recuperação ou Reprovado).
    
3. **Impressão do Resultado**: A média calculada e a situação do aluno são exibidas na tela com a formatação apropriada.
    

### Resumo

Esse código é um exemplo prático de como usar funções em Python para modularizar e organizar o código. Ele ilustra a utilização de funções para realizar cálculos e decisões, a manipulação de entradas do usuário, e a formatação da saída para fornecer informações úteis e compreensíveis.

# Exemplo 5:
```python
CÓDIGO

def fatorial(num, show=True):
    """
    -> Calcula o fatorial de um número
    param num: O número a ser calculado
    param show: (opcional) Mostrar ou não a conta
    return: O valor fatorial de um número
    """
    f = 1
    for c in range(num, 0, -1):
        if show == True:
            print(c, end="")
            if c>1:
                print(" x ", end="")
            else:
                print(" = ", end="")
        f*=c
    return f
print(fatorial(8, True))


OUTPUT
8 x 7 x 6 x 5 x 4 x 3 x 2 x 1 = 40320


ANÁLISE
`def fatorial(num, show=True):     
"""     -> Calcula o fatorial de um número     
	param num: O número a ser calculado     
	param show: (opcional) Mostrar ou não a conta     
	return: O valor fatorial de um número     """     
	f = 1`

1. **Definição da função**: `def fatorial(num, show=True):`
    
    - Define uma função chamada `fatorial` que recebe dois parâmetros: `num` e `show`.
    - `num` é o número para o qual o fatorial será calculado.
    - `show` é um parâmetro opcional (com valor padrão `True`) que indica se o cálculo deve ser mostrado.
2. **Docstring**:
    
    - A string entre as aspas triplas fornece uma descrição da função, explicando o que ela faz, os parâmetros que recebe e o que retorna.
3. **Inicialização da variável `f`**: `f = 1`
    
    - Inicializa a variável `f` com o valor 1. Essa variável será usada para armazenar o resultado do cálculo do fatorial.



    `for c in range(num, 0, -1):`

4. **Loop `for`**:
    - Itera sobre um intervalo de números começando de `num` até 1, decrementando de 1 a cada iteração.
    - `range(num, 0, -1)` cria uma sequência que começa em `num` e vai até 1, inclusive, com um passo de -1.



        `if show == True:`

5. **Condição `if`**:
    - Verifica se o parâmetro `show` é `True`. Se for, o cálculo do fatorial será exibido.



            `print(c, end="")`

6. **Exibição do número atual**:
    - Imprime o valor de `c` sem quebrar a linha (`end=""`).



            `if c > 1:                 
	            print(" x ", end="")`

7. **Exibição do operador de multiplicação**:
    - Se `c` é maior que 1, imprime " x " após o número. Isso formata a saída para mostrar a operação de multiplicação.



            `else:                 
	            print(" = ", end="")`

8. **Exibição do sinal de igual**:
    - Se `c` é 1 (último número da sequência), imprime " = " para indicar o fim da expressão.



        `f *= c`

9. **Cálculo do fatorial**:
    - Multiplica `f` pelo valor de `c` e armazena o resultado de volta em `f`. Assim, `f` acumula o produto dos números.



    `return f`

10. **Retorno do resultado**:
    - Retorna o valor final de `f`, que é o fatorial do número.



`print(fatorial(8, True))`

11. **Chamada da função e impressão do resultado**:
    - Chama a função `fatorial` com o valor 8 e `show=True`, o que significa que o cálculo do fatorial será exibido no console. O resultado do fatorial de 8 é então impresso.
```

# Exemplo 6:

```python

def ficha(jogador="<<desconhecido>>", gols=0):
    print(f"O jogador {jogador} fez {gols} gol(s) no campeonato.")
n = str(input("Nome do jogador: "))
g = str(input("Número de gols: "))
if g.isnumeric():
    g = int(g)
else:
    g = 0
if n.strip() == "":
    ficha(gols=g)
else:
    ficha(n, g)

OUTPUT
Nome do jogador: 
Número de gols: 
O jogador <<desconhecido>> fez 0 gol(s) no campeonato.

ANÁLISE
`def ficha(jogador="<<desconhecido>>", gols=0):    
	print(f"O jogador {jogador} fez {gols} gol(s) no campeonato.")`

1. **Definição da função**:
    - `ficha` é uma função que aceita dois parâmetros: `jogador` e `gols`.
    - `jogador` tem um valor padrão de `"<<desconhecido>>"`, e `gols` tem um valor padrão de `0`.
    - A função imprime uma mensagem informando o nome do jogador e o número de gols que ele fez.



`n = str(input("Nome do jogador: ")) 
g = str(input("Número de gols: "))`

2. **Entrada do nome do jogador**:
    
    - `n` armazena o nome do jogador, inserido pelo usuário como uma string.
3. **Entrada do número de gols**:
    
    - `g` armazena o número de gols, inserido pelo usuário como uma string.



`if g.isnumeric():     
	g = int(g) 
else:     
	g = 0`

4. **Validação e conversão do número de gols**:
    - `g.isnumeric()` verifica se a string `g` contém apenas caracteres numéricos.
    - Se for verdade, `g` é convertido para um inteiro.
    - Se não for, `g` é definido como `0`.



`if n.strip() == "":     
	ficha(gols=g) 
else:     
	ficha(n, g)`

5. **Validação do nome do jogador e chamada da função**:
    - `n.strip() == ""` verifica se `n` é uma string vazia ou contém apenas espaços em branco.
    - Se o nome estiver vazio, a função `ficha` é chamada com o parâmetro `gols` definido como `g`, e o parâmetro `jogador` usa o valor padrão `"<<desconhecido>>"`.
    - Se o nome não estiver vazio, a função `ficha` é chamada com o nome do jogador `n` e o número de gols `g`.

### Exemplos de execução:

1. **Se o usuário inserir "Cristiano Ronaldo" e "5"**:
    
    - A função será chamada como `ficha("Cristiano Ronaldo", 5)`.
    - Saída: `O jogador Cristiano Ronaldo fez 5 gol(s) no campeonato.`
2. **Se o usuário inserir uma string vazia para o nome e "3" para os gols**:
    
    - A função será chamada como `ficha(gols=3)`, usando o valor padrão para `jogador`.
    - Saída: `O jogador <<desconhecido>> fez 3 gol(s) no campeonato.`
3. **Se o usuário inserir "Neymar" e uma string não numérica para os gols (por exemplo, "três")**:
    
    - A conversão falhará, e `g` será definido como `0`.
    - A função será chamada como `ficha("Neymar", 0)`.
    - Saída: `O jogador Neymar fez 0 gol(s) no campeonato.`

### Resumo:

Este código solicita o nome do jogador e o número de gols ao usuário. Se o número de gols não for válido (ou seja, não for numérico), é tratado como `0`. Se o nome do jogador estiver vazio, um valor padrão é usado. Em seguida, a função `ficha` imprime a informação com base nas entradas fornecidas.
```

# Exemplo 7:

```python
def leiaInt(msg):
    ok = False
    while True:
        n = str(input(msg))
        if n.isnumeric():
            valor = int(n)
            ok = True
        else:
            print("\033[0;31mERRO")
        if ok:
            break
    return valor
n = leiaInt("Digite um número: ")
print(f"Você acabou de digitar o número {n}")

OUTPUT
Digite um número: 8
Você acabou de digitar o número 8
---------------------------------
Digite um número: a
ERRO

ANÁLISE

`def leiaInt(msg):
	ok = False     
	while True:         
		n = str(input(msg))         
		if n.isnumeric():             
			valor = int(n)             
			ok = True         
		else:             
			print("\033[0;31mERRO")         
		if ok:             
			break     
	return valor`

1. **Definição da função**: `def leiaInt(msg):`
    
    - Define a função `leiaInt` que recebe um parâmetro `msg`. Esse parâmetro será a mensagem exibida ao usuário para solicitar a entrada.
2. **Inicialização da variável `ok`**: `ok = False`
    
    - Inicializa a variável `ok` com `False`. Esta variável é usada para controlar quando uma entrada válida foi fornecida.
3. **Loop `while True`**:
    
    - Cria um loop infinito que só será interrompido quando `ok` for `True`.
4. **Entrada do usuário**: `n = str(input(msg))`
    
    - Solicita ao usuário uma entrada com a mensagem `msg` e armazena a entrada como uma string em `n`.
5. **Validação da entrada**: `if n.isnumeric():`
    
    - Verifica se a string `n` contém apenas caracteres numéricos.
6. **Conversão e atualização**:
    
    - `valor = int(n)`: Se a entrada é numérica, converte a string `n` para um inteiro e armazena em `valor`.
    - `ok = True`: Atualiza `ok` para `True`, indicando que a entrada é válida e o loop deve ser interrompido.
7. **Mensagem de erro**: `else: print("\033[0;31mERRO")`
    
    - Se a entrada não for numérica, imprime "ERRO" em vermelho (usando códigos ANSI para cor no terminal).
8. **Interrupção do loop**: `if ok: break`
    
    - Se `ok` for `True`, o loop é interrompido, saindo da repetição.
9. **Retorno do valor**: `return valor`
    
    - Retorna o valor inteiro obtido da entrada do usuário.


`n = leiaInt("Digite um número: ") 
print(f"Você acabou de digitar o número {n}")`

10. **Chamada da função `leiaInt`**: `n = leiaInt("Digite um número: ")`
    
    - Chama a função `leiaInt`, passando a mensagem `"Digite um número: "`. O resultado é armazenado na variável `n`.
11. **Exibição do resultado**: `print(f"Você acabou de digitar o número {n}")`
    
    - Imprime o número digitado pelo usuário, confirmando a entrada.

### Exemplos de execução:

1. **Entrada válida**:
    
    - Se o usuário digitar "42", a função converte a entrada para o número inteiro 42 e imprime: `Você acabou de digitar o número 42`.
2. **Entrada inválida**:
    
    - Se o usuário digitar "abc", o código exibirá "ERRO" em vermelho e solicitará novamente a entrada. O loop continuará até que uma entrada válida seja fornecida.

### Resumo:

A função `leiaInt` solicita ao usuário que insira um número, verifica se a entrada é um número inteiro positivo e, se não for, exibe uma mensagem de erro e solicita a entrada novamente. Quando uma entrada válida é fornecida, a função retorna o número e o imprime.
```

# Exemplo 8:
```python
def notas(*n, sit=False):
    """
    .> Função para analisar notas e situações de vários alunos
    param m: uma ou mais notas dos alunos (aceita várias)
    param sit: valor opcional, indicando se deve ou não adicionar a situação
    return: dicionário com varias informações sobre a situação da turma
    """
    r = dict()
    r['total'] = len(n)
    r["maior"] = max(n)
    r["menor"] = min(n)
    r["media"] = sum(n)/len(n)
    if sit:
        if r["media"] >=7:
            r["situação"] = "BOA"
        elif r["media"] >= 5:
            r["situação"] = "RAZOÁVEL"
        else:
            r["situação"] = "RUIM"
    return r

resp=notas(5.5, 2.5, 1.5, sit=True)
print(resp)
help(notas)

OUTPUT
{'total': 3, 'maior': 5.5, 'menor': 1.5, 'media': 3.1666666666666665, 'situação': 'RUIM'}
Help on function notas in module __main__:

notas(*n, sit=False)
    .> Função para analisar notas e situações de vários alunos
    param m: uma ou mais notas dos alunos (aceita várias)
    param sit: valor opcional, indicando se deve ou não adicionar a situação
    return: dicionário com varias informações sobre a situação da turma

ANÁLISE

def notas(*n, sit=False):
    """
    .> Função para analisar notas e situações de vários alunos
    param m: uma ou mais notas dos alunos (aceita várias)
    param sit: valor opcional, indicando se deve ou não adicionar a situação
    return: dicionário com varias informações sobre a situação da turma
    """
    r = dict()
    r['total'] = len(n)
    r["maior"] = max(n)
    r["menor"] = min(n)
    r["media"] = sum(n)/len(n)
    if sit:
        if r["media"] >=7:
            r["situação"] = "BOA"
        elif r["media"] >= 5:
            r["situação"] = "RAZOÁVEL"
        else:
            r["situação"] = "RUIM"
    return r
    - **Definição da função**: `def notas(*n, sit=False):`
    
    - Define a função `notas` que aceita um número variável de argumentos (`*n`) e um parâmetro opcional `sit` com valor padrão `False`.
    - `*n` permite passar um número variável de notas como argumentos para a função.
- **Docstring**:
    
    - Descreve o propósito da função, os parâmetros e o que ela retorna.
    - `param m`: Deveria ser `param n` para refletir que a função aceita várias notas.
    - `param sit`: Especifica que é um parâmetro opcional para determinar se a situação deve ser incluída.
- **Criação do dicionário `r`**: `r = dict()`
    
    - Cria um dicionário vazio `r` que será usado para armazenar as informações sobre as notas.
- **Total de notas**: `r['total'] = len(n)`
    
    - Armazena o número total de notas no dicionário `r`.
- **Nota máxima**: `r["maior"] = max(n)`
    
    - Armazena a maior nota entre as fornecidas.
- **Nota mínima**: `r["menor"] = min(n)`
    
    - Armazena a menor nota entre as fornecidas.
- **Média das notas**: `r["media"] = sum(n) / len(n)`
    
    - Calcula a média das notas e armazena no dicionário.
- **Determinação da situação**:
    
    - `if sit:`: Se `sit` for `True`, o código entra neste bloco para determinar a situação da turma.
    - `if r["media"] >= 7:`: Se a média for maior ou igual a 7, a situação é considerada "BOA".
    - `elif r["media"] >= 5:`: Se a média for maior ou igual a 5, mas menor que 7, a situação é "RAZOÁVEL".
    - `else:`: Se a média for menor que 5, a situação é "RUIM".
- **Retorno do dicionário**: `return r`
    
    - Retorna o dicionário `r` com todas as informações calculadas.

resp=notas(5.5, 2.5, 1.5, sit=True)
print(resp)
help(notas)
- **Chamada da função**: `resp = notas(5.5, 2.5, 1.5, sit=True)`
    
    - Chama a função `notas` com três notas e a situação definida como `True`.
- **Impressão do resultado**: `print(resp)`
    
    - Imprime o dicionário retornado pela função `notas`.

`help(notas)`

12. **Ajuda da função**: `help(notas)`
    - Exibe a documentação (docstring) da função `notas` para fornecer informações sobre como usar a função.

### Saída esperada:

Para a chamada `notas(5.5, 2.5, 1.5, sit=True)`, a função irá calcular:

- Total de notas: 3
- Maior nota: 5.5
- Menor nota: 1.5
- Média das notas: (5.5 + 2.5 + 1.5) / 3 = 3.833...
- Situação: "RUIM" (porque a média é menor que 5)

### Notas:

- O código está correto e funciona conforme esperado. No entanto, a documentação da função tem um pequeno erro (`param m` deveria ser `param n`).
- A função `help(notas)` exibirá a docstring e, portanto, ajudará a entender a finalidade e o uso da função.
```

# Exemplo 9:

```python
from time import sleep
c = ("\033[m",
     "\033[0;30;41m",
     "\033[0;30;42m",
     "\033[0;30;43m",
     "\033[0;30;44m",
     "\033[0;30;45m",
     "\033[7;30m")

def ajuda(com):
    titulo(f"Acessando o manual do comando  \" {com}\"", 4)
    print(c[6], end="")
    print(com)
    print(c[0], end="")
    sleep(2)

def titulo(msg, cor=0):
    tam = len(msg) + 4
    print(c[cor], end="")
    print("~"*tam)
    print(f"    {msg}")
    print("~"*tam)
    sleep(1)

comando = ""
while True:
    titulo("SISTEMA DE AJUDA PyHELP", 2)
    comando = str(input("Função ou biblioteca: "))
    if comando.upper() == "FIM":
        break
    else:
        ajuda(comando)
    titulo("ATÉ LOGO", 1)


OUTPUT
~~~~~~~~~~~~~~~~~~~~~~~~~~~
    SISTEMA DE AJUDA PyHELP
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Função ou biblioteca: print
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Acessando o manual do comando  " print"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Help on built-in function print in module builtins:

print(*args, sep=' ', end='\n', file=None, flush=False)
    Prints the values to a stream, or to sys.stdout by default.
    
    sep
      string inserted between values, default a space.
    end
      string appended after the last value, default a newline.
    file
      a file-like object (stream); defaults to the current sys.stdout.
    flush
      whether to forcibly flush the stream.

~~~~~~~~~~~~
    ATÉ LOGO
~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~
    SISTEMA DE AJUDA PyHELP
~~~~~~~~~~~~~~~~~~~~~~~~~~~
Função ou biblioteca: fim

ANÁLISE

`from time import sleep`

1. **Importação da função `sleep`**:
    - Importa a função `sleep` do módulo `time`, que é usada para pausar a execução do programa por um número de segundos.

c = ("\033[m",
     "\033[0;30;41m",
     "\033[0;30;42m",
     "\033[0;30;43m",
     "\033[0;30;44m",
     "\033[0;30;45m",
     "\033[7;30m")
**Definição das cores**:

- Define uma tupla `c` contendo códigos de cores ANSI para formatação do texto no terminal.
- Cada código corresponde a um estilo de cor de fundo e texto. Por exemplo, `"\033[0;30;41m"` configura texto branco sobre fundo vermelho.


def ajuda(com):
    titulo(f"Acessando o manual do comando  \" {com}\"", 4)
    print(c[6], end="")
    print(com)
    print(c[0], end="")
    sleep(2)

**Definição da função `ajuda`**:

- Recebe um parâmetro `com`, que é o comando ou nome da biblioteca para o qual se deseja acessar a ajuda.
- Chama a função `titulo` para imprimir um título com a mensagem "Acessando o manual do comando" e o nome do comando, usando a cor correspondente ao índice 4 (fundo roxo).
- Imprime o nome do comando com o estilo de cor e fundo definidos pelo código de índice 6 (fundo branco com texto preto).
- Retorna ao estilo padrão (índice 0).
- Pausa a execução por 2 segundos.

def titulo(msg, cor=0):
    tam = len(msg) + 4
    print(c[cor], end="")
    print("~"*tam)
    print(f"    {msg}")
    print("~"*tam)
    sleep(1)

**Definição da função `titulo`**:

- Recebe uma mensagem `msg` e uma cor opcional `cor` (valor padrão é 0).
- Calcula o comprimento da linha de borda com base no comprimento da mensagem (`tam`).
- Imprime uma linha de borda com a cor especificada.
- Imprime a mensagem centralizada com bordas superior e inferior.
- Pausa a execução por 1 segundo.



comando = ""
while True:
    titulo("SISTEMA DE AJUDA PyHELP", 2)
    comando = str(input("Função ou biblioteca: "))
    if comando.upper() == "FIM":
        break
    else:
        ajuda(comando)
    titulo("ATÉ LOGO", 1)


1. **Loop principal**:
    - Exibe o título "SISTEMA DE AJUDA PyHELP" com a cor de índice 2 (fundo verde com texto preto).
    - Solicita ao usuário que insira o nome de uma função ou biblioteca.
    - Se o comando inserido pelo usuário for "FIM" (ignora maiúsculas/minúsculas), o loop termina.
    - Caso contrário, chama a função `ajuda` passando o comando inserido.
    - Após chamar `ajuda`, exibe a mensagem "ATÉ LOGO" com a cor de índice 1 (fundo vermelho com texto preto).

### Resumo do funcionamento:

- O programa exibe um menu de ajuda com um título e aguarda a entrada do usuário para uma função ou biblioteca.
- Exibe informações sobre a função ou biblioteca solicitada (simula acesso ao manual).
- Permite ao usuário sair digitando "FIM".
- Usa cores ANSI para formatação e estilo do texto no terminal.

### Exemplo de execução:

1. **Inicialização**:
    
    - O programa exibe o título "SISTEMA DE AJUDA PyHELP" com fundo verde.
2. **Entrada do usuário**:
    
    - Usuário insere "print".
3. **Exibição de ajuda**:
    
    - O programa exibe "Acessando o manual do comando 'print'" em roxo.
    - Em seguida, mostra o comando "print" com fundo branco e texto preto.
    - Pausa por 2 segundos.
4. **Saída**:
    
    - Se o usuário digitar "FIM", o programa exibe "ATÉ LOGO" em fundo vermelho e encerra.

```


# Projetinho calculo de notas 2.0

```python
def media(n1=0, n2=0, n3=0):
    """
    -> função para calcular a media das notas
    param n1: nota 1
    param n2: nota2
    param n3: nota 3
    return: retorna a media total
    """
    soma = n1 + n2 + n3
    mediaTot = soma / 3
    return mediaTot

def situacao(media):
    """
    Função para determinar a situação do aluno com base na média
    """
    if media >= 7:
        return "Aprovado!"
    elif 4 < media < 7:
        return "Recuperação!"
    else:
        return "Reprovado!"  

# Inicialização das estruturas para armazenar os dados
alunos_lista = []

while True:
    # Coleta de dados do aluno
    nome = input("Nome do aluno: ")
    n1 = float(input("Nota 1: "))
    n2 = float(input("Nota 2: "))
    n3 = float(input("Nota 3: "))
  
    # Cálculo da média e determinação da situação
    media_aluno = media(n1, n2, n3)
    situacao_aluno = situacao(media_aluno)

    # Armazenamento dos dados do aluno em um dicionário
    aluno_dicionario = {
        "Nome": nome,
        "Notas": [n1, n2, n3],
        "Media": media_aluno,
        "Situação": situacao_aluno
    }

    # Adiciona o dicionário do aluno à lista de alunos
    alunos_lista.append(aluno_dicionario)

    # Pergunta se o usuário quer continuar inserindo dados
    continuar = input("Quer continuar? [S/N] ").strip().lower()
    if continuar == "n":
        break

# Impressão do cabeçalho com os dados de todos os alunos
print("\n--- Resultados Finais ---")
print(f"{'Nome':<10} {'Notas':<20} {'Média':<6} {'Situação':<15}")
print("-" * 50)
for aluno in alunos_lista:
    notas_formatadas = ', '.join([f"{nota:.1f}" for nota in aluno["Notas"]])
    print(f"{aluno['Nome']:<10} {notas_formatadas:<20} {aluno['Media']:<6.2f} {aluno['Situação']:<15}")****
```

```python
OUTPUT

Nome do aluno: matheus
Nota 1: 10
Nota 2: 10
Nota 3: 10
Quer continuar? [S/N] s
Nome do aluno: raissa
Nota 1: 5
Nota 2: 5
Nota 3: 5
Quer continuar? [S/N] s
Nome do aluno: lucas
Nota 1: 2
Nota 2: 2
Nota 3: 2
Quer continuar? [S/N] n

--- Resultados Finais ---
Nome       Notas                Média  Situação       
--------------------------------------------------    
matheus    10.0, 10.0, 10.0     10.00  Aprovado!
raissa     5.0, 5.0, 5.0        5.00   Recuperação!
lucas      2.0, 2.0, 2.0        2.00   Reprovado!
```

```python 
ANÁLISE

1. **Função `media`**:
    - **Objetivo**: Calcula a média de três notas.
    - **Parâmetros**: Recebe três notas (`n1`, `n2`, `n3`) com valores padrão de 
    - **Retorno**: A média das três notas é retornada como um valor float.
    
    
    `def media(n1=0, n2=0, n3=0):
         """      
         -> Função para calcular a média das notas.     
         param n1: Nota 1    
         param n2: Nota 2     
         param n3: Nota 3     
         return: Retorna a média total.    
         """     
	     soma = n1 + n2 + n3    
		 mediaTot = soma / 3     
         return mediaTot`
    
2. **Função `situacao`**:
    
    - **Objetivo**: Determina a situação do aluno com base na média calculada.
    - **Parâmetro**: Recebe a média do aluno como parâmetro.
    - **Retorno**: Retorna uma string que pode ser "Aprovado!", "Recuperação!" ou "Reprovado!" dependendo da média.
    
    
    `def situacao(media):
         """      
         -> Função para determinar a situação do aluno com base na média.     """     if media >= 7:         
	         return "Aprovado!"     
	    elif 4 < media < 7:         
		    return "Recuperação!"     
		else:         
			return "Reprovado!"`
    
3. **Coleta e Processamento dos Dados dos Alunos**:
    
    - **Objetivo**: Permite que o usuário insira os dados de múltiplos alunos, calcula a média e determina a situação de cada um.
    - **Estrutura de Dados**: Os dados de cada aluno são armazenados em um dicionário (`aluno_dicionario`), e cada dicionário é adicionado a uma lista (`alunos_lista`).
    - **Loop Infinito**: O loop permite a inserção de dados de vários alunos até que o usuário escolha sair (digitando "n").
    
# Inicialização das estruturas para armazenar os dados
alunos_lista = []

while True:
    # Coleta de dados do aluno
    nome = input("Nome do aluno: ")
    n1 = float(input("Nota 1: "))
    n2 = float(input("Nota 2: "))
    n3 = float(input("Nota 3: "))
  
    # Cálculo da média e determinação da situação
    media_aluno = media(n1, n2, n3)
    situacao_aluno = situacao(media_aluno)

    # Armazenamento dos dados do aluno em um dicionário
    aluno_dicionario = {
        "Nome": nome,
        "Notas": [n1, n2, n3],
        "Media": media_aluno,
        "Situação": situacao_aluno
    }

    # Adiciona o dicionário do aluno à lista de alunos
    alunos_lista.append(aluno_dicionario)

    # Pergunta se o usuário quer continuar inserindo dados
    continuar = input("Quer continuar? [S/N] ").strip().lower()
    if continuar == "n":
        break
    
4. **Exibição dos Resultados**:
    
    - **Objetivo**: Imprime um resumo com o nome, notas, média e situação de todos os alunos inseridos.
    - **Formatação**: As notas são formatadas com uma casa decimal, e as colunas são alinhadas para melhorar a legibilidade.
    
# Impressão do cabeçalho com os dados de todos os alunos
print("\n--- Resultados Finais ---")
print(f"{'Nome':<10} {'Notas':<20} {'Média':<6} {'Situação':<15}")
print("-" * 50)
for aluno in alunos_lista:
    notas_formatadas = ', '.join([f"{nota:.1f}" for nota in aluno["Notas"]])
    print(f"{aluno['Nome']:<10} {notas_formatadas:<20} {aluno['Media']:<6.2f} {aluno['Situação']:<15}")****
    

### Boas Práticas Utilizadas

- **Uso de Docstrings**: A função `media` e `situacao` possuem docstrings que explicam claramente seu propósito e como utilizá-las.
- **Manipulação de Listas e Dicionários**: O uso de listas para armazenar vários dicionários (um para cada aluno) é uma boa prática para manter os dados organizados.
- **Formatação de Saída**: O uso de formatação alinhada para a exibição dos resultados facilita a leitura e compreensão.

### Sugestões de Melhoria

- **Validação de Entrada**: Para evitar erros, seria interessante adicionar uma validação para garantir que o usuário insira valores válidos (ex., números para as notas).
- **Possibilidade de Inserir Mais de Três Notas**: Caso deseje flexibilizar o número de notas, a função `media` poderia ser ajustada para aceitar um número variável de notas.

```
