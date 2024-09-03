
#OperadoresLógicos (And,Not,or, in e not in)


#And - Realiza duas comparações ou mais. Por exemplo:

# var1 = 5

# var2 = 5

# var3 = 8

# var1 == var2 and var2 < var3

# Por exemplo:
entrada = str(input("Insira uma palavra!"))
if entrada == "matheus" and "lucas"
	print("matheus e lucas")
else:
	print("não é matheus e lucas")

pedi ao usúario que inserisse uma palavra, após isso fiz uma comparação
se(if) entrada(var) for igual a "matheus" e(and) "lucas", imprima "matheus e lucas", senao(else) imprima não é matheus e lucas.

and é usado para checar mais de uma condição

# #OR- Pergunta se alguma das condições é verdadeira. Por exemplo:

entrada = str(input("[E]ntrar [S]air: "))
senha_digitada = int(input("Senha: "))
senha_permitida = "123456"

if entrada == "E" or entrada == "e" and senha_digitada:
    print("Entrar")

else:
    print("sair")

# Qualquer condição que for avaliada como verdadeira, avalia a condição inteira como verdadeira


Var1 or var2
Pergunta qual das duas é verdadeira



# NOT -  Não precisa de duas expressões, apenas de uma. Ele é um inversor, ele inverte o resultado da expressão. Por exemplo:
var1 = 5
var2 = 10
if var2 > var1:

 o resultado sera verdadeiro

# porém, ao usar o #NOT, inverte esse resultado

# if not var2 > var1:

   o resultado sera falso

  


# IN
# nome = "matheus avolio"

 if "matheus" in nome:
    print("existe")
else:
    print("nao existe")

se matheus esta na variavel nome, execute o print

  

Not in - Inverte a expressão

nome = "matheus avolio"
 if "matheus" not in nome:
	print("Existe")
else:
    print("nao existe")

# se o texto que esta dentro das aspas não estiver dentro da var (nome) retorna verdadeiro( no caso é a condição que esta dentro de if)

e se o que estiver dentro da var(nome) existir retorna falso( condição else)


