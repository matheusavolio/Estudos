#funções

# Como se faz tal função?

  

# É preciso defini-la. A palavra definir é significativa aqui.

  

# Este é o aspeto da definição mais simples da função:

  

def function_name():

    function_body

  

# Começa sempre com a keyword def ( para definir)

# a seguir a def vai o nome da função (as regras para nomear funções são exatamente as mesmas que para nomear variáveis)

# após o nome da função, há um lugar para um par de parêntesis (não contêm nada aqui, mas isso irá mudar em breve)

# a linha tem de ser terminada com dois pontos;

# a linha imediatamente a seguir a def começa o corpo da função - um par (pelo menos um) de instruções necessariamente nested,

# que serão executadas sempre que a função for invocada; nota: a função termina onde termina o nesting, por isso é preciso ter cuidado.

  

Estamos prontos para definir a nossa função de prompting. Vamos nomeá-la message - aqui está:

  

def message():

    print("Enter a value: ")

  
  

A função é extremamente simples, mas totalmente utilizável. Demos-lhe o nome message, mas pode rotulá-la a seu gosto. Vamos usá-la.

O nosso código contém agora a definição da função:

  

def message():

    print("Enter a value: ")

  

print("We start here.")

print("We end here.")

  
  

Nota: não utilizamos de todo a função - não há nenhuma invocação dentro do código.

  

Quando a executa, vê o seguinte output:

  

We start here.

We end here.

output

  
  

# Isto significa que o Python lê as definições da função e lembra-se delas, mas não as lança sem a sua permissão.

# Modificámos o código agora - inserimos a invocação da função entre as mensagens de início e fim:

  

def message():

    print("Enter a value: ")

  

print("We start here.")

message()

print("We end here.")

  

# O output parece diferente agora:

  

We start here.

Enter a value:

We end here.

  

# 4.1.1.5

# quando se invoca uma função, o Python lembra-se do local onde aconteceu e salta para a função invocada;

# o corpo da função é então executado;

# chegar ao fim da função força o Python a regressar ao local diretamente após o ponto de invocação.

  

# 1. Uma função é um bloco de código que executa uma tarefa específica quando a função é chamada (invocada). Pode utilizar funções para tornar o seu código reutilizável, mais bem organizado e mais legível. As funções podem ter parâmetros e valores de retorno.

  

# 2. Existem pelo menos quatro tipos básicos de funções em Python:

# funções incorporadas que são parte integrante do Python (tais como a função print() ).

#  Pode ver uma lista completa de funções Python incorporadas em https://docs.python.org/3/library/functions.html.

# as que vêm de módulos pré-instalados (aprenderá sobre eles no curso Python Essentials 2)

# funções definidas pelo utilizador que são escritas por utilizadores para utilizadores -

# pode escrever as suas próprias funções e utilizá-las livremente no seu código,

# as funções lambda (aprenderá sobre elas no curso Python Essentials 2.)

  

# 3. Pode definir a sua própria função usando a keyword def e a seguinte sintaxe:

  

def your_function(optional parameters):

    the body of the function

  

Pode definir uma função que não aceita quaisquer argumentos, por exemplo:

  

def message():    defining a function

    print("Hello")    # body of the function

  

message()     calling the function

  
  

Pode definir uma função que também aceita argumentos, tal como a função de um parámetro abaixo:

  

def hello(name):     defining a function

    print("Hello,", name)    # body of the function

  
  

name = input("Enter your name: ")

  

hello(name)    # calling the function

  
  

#4.2.1.1

# Todo o potencial da função é revelado quando esta pode ser equipada com uma interface capaz de aceitar dados fornecidos pelo invocador. Tais dados podem modificar o comportamento da função, tornando-a mais flexível e adaptável às condições em mudança.

  

# Um parâmetro é na verdade uma variável, mas há dois fatores importantes que tornam os parâmetros diferentes e especiais:

  

# os parâmetros existem apenas dentro das funções em que foram definidos,

# e o único lugar onde o parâmetro pode ser definido é um espaço entre um par de parêntesis na declaração def ;

# atribuir um valor ao parâmetro é feito no momento da invocação da função, especificando o argumento correspondente.

  

def function(parameter):

  
# Não se esqueça:

# os parâmetros vivem dentro de funções (este é o seu ambiente natural)

# os argumentos existem fora de funções, e são portadores de valores passados para parâmetros correspondentes.

  
  

Temos de reconstruir a declaração def - é assim que se parece agora:

  

def message(number):
  
  

A definição especifica que a nossa função opera apenas num parâmetro chamado number.

#  Pode utilizá-lo como uma variável comum, mas apenas dentro da função -

#  ele não é visível em qualquer outro lugar.

Vamos agora melhorar o corpo da função:

  

def message(number):

    print("Enter a number:", number)

  
  

# Fizemos uso do parâmetro. Nota: não atribuímos o parâmetro com qualquer valor. Está correto?

# Sim, está.

# Um valor para o parâmetro chegará a partir do ambiente da função.

# Lembre-se: especificar um ou mais parâmetros na definição de uma função também é um requisito, e tem de o cumprir durante a invocação.

# Deve fornecer tantos argumentos quantos os parâmetros definidos.

# Não o fazer causará um erro.

  

#4.2.1.2

def message(number):

    print("Enter a number:", number)

  

message(1)

  
  

# Além disso, comporta-se melhor. O código irá produzir o seguinte output:

  

Enter a number: 1

output

  
  

# Vê como funciona? O valor do argumento utilizado durante a invocação (1) foi passado para a função,

# definindo o valor inicial do parâmetro chamado number.

  

primeiro ex

def message(number):

  

segundo ex

def message(number):

    print("Enter a number:", number)

  

terceiro ex

def message(number):

    print("Enter a number:", number)

  

message(1)

  
  

# É válido, e possível, ter uma variável com o mesmo nome que o parâmetro de uma função.

# O snippet ilustra o fenómeno:

  

def message(number):

    print("Enter a number:", number)

  

number = 1234

message(1)

print(number)

  
  

# Uma situação como esta ativa um mecanismo chamado sombreamento:

# parâmetro x sombreia qualquer variável do mesmo nome, mas...

# ... apenas dentro da função que define o parâmetro.

# O parâmetro chamado number é uma entidade completamente diferente da variável chamada number.

# Isto significa que o snippet acima irá produzir o seguinte output:

Enter a number: 1

1234

  

# Uma função pode ter tantos parâmetros quantos quiser, mas quanto mais parâmetros tiver, mais difícil é memorizar os seus papéis e propósitos.

# Funções como o conceito de caixa negra

# Vamos modificar a função - tem dois parâmetros agora:

  

primeiro ex

def message(what, number):

    print("Enter", what, "number", number)

  

# Isto também significa que invocar a função irá requerer dois argumentos.

# O primeiro parâmetro novo destina-se a levar o nome do valor desejado.

# Aqui está:

  

segundo ex

def message(what, number):

    print("Enter", what, "number", number)

  

message("telephone", 11)

message("price", 5)

message("number", "number")

  

# Esta é o output que está prestes a ver:

  

Enter telephone number 11

Enter price number 5

Enter number number number

output

  

# Execute o código, modifique-o, adicione mais parâmetros e veja como isso afeta o output.

  

# Uma técnica que atribui o iésimo (primeiro, segundo, e assim por diante) argumento ao iésimo (primeiro, segundo, e assim por diante)

#  parâmetro de função é chamada passagem de parâmetro posicional,

#  enquanto os argumentos passados desta forma são denominados argumentos posicionais.

  

# Já o usou, mas o Python pode oferecer muito mais. Vamos agora falar-lhe sobre isso.

  

def my_function(a, b, c):

    print(a, b, c)

  

my_function(1, 2, 3)

  

Nota: a passagem de parâmetros posicionais é intuitivamente utilizada pelas pessoas em muitas ocasiões sociais.

# Por exemplo, pode ser geralmente aceite que quando nos apresentamos mencionemos o(s) nosso(s) nome(s) próprio(s) antes do nosso apelido,

#  por exemplo, "O meu nome é Miguel Matos".

  

Vamos implementar esse costume social em Python. A seguinte função será responsável pela introdução de alguém:

  

def introduction(first_name, last_name):

    print("Hello, my name is", first_name, last_name)

  

introduction("Luke", "Skywalker")

introduction("Jesse", "Quick")

introduction("Clark", "Kent")

  
  
  

Agora imagine que a mesma função está a ser utilizada na Hungria. Nesse caso, o código ficaria assim:

def introduction(first_name, last_name):

    print("Hello, my name is", first_name, last_name)

  

introduction("Skywalker", "Luke")

introduction("Quick", "Jesse")

introduction("Kent", "Clark")

  
  

# O output terá um aspeto diferente. Consegue adivinhá-lo?

# Execute o código para ver se também estava certo aqui. Está surpreendido?

# Pode tornar a função mais independente da cultura?

  

#4.2.1.5

# O Python oferece outra convenção para passar argumentos, onde o significado do argumento é ditado pelo seu nome, não pela sua posição -

#  chama-se keyword argument passing.

# Veja o snippet:

  

def introduction (first_name, last_name):
 
    print("Hello, my name is", first_name, last_name)

  

introduction(first_name = "James", last_name = "Bond")

introduction(last_name = "Skywalker", first_name = "Luke")

  

O conceito é claro - os valores passados para os parâmetros são precedidos pelos nomes dos parâmetros alvo, seguidos do sinal = .

A posição não importa aqui - o valor de cada argumento conhece o seu destino com base no nome utilizado.

  

#4.2.1.6

# Pode misturar ambos os tipos se quiser - há apenas uma regra inquebrável: tem de colocar argumentos posicionais antes de argumentos de keyword.

# Se pensar por um momento, certamente adivinhará porquê.

# Para lhe mostrar como funciona, utilizaremos a seguinte função simples de três parâmetros:

  

def adding(a, b, c):

    print(a, "+", b, "+", c, "=", a + b + c)

  
  

# O seu objetivo é avaliar e apresentar a soma de todos os seus argumentos.

# A função, quando invocada da seguinte maneira:

adding(1, 2, 3)

  

# terá como output:

1 + 2 + 3 = 6

  

# Vamos tentar misturar ambos os estilos agora.

# Veja a invocação da função abaixo:

  

adding(3, c = 1, b = 2)

  

# Vamos analisá-la:

# o argumento (3) para o parâmetro a é passado usando a maneira posicional;

# os argumentos para c e b são especificados como keywords.

# Isto é o que verá na consola:

3 + 2 + 1 = 6

  

# Tenha cuidado, e atenção aos erros. Se tentar passar mais do que um valor para um argumento, tudo o que obterá será um erro de runtime.

# Olhe para a invocação em baixo - parece que tentámos fixar a duas vezes:

adding(3, a = 1, b = 2)

  

A resposta do Python:

TypeError: adding() got multiple values for argu

  

#4.2.1.7

# Acontece por vezes que os valores de um determinado parâmetro são utilizados com mais frequência do que outros.

# Tais argumentos podem ter os seus valores padrão (predefinidos)

# tomados em consideração quando os seus argumentos correspondentes tiverem sido omitidos.

# Dizem que o apelido inglês mais popular é Smith. Vamos tentar ter isto em conta.

  

# O valor padrão do parâmetro é definido usando uma sintaxe clara e pictórica:

  

def introduction(first_name, last_name="Smith"):

    print("Hello, my name is", first_name, last_name)

  
  

# Só tem de estender o nome do parâmetro com o sinal = , seguido pelo valor padrão.

# Vamos invocar a função como de costume:

introduction("James", "Doe")

  

# Consegue adivinhar o output do programa? Execute-o e verifique se estava certo.

# Então? Tudo parece igual, mas quando se invoca a função de uma forma que à primeira vista parece um pouco suspeita, como esta:

introduction("Henry")

  

# ou esta:

introduction(first_name="William")

  

não haverá nenhum erro, ambas as invocações serão bem sucedidas, e a consola mostrará o seguinte output:

Hello, my name is Henry Smith

Hello, my name is William Smith

  

# Pode ir mais além se for útil. Ambos os parâmetros têm agora os seus valores padrão, veja o código em baixo:

def introduction(first_name="John", last_name="Smith"):

    print("Hello, my name is", first_name, last_name)

  
  

# Isto faz com que a seguinte invocação seja absolutamente válida:

introduction()

  
  

# E este é o output esperado:

Hello, my name is John Smith

output

  
  

# Se utilizar um argumento de keyword, o restante tomará o valor padrão:

introduction(last_name="Hopkins")

  
  

# O output é:

Hello, my name is John Hopkins

output

  

# Teste-o.

# Parabéns - acabou de aprender as formas básicas de comunicar com funções.

  

#4.2.1.8

# 1. É possível passar informações para funções utilizando parâmetros. As suas funções podem ter todos os parâmetros que precisar.

# Um exemplo de uma função de um parâmetro:

def hi(name):

    print("Hi,", name)

  

hi("Greg")

  

# Um exemplo de uma função de dois parâmetros:

def hi_all(name_1, name_2):

    print("Hi,", name_2)

    print("Hi,", name_1)

  

hi_all("Sebastian", "Konrad")

  
  

# Um exemplo de uma função de três parâmetros:

def address(street, city, postal_code):

    print("Your address is:", street, "St.,", city, postal_code)

  

s = input("Street: ")

p_c = input("Postal Code: ")

c = input("City: ")

  

address(s, c, p_c)

  
  

# 2. Pode passar argumentos a uma função utilizando as seguintes técnicas:

  

# passagem de argumento posicional onde a ordem de passagem dos argumentos importa (Ex. 1),

# passagem de argumento de keyword (nomeada) onde a ordem dos argumentos passados não importa (Ex. 2),

# uma mistura de passagem de argumentos posicionais e de keyword (Ex. 3).

# Ex. 1

def subtra(a, b):

    print(a - b)

  

subtra(5, 2)    # outputs: 3

subtra(2, 5)    # outputs: -3

  
  

# Ex. 2

def subtra(a, b):

    print(a - b)

  

subtra(a=5, b=2)    # outputs: 3

subtra(b=2, a=5)    # outputs: 3

  

# Ex. 3

def subtra(a, b):

    print(a - b)

  

subtra(5, b=2)    # outputs: 3

subtra(5, 2)    # outputs: 3

  
  

# É importante lembrar que os argumentos posicionais não devem seguir os argumentos de keyword. É por isso que se tentar executar o seguinte snippet:

def subtra(a, b):

    print(a - b)

  

subtra(5, b=2)    # outputs: 3

subtra(a=5, 2)    # Syntax Error

  

# O Python não o deixará fazê-lo através da sinalização de um SyntaxError.

  

#3. Pode usar a técnica de passagem de argumentos de keyword para pré-definir um valor para um determinado argumento:

def name(first_name, last_name="Smith"):

    print(first_name, last_name)

  

name("Andy")    # outputs: Andy Smith

name("Betty", "Johnson")    # outputs: Betty Johnson (the ke

  

#4.3.1.1

# return sem uma expressão

# A primeira consiste na própria keyword, sem nada a seguir.

  

# Quando utilizada dentro de uma função, provoca a terminação imediata da execução da função, e uma devolução

# (em inglês, return) imediata (daí o nome) ao ponto de invocação.

  

# Nota: se uma função não se destina a produzir um resultado, utilizar a instrução return não é obrigatório -

# será executada implicitamente no final da função.

  

# De qualquer modo, pode utilizá-la para terminar as atividades de uma função a pedido, antes de o controlo chegar à última linha da função.

  

Consideremos a seguinte função:

def happy_new_year(wishes = True):

    print("Three...")

    print("Two...")

    print("One...")

    if not wishes:

        return

    print("Happy New Year!")

  
  

Quando invocada sem argumentos:

happy_new_year()

  
  

A função causa um pequeno ruído - o output terá este aspeto:

# Three...

# Two...

# One...

# Happy New Year!

  
  
  

Fornecer False como um argumento:

happy_new_year(False)

  
  

# irá modificar o comportamento da função - a instrução return causará a sua terminação imediatamente antes dos wishes - este é o resultado atualizado:

  

# Three...

# Two...

# One...

  
  

A segunda variante return é estendida com uma expressão:

def function():

    return expression

  
  

Há duas consequências da sua utilização:

# provoca a terminação imediata da execução da função (nada de novo em comparação com a primeira variante)

# além disso, a função avaliará o valor da expressão e devolvê-la-á (daí o nome, mais uma vez) como resultado da função.

# Sim, nós já sabemos - este exemplo não é realmente sofisticado:

def boring_function():

    return 123

  

x = boring_function()

  

print("The boring_function has returned its result. It's:", x)

  

# O snippet grava o seguinte texto na consola:

# The boring_function has returned its result. It's: 123

  
  

def boring_function():

    return 123

  

x = boring_function()

# A instrução return , enriquecida com a expressão (a expressão é muito simples aqui),

# "transporta" o valor da expressão para o local onde a função foi invocada.

  

# O resultado pode ser livremente utilizado aqui, por exemplo, para ser atribuído a uma variável.

  

Note, não estamos a ser muito educados aqui - a função devolve um valor, e ignoramo-lo (não o utilizamos de forma alguma):

  

def boring_function():

    print("'Boredom Mode' ON.")

    return 123

  

print("This lesson is interesting!")

boring_function()

print("This lesson is boring...")

  
  

O programa produz o seguinte output:

  

This lesson is interesting!

'Boredom Mode' ON.

This lesson is boring...

output

  
  

# É punível? De modo algum.

  

# A única desvantagem é que o resultado foi irremediavelmente perdido.

  

# Não se esqueça:

  

# é-lhe sempre permitido ignorar o resultado da função, e ficar satisfeito com o efeito da função (se a função tiver algum)

# se uma função se destina a devolver um resultado útil, deve conter a segunda variante da instrução return .

  

#4.3.1.2

  

# um valor nulo), chamado None.

  

# Os seus dados não representam nenhum valor razoável -

# na verdade, não é um valor de todo; portanto, não deve tomar parte em nenhuma expressão.

  
  

# Existem apenas dois tipos de circunstâncias onde None pode ser utilizado em segurança:

  

# quando o atribui a uma variável (ou o devolve como o resultado de uma função)

# quando o compara com uma variável para diagnosticar o seu estado interno.

# Tal como aqui:

  

value = None

if value is None:

    print("Sorry, you don't carry any value")

  
  

# Não se esqueça disto: se uma função não devolver um determinado valor usando uma return cláusula de expressão,

#  supõe-se que ela devolve implicitamente None.

  

#4.3.1.3

# Algumas palavras sobre None: continuação

# Veja o código no editor.

  

# É óbvio que a função strangeFunction devolve True quando o seu argumento é par.

  

# O que devolve de outra forma?

  

# Podemos utilizar o seguinte código para o verificar:

  

def strange_function(n):

    if(n % 2 == 0):

        return True

print(strange_function(2))

print(strange_function(1))

  

Não fique surpreendido da próxima vez que vir None como resultado de uma função - pode ser o sintoma de um erro subtil dentro da função.

  

#4.3.1.4

# Qualquer entidade reconhecível pelo Python pode desempenhar o papel de um argumento de função,

# embora tenha de ter a certeza de que a função é capaz de lidar com ela.

# Assim, se passar uma lista a uma função, a função tem de lidar com ela como uma lista.

# Uma função como esta aqui:

  

def list_sum(lst):

    s = 0

    for elem in lst:

        s += elem

    return s

  
  

# e invocada assim:

print(list_sum([5, 4, 3]))

  
  

# irá devolver 12 como resultado, mas deve esperar problemas se a invocar desta forma arriscada:

print(list_sum(5))

  
  

# A resposta do Python será inequívoca:

TypeError: 'int' object is not iterable

  

# Isto é causado pelo facto de que um único valor inteiro não deve ser iterado pelo loop for .

  

#4.3.1.5

# Qualquer entidade reconhecível por Python pode ser um resultado de uma função.

def strange_list_fun(n):

    strange_list = []

    for i in range(0, n):

        strange_list.insert(0, i)

    return strange_list

  

print(strange_list_fun(5))

  
  

# Veja o código no editor. O output do programa será assim:

# [4, 3, 2, 1, 0]

  

#4.3.1.6

A sua tarefa é escrever e testar uma função que leva um argumento (um ano) e devolve True se o ano for um ano bissexto, ou False caso contrário.

  

def is_year_leap(year):

    if year < 1582:

        return False

    elif year % 4 != 0:

        return False

    elif year % 100 != 0:

        return True

    elif year % 400 != 0:

        return False

    else:

        return True

  

test_data = [1900, 2000, 2016, 1987]

test_results = [False, True, True, False]

for i in range(len(test_data)):

    yr = test_data[i]

    print(yr,"->",end="")

    result = is_year_leap(yr)

    if result == test_results[i]:

        print("OK")

    else:

        print("Failed")