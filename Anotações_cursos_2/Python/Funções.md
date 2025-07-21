 Para declararmos uma função, utilizamos #def e abaixo de def colocamos o que essa função irá fazer, por exemplo:
 `def nome_da_função()`
	 `funcionalidade

# Exemplo: 
```python

`def cabeçalho(): >>> definindo nome da função
    `print("-"*30)
    `print(f"SISTEMA DE ALUNOS")
    `print("-"*30)
    `print("CADASTRO DE FUNCINÁRIOS") >>> funcionalidades
    `print("-"*30)
    `print("ERRO NO SISTEMA")
    `print("-"*30)
`cabeçalho() >>> chamando a função
```

```python
|output|
------------------------------
SISTEMA DE ALUNOS
------------------------------
CADASTRO DE FUNCINÁRIOS       
------------------------------
ERRO NO SISTEMA
------------------------------
```

Podemos usar parâmetros nas funções, no exemplo acima  recriamos as linhas entre as mensagens impressas várias vezes, porém podemos usar a função inseirr a mensagem que queremos com o parâmetro que quisermos, por exemplo:
```python
def mensagem(msg):
    print("-"*20)
    print(msg)
    print("-"*20)
mensagem(str(input("Nome: ")))
```

```python
output
Nome: matheus
--------------------
matheus
--------------------
```
depois de definirmos o nome da função, nos parênteses inserimos o nome do parâmetro, como uma variável para a função
por fim, chamamos a função e abrimos o parenteses pedindo ao usúario que insira seu nome e teve como output as linhas definidas na função e o parâmetro msg(nome)

Também podemos fazer a função se repetir


```python
def titulo(txt):
    print("-"*30)
    print(txt)
    print("-"*30)
titulo("    curso em video      ")
titulo("    Matheus Avolio      ")
titulo("    hello world      ")
```

```python
|output|
------------------------------
    curso em video            
------------------------------
------------------------------
    Matheus Avolio            
------------------------------
------------------------------
    hello world      
------------------------------
```


Podemos também pedir para fazer a media de um aluno, por exmeplo: 

```python
def media(a, b):
    s = (a + b) / 2
    print(f"A media do aluno é {s}")
media(float(input("Nota 1: ")), float(input("Nota 2: ")))
```

```python
OUTPUT
Nota 1: 8
Nota 2: 8
A media do aluno é 8.0
```


Exemplo de uma calculadora utilizando funções:
```python
def erro():
	print("Erro! insira apenas [S] para sim e [N] para não")
def calculadora(num):
	for c in range(1, 11):
	    print(f"{num} x {c} = {num * c}")
while True:
    calculadora(int(input("Insira o número da tabuada que você deseja: ")))
    while True:
        continuar = str(input("Quer continuar? [S/N] ")).lower()[0]
        if continuar in "sn":
            break
        erro()
    if continuar == "n":
        print("Volte sempre!")
        break
```

```python
OUTPUT

Insira o número da tabuada que você deseja: 5
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
Quer continuar? [S/N] s
Insira o número da tabuada que você deseja: 3
3 x 1 = 3  
3 x 2 = 6  
3 x 3 = 9  
3 x 4 = 12 
3 x 5 = 15 
3 x 6 = 18 
3 x 7 = 21 
3 x 8 = 24 
3 x 9 = 27 
3 x 10 = 30
Quer continuar? [S/N] p
Erro! insira apenas [S] para sim e [N] para não
Quer continuar? [S/N] n
Volte sempre!
```

## Análise completa:
### 1. Função `erro`

```python
def erro():     
print("Erro! insira apenas [S] para sim e [N] para não")`
```

- **Linha 1:** Define uma função chamada `erro`. As funções são blocos de código reutilizáveis que podem ser chamadas em qualquer parte do programa.
- **Linha 2:** Dentro da função `erro`, a instrução `print()` é usada para exibir a mensagem "Erro! insira apenas [S] para sim e [N] para não". Esta função será utilizada para alertar o usuário caso ele insira uma resposta inválida.

### 2. Função `calculadora`

```python
`def calculadora(num):
	for c in range(1, 11):         
		print(f"{num} x {c} = {num * c}")
```

- **Linha 3:** Define uma função chamada `calculadora` que aceita um argumento `num`.
- **Linha 4:** Um loop `for` é iniciado. A variável `c` irá assumir valores de 1 a 10 (inclusive). Isso é feito usando a função `range(1, 11)`.
- **Linha 5:** Dentro do loop `for`, o programa exibe no console o resultado da multiplicação de `num` por `c` em cada iteração, usando uma `f-string` para formatar a saída. Assim, a função `calculadora` exibe a tabuada de `num` de 1 a 10.

### 3. Loop principal

```python
`while True:     
	calculadora(int(input("Insira o número da tabuada que você deseja: ")))`
```

- **Linha 6:** Um `while True` é usado para criar um loop infinito. Esse loop só será interrompido explicitamente dentro do código.
- **Linha 7:** A função `input()` exibe a mensagem "Insira o número da tabuada que você deseja: " e espera o usuário digitar um número. O `input()` captura o valor digitado como uma string.
    - **int():** Converte o valor digitado para um inteiro. Se o usuário não digitar um número válido, o programa lançará um erro.
    - **calculadora(...):** A função `calculadora` é chamada com o número inserido pelo usuário, e a tabuada desse número é exibida.

### 4. Loop de continuação

```python
 `while True:         
	 continuar = str(input("Quer continuar? [S/N] ")).lower()[0]         
	 if continuar in "sn":             
		 break         
	erro()
```


- **Linha 8:** Outro `while True` cria um novo loop infinito. Este loop pergunta ao usuário se ele deseja continuar.
- **Linha 9:** A função `input()` solicita que o usuário informe se deseja continuar ou não, com a mensagem "Quer continuar? [S/N]". O valor inserido é convertido para uma string (`str()`), é transformado para minúsculo (`lower()`) e apenas o primeiro caractere é capturado (`[0]`).
    - Isso garante que a entrada do usuário seja tratada de forma consistente, independentemente de ele usar letras maiúsculas ou minúsculas.
- **Linha 10:** Verifica se o caractere capturado está na string `"sn"` (ou seja, se é `'s'` para sim ou `'n'` para não).
    - Se o valor estiver em `"sn"`, o `break` interrompe o loop interno.
- **Linha 11:** Se o valor digitado não for `'s'` ou `'n'`, a função `erro` é chamada, e a mensagem de erro é exibida.

### 5. Finalizando o programa

```python
python
    `if continuar == "n":
             print("Volte sempre!")
	         break
```


- **Linha 12:** Fora do loop interno, o programa verifica se o usuário respondeu `'n'` (não). Se sim, o programa exibe "Volte sempre!".
- **Linha 13:** O `break` interrompe o loop externo (o loop principal), encerrando a execução do programa.

### Resumo

- O código permite ao usuário escolher um número para calcular a tabuada, exibindo o resultado da multiplicação de 1 a 10.
- Após exibir a tabuada, o programa pergunta se o usuário deseja continuar. Se o usuário inserir `'s'`, o loop reinicia, permitindo uma nova escolha de número. Se o usuário inserir `'n'`, o programa exibe uma mensagem de despedida e termina.
- Caso o usuário insira algo diferente de `'s'` ou `'n'`, o programa exibe uma mensagem de erro e solicita novamente a resposta.
_______________________________________________________________________
_______________________________________________________________________
Agora vamos supor que você não saiba quantos parâmetros irá ser inserido, podemos fazer da seguinte fomra:
```python
def contador(*num):
	print(num)

contador(2, 1, 0)
contador(8, 0)
contador(4, 4, 7, 6, 2)
```
No output, o python irá criar #tuplas com os valores dos parâmetros
```python
OUTPUT
(2, 1, 0)
(8, 0)
(4, 4, 7, 6, 2)
```

E dessa forma, podemos #iterar sobre os resultados desses #parâmetros como se fossem #tuplas:
```python
def contador(*num):
    for v in num:
        print(v)

contador(2, 1, 0)
contador(8, 0)
contador(4, 4, 7, 6, 2)
```

```python
OUTPUT
2
1
0
8
0
4
4
7
6
2
```

Podemos também adicionar funções dentro de outras funções, por exemplo;

```python
def linha():
    print("-"*30)
    
def contador(*num):
    linha()
    for v in num:
        print(v)
    linha()

contador(2, 1, 0)
contador(8, 0)
contador(4, 4, 7, 6, 2)
```

```python
OUTPUT
------------------------------
2
1
0
------------------------------
------------------------------
8
0
------------------------------
------------------------------
4
4
7
6
2
------------------------------
```

Podemos também trabalhar com listas dentro das funções:

```python
CÓDIGO

def dobra(lst):
    pos = 0
    while pos < len(lst):
        lst[pos] *=2
        pos+=1

valores = [6, 3, 9, 1, 0, 2]
dobra(valores)
print(valores)
```
```python
OUTPUT

[12, 6, 18, 2, 0, 4]
```

```python
ANÁLISE

1. Função `dobra`


`def dobra(lst):
	pos = 0     
	while pos < len(lst):         
		lst[pos] *= 2         
		pos += 1`

- Linha 1: Define uma função chamada `dobra` que aceita um argumento `lst`, que deve ser uma lista.
- Linha 2: Inicializa a variável `pos` com o valor 0. Esta variável servirá como um índice para percorrer a lista.
- Linha 3: Inicia um loop while que continuará enquanto `pos` for menor que o comprimento da lista (len(lst)).
- Linha 4: Dentro do loop, o valor do elemento na posição `pos` da lista (lst[pos]) é dobrado (*= 2). Isso significa que o valor atual é multiplicado por 2 e o resultado é armazenado de volta na mesma posição.
- Linha 5: A variável `pos` é incrementada em 1 (pos += 1), o que faz com que o loop passe para o próximo elemento da lista na próxima iteração.

2. Lista `valores` e chamada da função


`valores = [6, 3, 9, 1, 0, 2] dobra(valores) print(valores)`

- Linha 6: Cria uma lista chamada `valores` contendo os elementos [6, 3, 9, 1, 0, 2].
- Linha 7: A função `dobra` é chamada com a lista `valores` como argumento. Esta função irá modificar diretamente a lista `valores`, dobrando o valor de cada um dos seus elementos.
- Linha 8: Usa a função `print` para exibir a lista `valores` após a chamada da função `dobra`. Como a função `dobra` modificou a lista original, o resultado exibido será a lista com todos os seus valores dobrados.

Saída do Programa: A função `dobra` modifica a lista `valores` de maneira que todos os seus elementos sejam multiplicados por 2. Portanto, a saída do programa após a execução do código será:

`[12, 6, 18, 2, 0, 4]`

Resumo:

- O código define uma função que percorre cada elemento de uma lista e dobra o valor desse elemento.
- A lista original é modificada diretamente, pois as listas em Python são mutáveis.
- Ao final, a lista `valores` é impressa, mostrando os valores após serem dobrados.```



________________________________________________________________________
------------------------------------------------------------------------
```python

from time import sleep
from random import randint
numeros = []
def sorteia():
    print("Sorteando 5 valores da lista:", end=" ", flush=True)
    sleep(0.5)
    for _ in range(5):
        num = randint(1, 5)
        sleep(0.8)
        print(num, end=" ", flush=True)
        numeros.append(num)

sorteia()

  
def somaPar():
    print()
    s = 0
    for c in numeros:
        if c % 2 == 0:
            s +=c
    print(f"Somando os valores pares de {numeros}, temos {s}")

somaPar()
```

### Uso de  #flush=True

Quando você define `flush=True`, está dizendo ao Python para "descarregar" o buffer imediatamente após a chamada da função `print()`. Isso significa que a saída é exibida na tela imediatamente, mesmo que a linha não tenha sido concluída ou o buffer não esteja cheio.

### Aplicação no Código



`print("Sorteando 5 valores da lista:", end=" ", flush=True)`

- **`end=" "`**: Especifica que o `print()` não deve pular para a próxima linha após exibir o texto, mas sim adicionar um espaço (`" "`) e continuar na mesma linha.
- **`flush=True`**: Garante que a mensagem "Sorteando 5 valores da lista:" apareça na tela imediatamente, sem esperar por mais dados ou o preenchimento do buffer.

Sem o `flush=True`, especialmente em situações onde há uma pequena pausa entre as operações (como com `sleep`), a mensagem inicial poderia não ser exibida imediatamente. O `flush=True` é particularmente útil quando você deseja exibir algo no console antes de uma operação que leva tempo, como uma animação, um carregamento ou, como no seu caso, um sorteio com pausas entre os números.

### Resumo

- **`flush=True`** força a saída de dados para a tela imediatamente, sem esperar o preenchimento do buffer ou o término da linha.
- **No seu código**, isso é usado para garantir que a mensagem "Sorteando 5 valores da lista:" apareça no console imediatamente, antes de começar a mostrar os números sorteados com pausas entre eles.


```python
from time import sleep
from random import randint
numeros = []

def sorteia():
    print("Sorteando 5 valores da lista:", end=" ", flush=True)
    sleep(0.5)
    for _ in range(5):
        num = randint(1, 5)
        sleep(0.8)
        print(num, end=" ", flush=True)
        numeros.append(num)

sorteia()

def somaPar():
    print()
    s = 0
    for c in numeros:
        if c % 2 == 0:
            s +=c
    print(f"Somando os valores pares de {numeros}, temos {s}")

somaPar()
```

```python
OUTPUT

Sorteando 5 valores da lista: 1 2 4 5 1 
Somando os valores pares de [1, 2, 4, 5, 1], temos 6
```

```python
ANÁLISE

### Importações
`from time import sleep 
from random import randint`

- **`from time import sleep`**: Importa a função `sleep` do módulo `time`. A função `sleep` faz com que o programa pause sua execução por um determinado número de segundos.
- **`from random import randint`**: Importa a função `randint` do módulo `random`. A função `randint(a, b)` retorna um número inteiro aleatório entre `a` e `b`, inclusive.


### Variáveis Globais
`numeros = []`

- **`numeros = []`**: Inicializa uma lista vazia chamada `numeros`. Esta lista armazenará os números gerados aleatoriamente.


### Função `sorteia()`
`def sorteia():     
	print("Sorteando 5 valores da lista:", end=" ", flush=True)     
	sleep(0.5)     
	for _ in range(5):         
		num = randint(1, 5)         
		sleep(0.8)         
		print(num, end=" ", flush=True)         
		numeros.append(num)`

- **`def sorteia():`**: Define a função `sorteia`, que não recebe parâmetros e não retorna nada explicitamente.
- **`print("Sorteando 5 valores da lista:", end=" ", flush=True)`**: Imprime a mensagem `"Sorteando 5 valores da lista:"` na tela, sem mudar de linha (`end=" "`). O argumento `flush=True` força a saída imediata do texto, garantindo que ele apareça antes de qualquer pausa subsequente.
- **`sleep(0.5)`**: Pausa a execução do programa por 0,5 segundos, criando um pequeno intervalo antes de começar a sortear os números.
- **`for _ in range(5):`**: Um loop que executa 5 vezes. O `_` é utilizado como uma convenção quando o valor da variável de loop não será utilizado dentro do loop.
    - **`num = randint(1, 5)`**: Em cada iteração, gera um número inteiro aleatório entre 1 e 5, armazenando-o na variável `num`.
    - **`sleep(0.8)`**: Pausa a execução do programa por 0,8 segundos antes de exibir o próximo número, criando um efeito de sorteio.
    - **`print(num, end=" ", flush=True)`**: Imprime o número sorteado na tela, sem mudar de linha (`end=" "`), e força a saída imediata (`flush=True`).
    - **`numeros.append(num)`**: Adiciona o número sorteado à lista `numeros`.


### Chamando a função `sorteia()`
`sorteia()`

- **`sorteia()`**: Chama a função `sorteia` para executar o sorteio dos 5 números e exibi-los na tela.


### Função `somaPar()`
`def somaPar():     
	print()     
	s = 0     
	for c in numeros:         
		if c % 2 == 0:             
		s += c     
	print(f"Somando os valores pares de {numeros}, temos {s}")`

- **`def somaPar():`**: Define a função `somaPar`, que não recebe parâmetros e não retorna nada explicitamente.
- **`print()`**: Imprime uma linha em branco para separar a saída anterior.
- **`s = 0`**: Inicializa a variável `s` com o valor 0. Esta variável será usada para acumular a soma dos números pares.
- **`for c in numeros:`**: Itera sobre cada número `c` na lista `numeros`.
    - **`if c % 2 == 0:`**: Verifica se o número `c` é par (ou seja, se o resto da divisão de `c` por 2 é igual a 0).
    - **`s += c`**: Se o número for par, ele é adicionado à variável `s`.
- **`print(f"Somando os valores pares de {numeros}, temos {s}")`**: Exibe a lista `numeros` e a soma dos números pares contidos nela.


### Chamando a função `somaPar()`
`somaPar()`

- **`somaPar()`**: Chama a função `somaPar` para calcular e exibir a soma dos números pares na lista `numeros`.


### Resumo
O código gera 5 números aleatórios entre 1 e 5, armazena-os na lista `numeros`, e depois calcula e exibe a soma dos números pares dessa lista. O uso das funções `sleep` e `print` com `flush=True` adiciona uma animação ao sorteio dos números, pausando a execução e garantindo que os números apareçam gradualmente na tela.
```

# #InteractiveHELP
Utilizamos o `help()` e em seguida o nome da função ou biblioteca que o python irá explicar todo o funcionamento
por exemplo:

```python
help()
```

```python
Menssagem exibida no terminal

Welcome to Python 3.11's help utility! If this is your first time using 
Python, you should definitely check out the tutorial at
https://docs.python.org/3.11/tutorial/.

Enter the name of any module, keyword, or topic to get help on writing  
Python programs and using Python modules.  To get a list of available   
modules, keywords, symbols, or topics, enter "modules", "keywords",     
"symbols", or "topics".

Each module also comes with a one-line summary of what it does; to list 
the modules whose name or summary contain a given string such as "spam",
enter "modules spam".

To quit this help utility and return to the interpreter,
enter "q" or "quit".

help> 
```
Outro exemplo:

```python
print(input.__doc__)
```

```python
Mensagem exibida no terminal

Read a string from standard input.  The trailing newline is stripped.       

The prompt string, if given, is printed to standard output without a        
trailing newline before reading input.

If the user hits EOF (*nix: Ctrl-D, Windows: Ctrl-Z+Return), raise EOFError.
On *nix systems, readline is used if available.
```


#docstring
As docstrings começam exatamente na palavra que sucede o comando #def 
e com isso podemos deixar explicado o que nossa função faz exatamente, e podemos utilziar o comando #InteractiveHELP nela, por exemplo: 


```python
CÓDIGO

from time import sleep
def contador(i, f, p):
    """
    faz uma contagem e exibe na tela
    i = inicio da contagem
    f = fim da contagem
    p = passo da contagem
    return = sem retorno
    """ 
    for c in range(i, f, p):
        print(f"{c}", end=" ", flush=True)
        sleep(0.5)
    print("Fim!")
contador(-50, 10, 5)

help(contador)
```
Definimos as #docstrings com """ abrindo e mais """ para fechar
```python
output

-50 -45 -40 -35 -30 -25 -20 -15 -10 -5 0 5 Fim!
Help on function contador in module __main__:

contador(i, f, p)
    faz uma contagem e exibe na tela
    i = inicio da contagem
    f = fim da contagem
    p = passo da contagem
    return = sem retorno
```

Parâmetros opcionais
vamos pensar em uma funcionalidade que some três números:

```python
def somar(a, b, c=0):
	s = a + b + c
	print(f"A soma vale {s}")

somar(3, 2, 5)
somar(8, 4)

```

no caso acima, irá dar um erro pela falta de parâmetros na segunda invocação da função, nesses casos utilizamos os parâmetros opcionais, como no exemplo abaixo

```python
CÓDIGO
def somar(a=0, b=0, c=0):
	"""
    -> Faz a soma de três valores e mostra o resultado na tela
    :param a: o primeiro valor
    :param b: o segundo valor
    :param c: o terceiro valor  
    Função criada por matheus avolio sedel
    """
	s = a + b + c
	print(f"A soma vale {s}")
somar(float(input("Primeiro número: ")), float(input("Segundo número: ")))

OUTPUT

Primeiro número: 135
Segundo número: 65
A soma vale 200.0
```
Se "a" ou "b" ou "c" não receber nenhum parâmetro, o parâmetro deles será 0 e todo conteúdo dentro das três aspas duplas é a docstring


# #EscopoDeVariáveis

```python
def teste():
    print(f"Na função teste, n vale {n}")

n = 2
print(f"No programa principal, n vale {n}")
teste()

OUTPUT

No programa principal, n vale 2
Na função teste, n vale 2
```
Nesse exemplo, mesmo a variável n ter sido declarado depois da criação da função, ela ainda é utilizável, e é chamada de #EscopoGlobal

```python
CÓDIGO
def teste():
    x = 8
    print(f"Na função teste, n vale {n}")
    print(f"Na função teste, x vale{x}")

n = 2
print(f"No programa principal, n vale {n}")
print(f"No programa principal, a variável x vale {x}")
teste()

OUTPUT

No programa principal, n vale 2
Traceback (most recent call last):
  File "d:\Python\Treinos\treino.py", line 7, in <module> 
    print(f"No programa principal, a variável x vale {x}")
                                                      ^   
NameError: name 'x' is not defined
```
Ja nesse exemplo ocorreu um erro, isso porque a variável x só existe dentro da função teste e é chamado de #EscopoLocal

```python
CÓDIGO

def teste(b):
	b+=4   ### ESCOPO LOCAL
    c=2    ### ESCOPO LOCAL
    print(f"A dentro vale {a}")
    print(f"B dentro vale {b}")
    print(f"C dentro vale {c}")

a = 5  ### ESCOPO GLOBAL
teste(a)
print(f"A fora vale {a}")

OUTPUT

A dentro vale 5
B dentro vale 9
C dentro vale 2
A fora vale 5 
```
no exemplo acima, as variáveis b e c,  são #EscopoLocal pois só existem dentro da função
ja a variável a é um #EscopoGlobal pois existe fora da função 

```python
CÓDIGO
def teste(b):
    a=8
    b+=4
    c=2
    print(f"A dentro vale {a}")
    print(f"B dentro vale {b}")
    print(f"C dentro vale {c}")

a = 5
teste(a)
print(f"A fora vale {a}")

OUTPUT

A dentro vale 8
B dentro vale 9
C dentro vale 2
A fora vale 5
```
Ja nesse exemplo, foi criada uma váriavel A no escopo local, então quando é impresso "A dentro vale" é impresso o resultado de no escopo local,

E quando quisermos que a variável global valha tanto para o escopo local e para o global, podemos untilizar o #global, por exemplo:
```python
CÓDIGO 

def teste(b):
    global a
    a +=8
    b+=4
    c=2
    print(f"A dentro vale {a}")
    print(f"B dentro vale {b}")
    print(f"C dentro vale {c}")
a = 5
teste(a)
print(f"A fora vale {a}")

OUTPUT

A dentro vale 13
B dentro vale 9
C dentro vale 2
A fora vale 13
```

No exemplo acima, não é criada uma nova variável localmente, e sim é pego essa variável do escopo global para poder utilizar ela dentro da função


As funções podem retornar ou não valores, para retornarmos valores, utilizamos o #return
Exemplo:

```python
CÓDIGO

def somar(a=0, b=0, c=0):
    s = a + b + c
    return s
resp = somar(int(input("Insira um número: ")), int(input("Insira um número: ")))
print(f"A soma vale {resp}")
---------------------------------------------------------------------------------

OUTPUT

Insira um número: 10
Insira um número: 50
A soma vale 60
```
Definimos a função somar com os parâmetros a, b e c. definimos a variável local como s = a + b + c e o #return irá retornar o resultado da soma, e pra isso, após o escopo da função, atribuimos a chamada da função somar a uma variável, e por fim imprimos o resultado utilizando a variável atribuida a chamada da função.


Também podemos atribuir várias variáveis para utilizar o return da função somar, como por exemplo:

```python
CÓDIGO

def somar(a=0, b=0, c=0):
    s = a + b + c
    return s
resp = somar(int(input("Insira um número: ")), int(input("Insira um número: ")))
resp2 = somar(int(input("Insira um número: ")), int(input("Insira um número: ")))
print(f"Os resultados das somas foram {resp}, {resp2}")

OUTPUT

Insira um número: 125
Insira um número: 225
Insira um número: 180
Insira um número: 280
Os resultados das somas foram 350, 460
```


```python
CÓDIGO
def fatorial(num=1):
    f = 1
    for c in range(num, 0, -1):
        f*=c
    return f

n = int(input("Digite um número: "))
print(f"O fatorial de {n} é igual a {fatorial(n)}")

OUTPUT
Digite um número: 5
O fatorial de 5 é igual a 120


ANÁLISE

### Função `fatorial()`
`def fatorial(num=1):
	f = 1     
	for c in range(num, 0, -1):         
		f *= c     
	return f`

- **`def fatorial(num=1):`**: Define a função `fatorial`, que recebe um parâmetro chamado `num` com valor padrão 1. Isso significa que, se a função for chamada sem argumentos, `num` será igual a 1.
- **`f = 1`**: Inicializa a variável `f` com o valor 1. Esta variável será usada para armazenar o resultado do fatorial.
- **`for c in range(num, 0, -1):`**: Um loop `for` que itera de `num` até 1 (incluindo 1), decrementando 1 em cada iteração. O `range(num, 0, -1)` cria uma sequência que começa em `num`, vai até 1 (excluindo 0), e decrementa em 1 a cada passo.
    - **`f *= c`**: Em cada iteração, a variável `f` é multiplicada pelo valor atual de `c`. Este é o cálculo do fatorial: o produto de todos os números de `num` até 1.
- **`return f`**: Retorna o valor de `f`, que agora contém o fatorial de `num`.



### Entrada do Usuário e Cálculo do Fatorial
`n = int(input("Digite um número: "))`

- **`n = int(input("Digite um número: "))`**: Pede ao usuário para digitar um número. A função `input` captura a entrada do usuário como uma string, e `int` converte essa string em um número inteiro, que é armazenado na variável `n`.


### Exibição do Resultado
`print(f"O fatorial de {n} é igual a {fatorial(n)}")`

- **`print(f"O fatorial de {n} é igual a {fatorial(n)}")`**: Exibe na tela o texto `"O fatorial de {n} é igual a {fatorial(n)}"`. Aqui, `n` é o número que o usuário digitou, e `fatorial(n)` é o resultado da função `fatorial`, que calcula o fatorial de `n`. A sintaxe `f""` é usada para formatação de strings (f-strings), permitindo a inclusão direta de variáveis e expressões dentro da string.

### Resumo
O código define uma função `fatorial` que calcula o fatorial de um número inteiro dado (`num`). O fatorial é o produto de todos os números inteiros positivos de 1 até `num`. Após definir a função, o código solicita ao usuário que insira um número, calcula o fatorial desse número usando a função `fatorial`, e exibe o resultado na tela.

Por exemplo, se o usuário digitar `5`, o programa calculará 5!=5×4×3×2×1=1205! = 5 \times 4 \times 3 \times 2 \times 1 = 1205!=5×4×3×2×1=120 e exibirá `"O fatorial de 5 é igual a 120"`.

```

Podemos utilizar a função return para retornar booleanos, strings, int, floats, dicionários, listas, tuplas.
Por exemplo:
```python
CÓDIGO
def par_impar(num):
    if num % 2 == 0:
        return "Par"
    else:
        return "Ímpar"
n1 = int(input("Digite um número: "))
n2 = int(input("Digite um número: "))
print(f"O número {n1} é {par_impar(n1)}")
print(f"O número {n2} é {par_impar(n2)}")

OUTPUT
Digite um número: 20
Digite um número: 19
O número 20 é Par  
O número 19 é Ímpar

```
