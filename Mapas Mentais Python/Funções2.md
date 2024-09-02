
### 1. Definindo uma Função

Para criar uma função em Python, utilizamos a palavra-chave `def`, seguida pelo nome da função e parênteses. Dentro desses parênteses, podemos colocar parâmetros (dados que a função vai receber). O código que define o que a função faz é escrito logo abaixo, com um recuo (indentação).

**Exemplo de Função Simples:**


```python
CÓDIGO
`def cabecalho():  # Define uma função chamada "cabecalho"     
	print("-" * 30)  # Imprime uma linha com 30 traços     
	print("SISTEMA DE ALUNOS")  # Imprime o título "SISTEMA DE ALUNOS"     
	print("-" * 30)  # Imprime outra linha com 30 traços     
	print("CADASTRO DE FUNCIONÁRIOS")  # Imprime "CADASTRO DEFUNCIONÁRIOS
	print("-" * 30)  # Imprime mais uma linha com 30 traços     
	print("ERRO NO SISTEMA")  # Imprime "ERRO NO SISTEMA"     
	print("-" * 30)  # Finaliza com uma última linha de 30 traços  
cabecalho()  # Chama (executa) a função "cabecalho"`
```

```python
OUTPUT
`------------------------------ 
SISTEMA DE ALUNOS
------------------------------ 
CADASTRO DE FUNCIONÁRIOS
------------------------------ 
ERRO NO SISTEMA
------------------------------`
```

Neste exemplo, criamos uma função chamada `cabecalho` que imprime um cabeçalho simples. Quando chamamos a função usando `cabecalho()`, todo o código dentro dela é executado.

### 2. Usando Parâmetros em Funções

Parâmetros são como variáveis que você pode passar para a função, permitindo que ela faça operações específicas com diferentes valores.

**Exemplo com Parâmetro:**


```python
`def mensagem(msg):  # Define uma função chamada "mensagem" que aceita um parâmetro "msg"     
	print("-" * 20)  # Imprime uma linha com 20 traços     
	print(msg)  # Imprime a mensagem passada como parâmetro     
	print("-" * 20)  # Imprime outra linha com 20 traços  
mensagem("Bem-vindo ao Python!")  # Chama a função "mensagem" passando uma string como argumento`
```

```python
output
`-------------------- 
Bem-vindo ao Python!
--------------------`
```

Neste exemplo, a função `mensagem` recebe um texto (string) como parâmetro e o exibe entre duas linhas de traços.

### 3. Repetindo a Função com Diferentes Valores

Podemos chamar a mesma função várias vezes com diferentes argumentos.

**Exemplo com Repetição:**



```python
def titulo(txt):  # Define uma função chamada "titulo" que aceita um parâmetro "txt"     
	print("-" * 30)  # Imprime uma linha com 30 traços     
	print(txt)  # Imprime o texto passado como parâmetro     
	print("-" * 30)  # Imprime outra linha com 30 traços  
titulo("   Curso em Vídeo   ")  # Chama a função "titulo" passando "Curso em Vídeo" 
titulo("   Matheus Avolio   ")  # Chama a função novamente com "Matheus Avolio" 
titulo("   Hello World!     ")  # E mais uma vez com "Hello World!"`
```

```python
OUTPUT

`------------------------------    Curso em Vídeo    ------------------------------ ------------------------------  Matheus Avolio    ------------------------------ ------------------------------  Hello World!      ------------------------------`
```

Aqui, a função `titulo` é reutilizada com diferentes textos. A função formata esses textos com as mesmas linhas de traços em volta.

### 4. Calculando a Média de um Aluno

Funções também podem fazer cálculos e operações mais complexas.

**Exemplo de Função para Calcular Média:**


```python
`def media(a, b):  # Define uma função chamada "media" que aceita dois parâmetros "a" e "b"     
s = (a + b) / 2  # Calcula a média dos dois valores     
print(f"A média do aluno é {s}")  # Exibe a média calculada  
media(8, 7.5)  # Chama a função "media" com notas 8 e 7.5`
```

```python
OUTPUT
`A média do aluno é 7.75`
```
Aqui, passamos duas notas para a função `media`, que calcula e exibe a média delas.

### 5. Criando uma Calculadora de Tabuada

Podemos criar funções que interagem com o usuário e executam operações em loop.

**Exemplo de Calculadora de Tabuada:**

```python

`def erro():  # Define uma função chamada "erro"     
	print("Erro! Insira apenas [S] para sim e [N] para não")  # Exibe uma mensagem de erro  
def calculadora(num):  # Define uma função chamada "calculadora" que aceita um parâmetro "num"     
	for c in range(1, 11):  # Cria um loop de 1 a 10         
		print(f"{num} x {c} = {num * c}")  # Exibe a multiplicação de "num" por "c" 
 while True:  # Cria um loop infinito     
	 calculadora(int(input("Insira o número da tabuada que você deseja: ")))  # Pede ao usuário um número e exibe a tabuada     
	 while True:  # Outro loop infinito para continuar ou sair         
	 continuar = input("Quer continuar? [S/N] ").strip().lower()[0]  # Pede ao usuário para continuar ou não         
	 if continuar in "sn":  # Verifica se a resposta é válida             
		 break  # Sai do loop se for         
	 erro()  # Exibe mensagem de erro se a resposta for inválida     
	 if continuar == "n":  # Se o usuário escolher não continuar         
		print("Volte sempre!")  # Exibe mensagem de despedida         break  # Sai do loop principal`
```

```python
`Insira o número da tabuada que você deseja: 5 
5 x 1 = 5 
5 x 2 = 10 ... 
5 x 10 = 50 
Quer continuar? [S/N] s 
Insira o número da tabuada que você deseja: 3 
3 x 1 = 3 ... 
3 x 10 = 30 
Quer continuar? [S/N] n 
Volte sempre!`
```

Este exemplo cria uma pequena "calculadora" que exibe a tabuada de um número escolhido pelo usuário e permite que ele continue ou saia do programa.

### 6. Funções com Número Variável de Parâmetros

Python permite criar funções que aceitam um número indefinido de argumentos.

**Exemplo de Função com Vários Parâmetros:**

```python
`def contador(*num):  # Define uma função chamada "contador" que aceita múltiplos parâmetros     
	print(num)  # Exibe os valores passados como uma tupla  
contador(2, 1, 0)  # Chama a função com três argumentos 
contador(8, 0)  # Chama a função com dois argumentos 
contador(4, 4, 7, 6, 2)  # Chama a função com cinco argumentos`
```

```python
`(2, 1, 0) (8, 0) (4, 4, 7, 6, 2)`
```
`
A função `contador` pode receber qualquer quantidade de números e os exibe como uma tupla.

### 7. Iterando Sobre os Parâmetros

Você pode iterar sobre os parâmetros recebidos e realizar operações com eles.

**Exemplo de Iteração:**

```python
`def contador(*num):  # Define uma função que aceita múltiplos parâmetros  
	for v in num:  # Itera sobre cada valor passado         
	print(v)  # Exibe cada valor  
contador(2, 1, 0)  # Chama a função com três valores 
contador(8, 0)  # Chama a função com dois valores 
contador(4, 4, 7, 6, 2)  # Chama a função com cinco valores`
```

```python
OUTPUT
`2
 1
 0 
 8 
 0 
 4 
 4 
 7 
 6 
 2`
```

Agora, cada valor é exibido separadamente.

### 8. Adicionando Funções Dentro de Outras Funções

Podemos criar funções auxiliares para reutilizar código dentro de outras funções.

```python
`def linha():  # Define uma função chamada "linha"     
	print("-" * 30)  # Imprime uma linha de 30 traços  


def contador(*num):  # Define a função "contador"     
	linha()  # Chama a função "linha"     
	for v in num:  # Itera sobre os valores passados        
			print(v)  # Exibe cada valor     
linha()  # Chama a função "linha" novamente  
contador(2, 1, 0)  # Chama a função "contador" 
contador(8, 0)  # Chama a função novamente 
contador(4, 4, 7, 6, 2)  # E mais uma vez`

```

```python
OUTPUT
------------------------------
------------------------------
2
1
0
------------------------------
8
0
------------------------------
4
4
7
6
2
```

A função `linha` é chamada dentro da função `contador` para separar visualmente as listas de números.

---

Esses exemplos abordam desde o básico até conceitos mais avançados de funções em Python. Cada exemplo introduz uma nova ideia ou aprimora as anteriores, fornecendo uma base sólida para entender e aplicar funções em diferentes contextos.


### 1. Usando `return` para Devolver um Valor

Quando você define uma função, pode usar o `return` para enviar de volta o resultado de algum cálculo ou operação.

**Exemplo Simples:**



```python
`def soma(a, b):  # Define uma função chamada "soma" que aceita dois parâmetros "a" e "b"     
	resultado = a + b  # Calcula a soma de "a" e "b"     
	return resultado  # Retorna o resultado da soma  
# Chamando a função e armazenando o valor retornado 
resultado = soma(5, 3)   
print(f"O resultado da soma é {resultado}")  # Exibe o valor retornado`
```


```python
OUTPUT
`O resultado da soma é 8`
```

Neste exemplo, a função `soma` recebe dois números, calcula a soma deles e usa `return` para enviar o resultado de volta ao ponto onde a função foi chamada. O valor retornado é então armazenado na variável `resultado` e pode ser usado em outras partes do código.

### 2. Terminar a Função Antecipadamente

O `return` também pode ser usado para encerrar a execução de uma função antes de chegar ao final dela.


```python
`def divide(a, b):     
	if b == 0:  # Verifica se o divisor é zero         
		return "Erro! Divisão por zero."  # Retorna uma mensagem de erro se for 
	return a / b  # Caso contrário, retorna o resultado da divisão  
# Testando a função 
resultado1 = divide(10, 2)   
resultado2 = divide(10, 0)    
print(resultado1)  # Exibe o resultado da divisão 
print(resultado2)  # Exibe a mensagem de erro`
```


```python
OUTPUT
`5.0 
Erro! Divisão por zero.`
```

Neste exemplo, a função `divide` usa `return` para encerrar a execução e retornar uma mensagem de erro se o divisor for zero. Caso contrário, a função continua e retorna o resultado da divisão.

### 3. Retornando Múltiplos Valores

Em Python, uma função pode retornar múltiplos valores separados por vírgula. Na prática, isso faz com que a função retorne uma tupla (um tipo de dado que pode armazenar vários valores).

**Exemplo de Retorno Múltiplo:**

```python
`def operacoes(a, b):     
	soma = a + b     
	diferenca = a - b     
	produto = a * b     
	return soma, diferenca, produto  # Retorna três valores: soma, diferença e produto  
	# Desempacotando os valores retornados em variáveis separadas 
s, d, p = operacoes(10, 5)  
print(f"Soma: {s}, Diferença: {d}, Produto: {p}")`
```


```python
OUTPUT
`Soma: 15, Diferença: 5, Produto: 50`
```

Aqui, a função `operacoes` realiza três cálculos e retorna os três resultados. Esses valores são então "desempacotados" em variáveis separadas (`s`, `d`, `p`) quando a função é chamada.

### 4. `return` sem Valor

Você também pode usar `return` sozinho para encerrar uma função sem retornar nenhum valor.

**Exemplo:**

```python
OUTPUT
`def verifica_numero(n):     
	if n % 2 == 0:         
		return  # Encerra a função se o número for par     
	print(f"{n} é ímpar")  # Só executa se o número for ímpar 
verifica_numero(4)  # Não imprime nada, pois 4 é par 
verifica_numero(7)  # Imprime, pois 7 é ímpar`
```

```python
OUTPUT
`7 é ímpar`
```

Neste exemplo, se o número for par, a função é encerrada com `return` e não faz mais nada. Se o número for ímpar, o `print` é executado.

### 5. Funções Sem `return`

Se uma função não tiver um `return` explícito, ela retornará `None` por padrão.

**Exemplo:**


```python

``def saudacao(nome):     
	print(f"Olá, {nome}!")  # A função só imprime uma saudação, sem `return`  
resultado = saudacao("Ana") 
print(f"O retorno da função é {resultado}")``
```

**Saída:**


```python
OUTPUT
`Olá, Ana! O retorno da função é None`
```

Mesmo sem `return`, a função `saudacao` ainda retorna algo, que é o valor especial `None`, indicando a ausência de um retorno específico.

### Resumo

- **`return valor`**: Finaliza a função e retorna `valor` para o chamador.
- **`return` (sozinho)**: Finaliza a função sem retornar nada (equivalente a retornar `None`).
- **Múltiplos `return`**: Você pode ter várias instruções `return` em uma função, mas apenas a primeira que for executada realmente encerra a função.