#LOOP (while-for-range) 3.2.1.1

# (for) loop que percorre sequências repetindo ações para cada elemento

# (while) loop que executa ações enquanto a condição for verdadeira

# (range) cria uma sequência de números a serem executados

  

for x in range(5):

    print(x)

# o (for) é a keyword que inicia o loop, (x) é uma variavel temporária que será modificada de acordo com a execução do loop

# nesse caso, a primeira execução equivale a 0 a segunda execução a 1, a terceira a 2, a quarta a 3 e a quinta a 4, totalizando a repetição 5 vezes

# a keyword (range) cria uma sequência de números, nesse caso é uma seqûencia de 5 números

  

# Usar uma variável counter para sair de um loop

# Veja o snippet abaixo:

  

 counter = 5

 while counter != 0:

     print("Inside the loop.", counter)

     counter -= 1

 print("Outside the loop.", counter)

  
  

# Este código destina-se a imprimir a string "Inside the loop." e o valor armazenado na variável counter durante um determinado loop exatamente cinco vezes.

# Uma vez que a condição não foi atendida (a variável counter atingiu 0)

#  o loop é encerrado, e a mensagem "Outside the loop." bem como o valor armazenado em counter é impresso.

  
  

 LAB 3.2.1.3 (WHILE)

# A sua tarefa é ajudar o mágico a completar o código no editor, de modo a que o código:

# peça ao utilizador para introduzir um número inteiro;

# utilize um loop while ;

# verifique se o número introduzido pelo utilizador é o mesmo que o número escolhido pelo mágico.

# Se o número escolhido pelo utilizador for diferente do número secreto do mágico, o utilizador deve ver a mensagem "Ha ha! You're stuck in my loop!"

# e ser solicitado a introduzir novamente um número. Se o número introduzido pelo utilizador corresponder ao número escolhido pelo mágico,

# o número deve ser impresso no ecrã, e o mágico deve dizer as seguintes palavras: "Well done, muggle! You are free now."

# A propósito, olha para a função print() . A forma como a utilizámos aqui chama-se impressão multi-linha.

# Pode usar aspas triplas para imprimir strings em várias linhas a fim de tornar o texto mais fácil de ler,

# ou criar um desenho especial baseado em texto. Experimente-o.

  

secret_number = 777

usuario = int(input("Digite um número: "))

while usuario != secret_number:

    print("Ha ha! You're stuck in my loop!")

else:

    print("Well done, muggle! You are free now")

print(

"""

+================================+

| Welcome to my game, muggle!    |

| Enter an integer number        |

| and guess what number I've     |

| picked for you.                |

| So, what is the secret number? |

+================================+

""")

  

# atribúo o número 777 a variavel (secret_number), após isso crio uma variavel chamada (usuario) aonde defino qual tipo de informação vai entrar.

# após isso utilizo o (while) para iniciar um loop caso a var(usuario) não for igual(!=) a var(secret_number)

# após isso, se o dado inserido pelo usúario for igual a var(secret_number) será impressa no output a string dentro da keyword print

  

#3.2.1.5 (for)

# O primeiro argumento passado para a função range() diz-nos qual o número inicial da sequência (logo, 2 no output).

# O segundo argumento informa à função onde parar a sequência (a função gera números até ao número indicado pelo segundo argumento, mas não o inclui). Finalmente,

# o terceiro argumento indica a etapa, que na realidade significa a diferença entre cada número na sequência de números gerados pela função.

  

for i in range(2, 8, 3):

    print("The value of i is currently", i)

  

#for é o lopp, (i) é a variavel uma variavel temporária que será modificada de acordo com a execução do loop o numero(2) sera o número em que se iniciara a contagem no output

o numero(8) sera o limite, o loop só vai se repetir até chegar a 8

# e o numero (3) mostra quantas casas pular

# então a contagem começa em 2, só vai até 8 e a cada repetição, tem de ser pulado 3 números

  

LAB 3.2.1.6(for)

# A sua tarefa aqui é muito simples: escreva um programa que utilize um loop for para “contar mississippily” até cinco.

# Tendo contado até cinco, o programa deve imprimir para o ecrã a mensagem final "Ready or not, here I come!"

  

for x in range(1, 6, 1):

    print("mississippily", x)

if x >=5:

    print("Ready or not, here I come!")

  
  

# #break - sai imediatamente do loop, e termina incondicionalmente a operação do loop; o programa começa a executar a instrução mais próxima após o corpo do loop;

# #continue - comporta-se como se o programa tivesse subitamente chegado ao fim do corpo; inicia-se a volta seguinte e a expressão da condição é testada imediatamente.

  

LAB 3.2.1.9(while)

ani = input("Insira o nome de um animal: ")

while ani != "cachorro":

    ani = str(input("Insira o nome de um animal:"))

    continue

while ani == "cachorro":

    print("You've successfully left the loop.")

    break

  

criei uma variavel chamada (ani) para pedir ao usuario que insira um nome de um animal

# enquanto(while) ani(var) não for igual(!=) a cachorro

# vai pedir novamente para o usuario inserir um nome

usei o continue para que o programa continue perguntando infinitamente um nome ao usuario

até ele digitar "cachorro"

se ele digitar "cachorro" o programa exibe uma mensagem(you've successfully left the loop.) e para(break)

  

LAB 3.2.1.10 (comedor de vogais 1.0)

# A sua tarefa aqui é muito especial: tem de conceber um vowel eater (comedor de vogais)! Escreva um programa que use:

  

# um loop for ;

# o conceito de execução condicional (if-elif-else)

# a declaração continue .

# O seu programa deve:

  

# pedir ao utilizador para introduzir uma palavra;

# usar user_word = user_word.upper() para converter a palavra introduzida pelo utilizador em maiúsculas;

# falaremos sobre os chamados métodos de strings e o método upper() muito em breve - não se preocupe;

# usar execução condicional e a declaração continue para “comer” as seguintes vogais A, E, I, O, U da palavra introduzida;

# imprimir as letras não comidas para o ecrã, cada uma delas numa linha separada.

  

user_word = str(input("Insira uma palavra:"))

user_word = user_word.upper()

for letter in user_word:

    if letter == "A":

        continue

    elif letter == "E":

        continue

    elif letter == "I":

        continue

    elif letter == "O":

        continue

    elif letter == "U":

        continue

    else:

        print(letter)

  

user_word é a var, primeiro valor atribuido a ela eu peço para o usuario inserir os dados

após isso, substituo o valor dela por upper() para converter a palavra introduzida pelo usuario em maiúsculas

após isso, começo o loop usando(for) utilizando a var(letter)  como var temporaria e utilizo logo em seguida a var(user_word)

se(if) letter == A o programa vai "comer" essa palavra e continuar, faço isso novamente utilizando elif com as outras vogais

  


LAB 3.2.1.14

blocks = int(input("Enter the number of blocks: "))

height = 0

while blocks > height:

    height = height + 1

    blocks = blocks - height

  

print("The height of the pyramid:", height)

  
  
  

LAB 3.2.1.15

c0 =  int(input("Enter a number: "))

if c0 < 1:

    print("Use a non-negative, non-zero number")

else:

    steps = 0

    while c0 != 1:

        if c0 % 2 == 0:

            c0 = int(c0 / 2)

        else:

            c0 = c0 = 3 * c0 + 1

        print(c0)

        steps += 1

    print("total number of steps: ", steps)

  
  

#3.1.2.16 (1/2)

#1. Existem dois tipos de loops em Python: while e for:

  

o loop #while executa uma declaração ou um conjunto de declarações, desde que uma condição booleana especificada seja verdadeira, por exemplo:

  

# Example 1

while True:

    print("Stuck in an infinite loop.")

  

# Example 2

counter = 5

while counter > 2:

    print(counter)

    counter -= 1

  
  

o loop #for executa um conjunto de declarações várias vezes; é usado para iterar sobre uma sequência

#  (por exemplo, uma lista, um dicionário, um tuple, ou um conjunto - aprenderá sobre eles em breve) ou outros objetos que são iteráveis (por exemplo, strings). Pode utilizar o loop for para iterar sobre uma sequência de números usando a função range . Veja os exemplos em baixo:

  

# Example 1

word = "Python"

for letter in word:

    print(letter, end="*")

  

# Example 2

for i in range(1, 10):

    if i % 2 == 0:

        print(i)

  
  

#2. Pode utilizar as declarações break e continue para alterar o fluxo de um loop:

  

Utilize #break para sair de um loop, por exemplo:

  

text = "OpenEDG Python Institute"

for letter in text:

    if letter == "P":

        break

    print(letter, end="")

  
  

Utilize #continue para ignorar a iteração atual e continuar com a próxima iteração, por exemplo:

  

text = "pyxpyxpyx"

for letter in text:

    if letter == "x":

        continue

    print(letter, end="")

  

#3. Os loops while e for também podem ter uma cláusula else em Python. A cláusula else executa-se após o loop terminar a sua execução, desde que não tenha sido terminado por break, por exemplo.:

  

n = 0

  

while n != 3:

    print(n)

    n += 1

else:

    print(n, "else")

  

print()

  

for i in range(0, 3):

    print(i)

else:

    print(i, "else")

  
  

#4. O objeto da exceção range() gera uma sequência de números. Aceita números inteiros e devolve objetos de range.

#  A sintaxe de #range parece como se segue: range(start, stop, step), onde:

  

start é um parâmetro opcional que especifica o número inicial da sequência (0 por padrão)

stop é um parâmetro opcional que especifica o fim da sequência gerada (não está incluído),

e step é um parâmetro opcional que especifica a diferença entre os números na sequência (1 por padrão.)

Código de exemplo:

  

for i in range(3):

    print(i, end=" ")  # Outputs: 0 1 2

  

for i in range(6, 1, -2):

    print(i, end=" ")  # Outputs: 6, 4, 2

  
  

#3.2.1.17 (2/2)

Principais takeaways: continuação

Exercício 1

  

Crie um loop for que conta de 0 a 10, e imprime os números ímpares no ecrã. Use o esqueleto abaixo:

  

for i in range(1, 11):

    # Line of code.

        # Line of code.

  
  

Verifique

Solução de amostra:

for i in range(0, 11):

    if i % 2 != 0:

        print(i)

  
  

Exercício 2

  

Crie um loop while que conta de 0 a 10, e imprime os números ímpares no ecrã. Use o esqueleto abaixo:

  

x = 1

while x < 11:

    # Line of code.

        # Line of code.

    # Line of code.

  
  

Verifique

Solução de amostra:

x = 1

while x < 11:

    if x % 2 != 0:

        print(x)

    x += 1

  
  

Exercício 3

  

Crie um programa com um loop for e uma declaração break . O programa deve iterar sobre os caracteres de um endereço de e-mail,

# sair do loop quando chegar ao símbolo @ , e imprimir a parte antes de @ numa linha. Use o esqueleto abaixo:

  

for ch in "john.smith@pythoninstitute.org":

    if ch == "@":

        # Line of code.

    # Line of code.

  
  

Verifique

Solução de amostra:

for ch in "john.smith@pythoninstitute.org":

    if ch == "@":

        break

    print(ch, end="")

  
  

Exercício 4

  

Crie um programa com um loop for e uma declaração continue . O programa deve iterar sobre uma string de dígitos,

substituir cada 0 com xe imprimir a string modificada no ecrã. Use o esqueleto abaixo:

  

for digit in "0165031806510":

    if digit == "0":

        # Line of code.

        # Line of code.

    # Line of code.

  
  

Verifique

Solução de amostra:

for digit in "0165031806510":

    if digit == "0":

        print("x", end="")

        continue

    print(digit, end="")

  
  

Exercício 5

  

Qual é o output do seguinte código?

  

n = 3

  

while n > 0:

    print(n + 1)

    n -= 1

else:

    print(n)

  
  

Verifique

4

3

2

0

  

Exercício 6

  

Qual é o output do seguinte código?

  

n = range(4)

  

for num in n:

    print(num - 1)

else:

    print(num)

  
  

Verifique

-1

0

1

2

3

Exercício 7

  

Qual é o output do seguinte código?

  

for i in range(0, 6, 3):

    print(i)

  
  

Verifique

0

3