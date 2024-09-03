appen# 3.4.1.3 (len)

# O método len() .

# O comprimento de uma lista pode variar durante a execução.

# Novos elementos podem ser acrescentados à lista, enquanto outros podem ser retirados da mesma.

# Isto significa que a lista é uma entidade muito dinâmica.

  

# Se quiser verificar o comprimento atual da lista, pode usar uma função chamada len()

# (o seu nome vem de length (comprimento)).

  

# A função toma o nome da lista como argumento, e devolve o número de elementos atualmente armazenados dentro da lista

# (por outras palavras - o comprimento da lista).

  

# 3.4.1.4 (del)

# Qualquer elemento da lista pode ser removido a qualquer momento -

# isto é feito com uma instrução chamada del (delete). Nota: é uma instrução, não uma função.

  

# É preciso apontar o elemento a ser removido - desaparecerá da lista, e o comprimento da lista será reduzido em um.

  

# Índices negativos são legais

# Pode parecer estranho, mas os índices negativos são legais, e podem ser muito úteis.

  

# Um elemento com um index igual a -1 é o último na lista.

# Os índices negativos são lidos de trás pra frente

  

# lab 3.4.1.6

A sua tarefa é:

# escrever uma linha de código que peça ao utilizador para substituir o número médio na lista

# por um número inteiro introduzido pelo utilizador (Passo 1)

# escrever uma linha de código que remova o último elemento da lista (Passo 2)

# escrever uma linha de código que imprima o comprimento da lista existente (Passo 3).

hat_list = [1, 2, 3, 4, 5]

var = int(input("Insira um número: "))

hat_list[3] = var

del hat_list [-1]

  

print("o comprimento da lista é: ", len(hat_list))

  

# a lista é definida pelo conteúdo dentro das []

# após a lista, faço uma variavel(var) aonde peõ para o usuario inserir um numero inteiro

# após isso, seleciono o terceiro item da lista e substítuo ele pelo conteúdo que esta dentro da variavel(var)

# ai eu removo o último item da lista utilizando o (del) + o nome da lista + o índice negativo correspondente.

  

#3.4.1.7

# Um método é um tipo específico de função - comporta-se como uma função e parece uma função,

# mas difere na forma como atua, e no seu estilo de invocação.

  

# Uma função não pertence a nenhum dado - recebe dados, pode criar novos dados e (geralmente) produz um resultado.

  

# Um método faz todas estas coisas, mas também é capaz de alterar o estado de uma entidade selecionada.

  

# Um método é propriedade dos dados para os quais trabalha, enquanto uma função é propriedade de todo o código.

  

Nota: o nome do método é precedido do nome dos dados que possuem o método.

# Em seguida, adiciona-se um ponto, seguido do nome do método, e um par de parêntesis que encerra os argumentos.

  

#3.4.1.8(append e insert)

Um novo elemento pode ser colado no fim da lista existente:

list.append(value)

# Tal operação é realizada por um método chamado append().

# Toma o valor do seu argumento e coloca-o no final da lista que possui o método.

# O comprimento da lista aumenta então em um.

  

O método insert() é um pouco mais inteligente - pode acrescentar um novo elemento em qualquer lugar da lista,

# e não apenas no final.

list.insert(location, value)

# São necessários dois argumentos:

  

# o primeiro mostra a localização necessária do elemento a ser inserido;

# nota: todos os elementos existentes que ocupam locais à direita do novo elemento

#  (incluindo o que se encontra na posição indicada) são deslocados para a direita,

# a fim de criar espaço para o novo elemento;

# o segundo é o elemento a ser inserido.

  

my_list = []  # Creating an empty list.

  

for i in range(5):

    my_list.append(i + 1)

  

print(my_list)

Será uma sequência de números inteiros consecutivos a partir de 1

# (depois adiciona-se um a todos os valores anexados) até 5.

  

my_list = []  # Creating an empty list.

  

for i in range(5):

    my_list.insert(0, i + 1)

  

print(my_list)

  

Deve obter a mesma sequência, mas em ordem inversa (este é o mérito de usar o método insert() ).

  

#3.4.1.10 (listas e loop)

my_list = [10, 1, 8, 3, 5]

total = 0

  

for i in range(len(my_list)):

    total += my_list[i]

  

print(total)

  

# à lista é atribuída uma sequência de cinco valores inteiros;

# a variável i toma os valores 0, 1, 2, 3, e 4, e depois indexa a lista,

# selecionando os elementos seguintes: o primeiro, o segundo, o terceiro, o quarto e o quinto;

# cada um destes elementos é adicionado em conjunto pelo operador += à variável total ,

# dando o resultado final no fim do loop;

# observe a forma como a função len() foi utilizada -

# torna o código independente de quaisquer possíveis alterações no conteúdo da lista.

  
  

# A segunda face do loop for .

# Mas o loop for pode fazer muito mais. Pode ocultar todas as ações ligadas à indexação da lista,

# e entregar todos os elementos da lista de uma forma prática.

  

# Este snippet modificado mostra como isto funciona:

my_list = [10, 1, 8, 3, 5]

total = 0

  

for i in my_list:

    total += i

  

print(total)

# a instrução for especifica a variável usada para navegar na lista (i aqui)

# seguida pela keyword in e pelo nome da lista que está a ser processada (my_list aqui)

# à variável i são atribuídos os valores de todos os elementos da lista subsequente,

# e o processo ocorre tantas vezes quantos os elementos da lista;

# isto significa que se utiliza a variável i como uma cópia dos valores dos elementos,

# e não se precisa de utilizar índices;

# a função len() também não é necessária aqui.

  

#3.4.1.11

como se pode trocar os valores de duas variáveis?

variable_1 = 1

variable_2 = 2

variable_1, variable_2 = variable_2, variable_1

Será ainda aceitável com uma lista contendo 100 elementos? Não, não será.

  

Pode utilizar o loop for para fazer a mesma coisa automaticamente, independentemente do comprimento da lista? Sim, pode.

Foi assim que o fizemos:

  

my_list = [10, 1, 8, 3, 5]

length = len(my_list)

  

for i in range(length // 2):

    my_list[i], my_list[length - i - 1] = my_list[length - i - 1], my_list[i]

  

print(my_list)

  

# nós atribuímos a variável length com o comprimento da lista atual

# (isto torna o nosso código um pouco mais claro e mais curto)

# lançámos o loop for para correr através do seu corpo length // 2 vezes

# (isto funciona bem para listas com comprimentos pares e ímpares, porque quando a lista contém um número ímpar de elementos,

# o do meio permanece intocado)

# trocamos o i-ésimo elemento (desde o início da lista) com o que tem um index

# igual a (length - i - 1) (do final da lista);

# no nosso exemplo, para i igual a 0 o ramo (lenght - i - 1) dá 4; para i igual a 1, dá 3 -

# Isto é exatamente o que precisávamos.

  

lab 3.4.1.13

# Escreva um programa que reflita estas mudanças e lhe permita praticar com o conceito de listas. A sua tarefa é:

  

# passo 1: criar uma lista vazia com o nome beatles;

# passo 2: utilizar o método append() para adicionar os seguintes membros da banda à lista:

#  John Lennon, Paul McCartney, e George Harrison;

  

# passo 3: utilizar o loop for e o método append() para solicitar ao utilizador que adicione os seguintes membros

#  da banda à lista: Stu Sutcliffe, e Pete Best;

  

# passo 4: utilizar a instrução del para remover Stu Sutcliffe e Pete Best da lista;

# passo 5: utilizar o método insert() para adicionar Ringo Starr ao início da lista.

  

beatles = []

print("Step 1:", beatles)

  

beatles.append("John Lennon")

beatles.append("Paul McCartney")

beatles.append("George Harrison")

print("Step 2:", beatles)

  

for member in range(2):

    newMembers = str(input("Insert the new members of the beatles: "))

    beatles.append(newMembers)

print("Step 3:", beatles)

  

del beatles [-1]

del beatles [-1]

print("Step 4: ", beatles)

  

beatles.insert(0, "Ringo Starr")

print("Step 5:", beatles)

  

print("The Fab", len(beatles))

  
  

# 3.4.1.14

# 1. A lista é um tipo de dados em Python usada para armazenar vários objetos.

# É uma coleção ordenada e mutável de ítens separados por vírgulas, entre parêntesis retos, por exemplo:

  

# my_list = [1, None, True, "I am a string", 256, 0]

  
  

# 2. As listas podem ser indexadas e atualizadas, por exemplo:

  

# my_list = [1, None, True, 'I am a string', 256, 0]

# print(my_list[3])  # outputs: I am a string

# print(my_list[-1])  # outputs: 0

  

# my_list[1] = '?'

# print(my_list)  # outputs: [1, '?', True, 'I am a string', 256, 0]

  

# my_list.insert(0, "first")

# my_list.append("last")

# print(my_list)  # outputs: ['first', 1, '?', True, 'I am a string', 256, 0, 'last']

  
  

# 3. As listas podem ser nested, por exemplo:

  

# my_list = [1, 'a', ["list", 64, [0, 1], False]]

  
  

# Aprenderá mais sobre o nesting no módulo 3.1.7 - por enquanto,

# só queremos que esteja ciente de que algo como isto também é possível.

  

# 4. Os elementos da lista e as listas podem ser excluídos, por exemplo:

  

# my_list = [1, 2, 3, 4]

# del my_list[2]

# print(my_list)  # outputs: [1, 2, 4]

  

# del my_list  # deletes the whole list

  
  

# Novamente, aprenderá mais sobre isto no módulo 3.1.6 -

# não se preocupe. Por enquanto, basta tentar experimentar o código acima e verificar como a sua alteração afeta o output.

  

# 5. As listas podem ser iteradas através da utilização do loop for , por exemplo:

  

# my_list = ["white", "purple", "blue", "yellow", "green"]

  

# for color in my_list:

#     print(color)

  
  

# 6. A função len() pode ser usada para verificar o comprimento da lista, por exemplo:

  

# my_list = ["white", "purple", "blue", "yellow", "green"]

# print(len(my_list))  # outputs 5

  

# del my_list[2]

# print(len(my_list))  # outputs 4

  
  

# 7. Uma invocação de função típica parece-se com a seguinte: result = function(arg),

# enquanto uma invocação de método típica parece-se com isto:result = data.method(arg).

  

# 3.5.1.2

# Resolvemos esta questão da seguinte forma: introduzimos outra variável;

# a sua tarefa é observar se foi feita alguma troca durante a passagem ou não; se não houver troca,

# então a lista já está ordenada, e nada mais tem de ser feito. Criamos uma variável chamada swapped,

# e atribuímos-lhe um valor de False , para indicar que não há trocas. Caso contrário, será atribuído True.

  

my_list = [8, 10, 6, 2, 4]  # list to sort

swapped = True  # It's a little fake, we need it to enter the while loop.

  

while swapped:

    swapped = False  # no swaps so far

    for i in range(len(my_list) - 1):

        if my_list[i] > my_list[i + 1]:

            swapped = True  # a swap occurred!

            my_list[i], my_list[i + 1] = my_list[i + 1], my_list[i]

  

print(my_list)

  

#3.5.1.3

Se quiser que o Python ordene a sua lista, pode fazê-lo desta forma:

  

my_list = [8, 10, 6, 2, 4]

my_list.sort()

print(my_list)

  

# O .sort serve para organizar a lista do menor para o meior número que contem dentro dela

  

#1. Pode utilizar a keyword sort() para ordenar elementos de uma lista, por exemplo:

lst = [5, 3, 1, 2, 4]

print(lst)

  

lst.sort()

print(lst)  # outputs: [1, 2, 3, 4, 5]

  

#2. Há também um método de lista chamado reverse(), que pode utilizar para inverter a lista, por exemplo

lst = [5, 3, 1, 2, 4]

print(lst)

  

lst.reverse()

print(lst)  # outputs: [4, 2, 1, 3, 5]

  

#3.6.1.1

list_1 = [1]

list_2 = list_1

list_1[0] = 2

print(list_2)

  

# cria uma lista de um elemento chamada list_1;

# atribui-o a uma nova lista chamada list_2;

# altera o único elemento de list_1;

# imprime list_2.

  

# A atribuição: list_2 = list_1 copia o nome do array, não o seu conteúdo. Com efeito, os dois nomes

# (list_1 e list_2) identificam o mesmo local na memória do computador. Modificar um deles afeta o outro, e vice-versa.

  
  

# O método index é utilizado para encontrar o índice de um elemento específico dentro de uma lista.

# Ele retorna o índice da primeira ocorrência do elemento passado como argumento. Se o elemento não estiver na lista, um erro ValueError será levantado.

  

# Sintaxe:

lista. #index(elemento, start, end)

# elemento: O elemento cujo índice queremos encontrar na lista.

# start (opcional): O índice a partir do qual a busca deve começar.

# end (opcional): O índice até o qual a busca deve ser feita.

# Exemplo:

python

Copiar código

lista = ['a', 'b', 'c', 'a', 'd']

indice_a = lista.index('a')  # Retorna 0, o índice da primeira ocorrência de 'a'

indice_a_apos_1 = lista.index('a', 1)  # Retorna 3, busca a partir do índice 1

indice_a_entre_1_e_3 = lista.index('a', 1, 3)  # Retorna ValueError, pois 'a' não está

  

# Método append

# O método #append é utilizado para adicionar um elemento ao final de uma lista existente.

# Ele modifica a lista original, adicionando o novo elemento como o último item.

  

# Sintaxe:

lista.append(elemento)

# elemento: O elemento a ser adicionado ao final da lista.

# Exemplo:

lista = [1, 2, 3]

lista.append(4)  # Adiciona o número 4 ao final da lista

print(lista)  # Saída: [1, 2, 3, 4]

  

# Método #insert

# O método insert é utilizado para adicionar um elemento em uma posição específica dentro de uma lista.

# Todos os elementos subsequentes são deslocados para a direita. Ele modifica a lista original.

  

Sintaxe:

lista.insert(indice, elemento)

indice: O índice onde o elemento deve ser inserido na lista.

elemento: O elemento a ser inserido na lista.

Exemplo:

lista = [1, 2, 3]

lista.insert(1, 'a')  # Insere 'a' no índice 1, deslocando o 2 para a direita

print(lista)  # Saída: [1, 'a', 2, 3]

  

lista.insert(0, 'z')  # Insere 'z' no índice 0, deslocando todos os elementos para a direita

print(lista)  # Saída: ['z', 1, 'a', 2, 3]

  

#3.6.1.2

Uma das formas mais gerais da #slice tem o seguinte aspeto:

my_list[start:end]

Uma slice desta forma faz uma nova lista (alvo), retirando elementos da source list - os elementos dos índices desde o início até end - 1.

  

my_list = [10, 8, 6, 4, 2]

new_list = my_list[1:3]

print(new_list)

  

A new_list lista terá end - start (3 - 1 = 2) elementos - aqueles com índices iguais a 1 e 2 (mas não 3).

O output do snippet é: [8, 6]

  

É assim que os índices negativos funcionam com o slice:

  

my_list = [10, 8, 6, 4, 2]

new_list = my_list[1:-1]

print(new_list)

  

# O output do snippet é:

  

# [8, 6, 4]

  

#Se o start especifica um elemento que se encontra mais longe do que o descrito pelo end (do ponto de vista inicial da lista), o slice estará vazio:

  

my_list = [10, 8, 6, 4, 2]

new_list = my_list[-1:1]

print(new_list)

  

O output do snippet é:

# []

  

# Se omitir o start no seu slice, assume-se que pretende obter um slice começando pelo elemento com index 0.

# Por outras palavras, o slice desta forma:

my_list[:end]

  

é um equivalente mais compacto de:

my_list[0:end]

  

# Da mesma forma, se omitir o end no seu slice, presume-se que deseja que o slice termine no elemento com o index len(my_list).

# Por outras palavras, o slice desta forma:

my_list[start:]

  

my_list = [10, 8, 6, 4, 2]

new_list = my_list[3:]

print(new_list)

  

O seu output é, portanto: [4, 2].

  

#3.6.1.5

A instrução anteriormente descrita del é capaz de apagar mais do que apenas um elemento de uma lista ao mesmo tempo - também pode apagar slices:

my_list = [10, 8, 6, 4, 2]

del my_list[1:3]

print(my_list)

Nota: neste caso, o slice não produz nenhuma lista nova!

O output do snippet é: [10, 4, 2].

  
  

#3.6.1.6

O primeiro deles (in) verifica se um dado elemento (o seu argumento da esquerda)

está atualmente armazenado algures dentro da lista (o argumento da direita) - o operador devolve True neste caso.

  

my_list = [0, 3, 12, 8, 2]

  

print(5 in my_list)

print(5 not in my_list)

print(12 in my_list)

  
  

O segundo (not in) verifica se um dado elemento (o seu argumento da esquerda) está ausente numa lista - o operador devolve True neste caso.

  

#3.6.1.7

# O primeiro deles tenta encontrar o maior valor na lista. Veja o código no editor.

  

# O conceito é bastante simples - assumimos temporariamente que o primeiro elemento é o maior,

# e verificamos a hipótese contra todos os restantes elementos da lista.

  

my_list = [17, 3, 11, 5, 1, 9, 7, 15, 13]

largest = my_list[0]

  

for i in range(1, len(my_list)):

    if my_list[i] > largest:

        largest = my_list[i]

  

print(largest)

# O código fará o output 17 (como esperado).

  

# O código pode ser reescrito para fazer uso da forma recentemente introduzida do for :

my_list = [17, 3, 11, 5, 1, 9, 7, 15, 13]

largest = my_list[0]

  

for i in my_list:

    if i > largest:

        largest = i

  

print(largest)

  

Se precisar de poupar energia do computador, pode utilizar um slice:

  

my_list = [17, 3, 11, 5, 1, 9, 7, 15, 13]

largest = my_list[0]

  

for i in my_list[1:]:

    if i > largest:

        largest = i

  

print(largest)

  
  

#3.6.1.8

Agora vamos encontrar a localização de um dado elemento dentro de uma lista:

  

my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

to_find = 5

found = False

  

for i in range(len(my_list)):

    found = my_list[i] == to_find

    if found:

        break

  

if found:

    print("Element found at index", i)

else:

    print("absent")

  

# Nota:

# o valor alvo é armazenado na variável to_find ;

# o estado atual da pesquisa é armazenado na variável found (True/False)

# quando found se torna True, o loop for é saído.

  
  

# Vamos supor que escolheu os seguintes números na lotaria: 3, 7, 11, 42, 34, 49.

# Os números que foram sorteados são: 5, 11, 9, 42, 3, 49.

# A questão é: em quantos números é que acertou?

# O programa dar-lhe-á a resposta:

  

drawn = [5, 11, 9, 42, 3, 49]

bets = [3, 7, 11, 42, 34, 49]

hits = 0

  

for number in bets:

    if number in drawn:

        hits += 1

  

print(hits)

  

# Nota:

  

# a keyword drawn armazena todos os números sorteados;

# a lista bets armazena as suas apostas;

# a variável hits conta os seus êxitos.

# O output do programa é: 4.

  

#3.6.1.10

#1. Se tiver uma lista l1, então a seguinte tarefa: l2 = l1 não faz uma cópia da lista l1 ,

#  mas faz com que as variáveis l1 e l2 apontem para uma e a mesma lista na memória. Por exemplo:

vehicles_one = ['car', 'bicycle', 'motor']

print(vehicles_one) # outputs: ['car', 'bicycle', 'motor']

  

vehicles_two = vehicles_one

del vehicles_one[0] # deletes 'car'

print(vehicles_two) # outputs: ['bicycle', 'motor']

  

#2. Se quiser copiar uma lista ou parte da lista, pode fazê-lo executando slicing:

colors = ['red', 'green', 'orange']

  

copy_whole_colors = colors[:]  # copy the entire list

copy_part_colors = colors[0:2]  # copy part of the list

  

#3. Também se podem utilizar índices negativos para executar slices. Por exemplo:

  

sample_list = ["A", "B", "C", "D", "E"]

new_list = sample_list[2:-1]

print(new_list)  # outputs: ['C', 'D']

  

#4. O objeto da exceção start e end parâmetros são opcionais ao executar uma slice: list[start:end], por exemplo.:

  

my_list = [1, 2, 3, 4, 5]

slice_one = my_list[2: ]

slice_two = my_list[ :2]

slice_three = my_list[-2: ]

  

print(slice_one)  # outputs: [3, 4, 5]

print(slice_two)  # outputs: [1, 2]

print(slice_three)  # outputs: [4, 5]

  

#5. Pode eliminar slices usando a instrução del :

  

my_list = [1, 2, 3, 4, 5]

del my_list[0:2]

print(my_list)  # outputs: [3, 4, 5]

  

del my_list[:]

print(my_list)  # deletes the list content, outputs: []

  

#6. Pode testar se alguns itens existem numa lista ou não usando as keywords in e not in, por exemplo.:

  

my_list = ["A", "B", 1, 2]

  

print("A" in my_list)  # outputs: True

print("C" not in my_list)  # outputs: True

print(2 not in my_list)  # outputs: False

  
  

#3.7.1.1

# Vamos assumir que somos capazes de utilizar os números selecionados para representar qualquer peça de xadrez.

# Podemos também assumir que cada linha do tabuleiro de xadrez é uma lista.

  

# Veja o código abaixo:

  

row = []

  

for i in range(8):

    row.append(WHITE_PAWN)

  
  

# Constrói uma lista contendo oito elementos que representam a segunda linha do tabuleiro de xadrez - a que está cheia de peões

# (suponha que WHITE_PAWN é um símbolo pré-definido que representa um peão branco).

  

# O mesmo efeito pode ser alcançado através de uma compreensão de lista, a sintaxe especial utilizada por Python para preencher listas massivas.

  

# Uma compreensão de lista é na realidade uma lista, mas criada durante a execução do programa, e não é descrita estaticamente.

  

# Veja o snippet:

  

row = [WHITE_PAWN for i in range(8)]

  
  

# A parte do código colocada dentro dos parêntesis retos especifica:

  

# os dados a utilizar para preencher a lista (WHITE_PAWN)

# a cláusula que especifica quantas vezes os dados ocorrem dentro da lista (for i in range(8))

# Deixe-nos mostrar-lhe alguns outros exemplos de compreensão de lista:

  

# Exemplo #1:

  

squares = [x ** 2 for x in range(10)]

  
  

# O snippet produz uma lista de dez elementos preenchida com quadrados de dez números inteiros começando do zero (0, 1, 4, 9, 16, 25, 36, 49, 64, 81)

  

# Exemplo #2:

  

twos = [2 ** i for i in range(8)]

  
  

# O snippet cria um array de oito elementos contendo as primeiras oito potências de dois (1, 2, 4, 8, 16, 32, 64, 128)

  

# Exemplo #3:

  

odds = [x for x in squares if x % 2 != 0 ]

  
  

# O snippet faz uma lista apenas com os elementos ímpares da lista squares .

  
  

#3.7.1.4

# Imagine que desenvolve uma peça de software para uma estação meteorológica automática.

# O dispositivo regista a temperatura do ar numa base horária e fá-lo ao longo de todo o mês.

# Isto dá-lhe um total de 24 & vezes; 31 = 744 valores. Vamos tentar criar uma lista capaz de armazenar todos estes resultados.

  

# Primeiro, tem de decidir que tipo de dados serão adequados para esta aplicação.

# Neste caso, um float seria melhor, uma vez que este termómetro é capaz de medir a temperatura com uma precisão de 0,1 ℃.

  

# De seguida, toma uma decisão arbitrária de que as filas registarão as leituras de hora em hora

# (por isso a fila terá 24 elementos) e que cada uma das filas será atribuída a um dia do mês

# (vamos supor que cada mês tem 31 dias, por isso precisa de 31 filas). Aqui está o par apropriado de compreensões (h é para hora, d para dia):

temps = [[0.0 for h in range(24)] for d in range

# Toda a matriz está agora preenchida com zeros. Pode assumir que é atualizada automaticamente utilizando agentes especiais de hardware.

# O que tem de fazer é esperar que a matriz seja preenchida com medições.

  

# Agora é altura de determinar a temperatura média mensal ao meio-dia.

# Some todas as 31 leituras registadas ao meio-dia e divida a soma por 31. Pode assumir que a temperatura à meia-noite é armazenada em primeiro lugar.

# Aqui está o código relevante:

  

temps = [[0.0 for h in range(24)] for d in range(31)]

#

# The matrix is magically updated here.

#

  

total = 0.0

  

for day in temps:

    total += day[11]

  

average = total / 31

  

print("Average temperature at noon:", average)

  

# Nota: a variável day usada pelo loop for não é um escalar - cada passagem através da matriz temps atribui-a com as linhas subsequentes da matriz;

# portanto, é uma lista. Tem que ser indexado com 11 para aceder ao valor da temperatura medida ao meio-dia.

  

# Agora encontre a temperatura mais alta durante todo o mês - veja o código:

  

temps = [[0.0 for h in range(24)] for d in range(31)]

#

# The matrix is magically updated here.

#

  

highest = -100.0

  

for day in temps:

    for temp in day:

        if temp > highest:

            highest = temp

  

print("The highest temperature was:", highest)

  

# Nota:

  

# a keyword day itera através de todas as linhas na matriz temps ;

# a variável temp itera através de todas as medições efetuadas num dia.

  

#3.7.1.5

# Primeiro passo - o tipo de elementos do array. Neste caso, um valor booleano (True/False) caberia.

  

# Segundo passo - análise calma da situação. Resumir a informação disponível: três edifícios, 15 andares, 20 quartos.

  

# Agora pode criar o array:

  

rooms = [[[False for r in range(20)] for f in range(15)] for t in range(3)]

  

# O primeiro index (0 através 2) seleciona um dos edifícios; o segundo (0 através 14) seleciona o andar,

#  o terceiro (0 através 19) seleciona o número do quarto. Todos os quartos estão inicialmente livres.

  

# Agora pode reservar um quarto para dois recém-casados: no segundo edifício, no décimo andar, quarto 14:

  

rooms[1][9][13] = True

  
  

e libertar o segundo quarto no quinto andar, localizado no primeiro edifício:

  

rooms[0][4][1] = False

  
  

Verifique se há vagas no 15º andar do terceiro edifício:

  

vacancy = 0

  

for room_number in range(20):

    if not rooms[2][14][room_number]:

        vacancy += 1

  
  

A variável vacancy contém 0 se todos os quartos estiverem ocupados, ou o número de quartos disponíveis, caso contrário.

  

#3.7.1.6

#1. A compreensão de lista permite-lhe criar novas listas a partir de listas existentes de uma forma concisa e elegante.

#  A sintaxe de uma compreensão de lista é a seguinte:

  

[expression for element in list if conditional]

  
  

que é na verdade um equivalente ao seguinte código:

  

for element in list:

    if conditional:

        expression

  
  

Eis um exemplo de compreensão de uma lista - o código cria uma lista

#  de cinco elementos preenchida com os primeiros cinco números naturais elevados à potência de 3:

  

cubed = [num ** 3 for num in range(5)]

print(cubed)  # outputs: [0, 1, 8, 27, 64]

  
  

#2. Pode usar listas nested em Python para criar matrizes (ou seja, listas bidimensionais). Por exemplo:

  

Tabela - uma matriz bidimensional

  

# A four-column/four-row table - a two dimensional array (4x4)

  

table = [[":(", ":)", ":(", ":)"],

         [":)", ":(", ":)", ":)"],

         [":(", ":)", ":)", ":("],

         [":)", ":)", ":)", ":("]]

  

print(table)

print(table[0][0])  # outputs: ':('

print(table[0][3])  # outputs: ':)'

  

#3. Pode fazer nest de quantas lists-in-lists quiser, e portanto criar listas n-dimensionais,

#  por exemplo, três, quatro ou mesmo sessenta e quatro arrays dimensionais. Por exemplo:

  

Cubo - uma matriz tridimensional

  

# Cube - a three-dimensional array (3x3x3)

  

cube = [[[':(', 'x', 'x'],

         [':)', 'x', 'x'],

         [':(', 'x', 'x']],

  

        [[':)', 'x', 'x'],

         [':(', 'x', 'x'],

         [':)', 'x', 'x']],

  

        [[':(', 'x', 'x'],

         [':)', 'x', 'x'],

         [':)', 'x', 'x']]]

  

print(cube)

print(cube[0][0][0])  # outputs: ':('

print(cube[2][2][0])  # outputs: ':)'
#4.1.1.4

#Lista é uma coleção ordenada e mutável(pode adicionar e remover os elementos de dentro dela). Permite elementos duplicados

# index:    0        1   2   3

lista = ["carro", True, 2, 3.5]

print (lista)

print(type(lista))

print(lista[1])

  
  

#Tupla é uma coleção ordenada e imútavel. Também permite elementos duplicados

tupla = ("carro", True, 2, 3.5)

print(tupla)

print(type(tupla))

  

os dicionarios são coleções ordenadas, mutáveis e não permite elementos duplicados

               #chave :  valor

dicionario = {"nome" : "carro", "logica" : True, "numero" : 2, "outroNumero" : 3.5}

print(dicionario)

print(type(dicionario))

print(dicionario["logica"])

  
  

#set é uma coleção não ordenada e nãi indexada. Nenhum mebro duplicado

conjunto = {"carro", True, 2, 3.5}

print(conjunto)

print(type(conjunto))

  
  
  

A estrutura do array permite fazer manipulações matematicas, ja a lista não. Apenas armazena os valores.

  
  

# Aqui vamos começar com um exemplo bem simples de lista, onde estamos atribuindo 3 itens a variável lista_compras.

  

lista_compras = ['banana','laranja','maçã']

print(lista_compras)

['banana', 'laranja', 'maçã']

# Cada item da lista possui uma posição. Por padrão, as posições não iniciam do 1 (um) e sim do 0 (ZERO).

# Nos códigos seguintes temos as formas de acessar uma informação da lista.

  

# Para acessarmos um item da lista vamos utilizar a estrutura: nomedalista[posição].

  

# Buscando a posição [1]:

  

print(lista_compras[1])

laranja

# Buscando a posição [0]:

  

print(lista_compras[0])

banana

  
  

# Se tentarmos buscar a posição [3] teremos um erro. Isso corre, porque não existe uma posição 3. Apenas as posições [0], [1], [2]:

  

# Outro ponto interessante é que conseguimos utilizar as posições negativas dentro da lista para buscar os dados na ordem inversa!

  

# O uso de números negativos permite acessar a lista na ordem inversa:

  

print(lista_compras[-1])

    maça

  

[banana , laranja , maçã]

[  0    ,   1     ,  2  ] -> Posições números positivos

[  -3   ,  -2     , -1  ] -> Posições números negativos

  

# Para adicionar um item a lista:

  

# .append(): adiciona o item ao final da lista;

# .insert(): insere um item na lista na posição indicada

  

# Para deletar um item da lista:

# del: remove um item da lista baseado na posição indicada;

# .remove(): remove um item baseado no seu valor e não na sua posição;

# .pop(): remove da lista_compras o último item, mas não o exclui.

  

# No exemplo abaixo tentamos incluir o item ‘carro’ a nossa lista_compras com o .append():

lista_compras.append('carro')

print(lista_compras)

['banana', 'laranja', 'maçã', 'carro']

  

# Utilizando del para remover item com base na posição indicada:

del lista_compras[3]

print(lista_compras)

['banana', 'laranja', 'maçã']

  

# Já no código abaixo, adicionamos ‘carro’ à lista na posição indicada, com .insert():

lista_compras.insert(1,'carro')

print(lista_compras)

['banana', ' carro', 'laranja', 'maçã']

  

#  Removendo um item com base no seu valor e não na sua posição, com o .remove() (ATENÇÃO! retira apenas a primeira ocorrência e não todas):

lista_compras.append('carro')

print(lista_compras)

['banana', 'carro', 'laranja', 'maçã', 'carro']

  

lista_compras.remove('carro')

print(lista_compras)

['banana', 'laranja', 'maçã', 'carro']

  

# Para criarmos vamos usar novamente o colchetes, mas sem nenhum item:

  

lista_sonhos = []

  

# Utilizando .pop(), iremos remover o último item da lista_compras, mas sem excluí-lo. Nesse caso, o valor carro será armazenado na variável item:

item = lista_compras.pop(-1)

print(item)

carro

  

# Após retirar da lista_compras, adicionamos ‘carro’ na nossa lista_sonhos:

lista_sonhos.append(item)

print(lista_sonhos)

['carro']

  

# Como criar uma lista do zero no Python?

# Podemos também criar uma lista do zero

# e trazer itens de outras listas para dentro dele com a utilização do pop que vai pegar essa informação e armazenar em outra variável.

# Outra opção para criar uma lista é utilizar a função input para que o próprio usuário possa inserir as informações de forma manual através de uma caixa!

  

# Criando a lista tarefas

tarefas = []

  

# Usando o Input() vamos coletar do usuário qual a tarefa a ser adicionada.

atividade = input('Insira uma atividade: ')

  

Adiciona a tarefa indicada pelo usuário a lista de tarefas

tarefas.append(atividade)

  

# Insira uma atividade: Curtir o video de listas da Hashtag

print(tarefas)

['Curtir o video de listas da Hashtag']