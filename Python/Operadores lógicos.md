#Operadores #lógicos (And,Not,or, in e not in)


# #and → se ambos os operandos forem verdadeiros, a condição é verdadeira, por exemplo, (True and True) é True,

# #or → se algum dos operandos for verdadeiro, a condição é verdadeira, por exemplo, (True or False) é True,

# #not → retorna falso se o resultado for verdadeiro, e retorna verdadeiro se o resultado for falso, por exemplo, not True é False.

  

#And - Realiza duas comparações ou mais. Por exemplo:

# var1 = 5

# var2 = 5

# var3 = 8

# var1 == var2 and var2 < var3

  

#OR - Pergunta se alguma das condições é verdadeira. Por exemplo:

var1 or var2

Pergunta qual das duas é verdadeira

  

#Not-  Não precisa de duas expressões, apenas de uma. Ele é um inversor, ele inverte o resultado da expressão. Por exemplo:

# var1 = 5

# var2 = 10

# if var2 > var1:

    o resultado sera verdadeiro

# porém, ao usar o not, inverte esse resultado

# if not var2 > var1:

    o resultado sera falso

  

#In -

# nome = "matheus avolio"

# if "matheus" in nome:

    #print("existe")

# else:

    #print("nao existe")

se matheus esta na variavel nome, execute o print

  

#Not in - Inverte a expressão

nome = "matheus avolio"

# if "matheus" not in nome:

    #print("Existe")

else:

    #print("nao existe")

  

# se o texto que esta dentro das aspas não estiver dentro da var (nome) retorna verdadeiro( no caso é a condição que esta dentro de if)

e se o que estiver dentro da var(nome) existir retorna falso( condição else)

  

# Este é o operador xor (como em exclusivo ou), e é denotado como ^ (acento circunflexo).

  

# Aqui estão todos eles:

  

# & (e comercial) - conjunção bitwise;

# | (barra) - disjunção bitwise;

# ~ (til) - negação bitwise;

# ^ (acento circunflexo) - bitwise exclusive ou (xor).

  

#3.3.1.6

# 1. O Python suporta os seguintes operadores lógicos:

  

# #and → se ambos os operandos forem verdadeiros, a condição é verdadeira, por exemplo, (True and True) é True,

# #or → se algum dos operandos for verdadeiro, a condição é verdadeira, por exemplo, (True or False) é True,

# #not → retorna falso se o resultado for verdadeiro, e retorna verdadeiro se o resultado for falso, por exemplo, not True é False.

# 2. Pode utilizar operadores bitwise para manipular bits únicos de dados. Os seguintes dados de amostra:

  

# x = 15, que é 0000 1111 em binário,

# y = 16, que é 0001 0000 em binário.

# serão utilizados para ilustrar o significado de operadores bitwise em Python. Analise os exemplos em baixo:

  

# & faz um bitwise and, por exemplo, x & y = 0, que é 0000 0000 em binário,

# | faz um bitwise ou, por exemplo, x | y = 31, que é 0001 1111 em binário,

# ˜  faz um bitwise não, por exemplo, ˜ x = 240*, que é 1111 0000 em binário,

# ^ faz um bitwise xor, por exemplo, x ^ y = 31, que é 0001 1111 em binário,

# >> faz um bitwise right shift, por exemplo, y >> 1 = 8, que é 0000 1000 em binário,

# << faz um bitwise left shift, por exemplo, y << 3 = , que é 1000 0000 em binário,

  

# * -16 (decimal do complemento assinado de 2)