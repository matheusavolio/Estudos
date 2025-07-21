 # A instrução #while é usada para execução repetida desde que uma expressão seja verdadeira:
Ex:
`condicao = True`

`while condicao:`
	`nome = input("Insira seu nome: ")`
	`print(f"Seu nome é:{nome}")`

O exemplo acima se trata de um loop infinito, enquanto a condicao for verdadeira, o loop continuará , porém, quando a condicao for falsa ele irá parar.

Ou podemos usar um #break 
e assim irá ficar nosso código:

`condicao = True`

`while condicao:`
	`nome = input("Insira seu nome: ")`
	`print(f"Seu nome é:{nome}")`

	if nome == "sair":
		break

quando o break é acionado, ele irá parar a execução do loop até o momento. O loop irá se repetir normalmente, porém se alguém escrever "sair", o loop irá parar de ser executado.

#  Outro exemplo:

`n = s = 0
`while True:
    `n = int(input("Insira um número: "))
    `if n == 999:
        `break
    `s+=n
`print(f"A soma vale: {s}")

# Análise do código:
 # `No exemplo acima, graças a condição do while que vai ser verdadeira para sempre, vai ficar pedindo para o usuário inserir um número, porém, se o usuário inserir o número 999 o loop irá parar de se repetir e irá para o próximo bloco de código se houver, no caso acima ele irá para o `s+=n` que vai somar todos os números inseridos pelo usuário sem contar o 999, ja que ele é a condição de parada`





# Vamos supor que você está em uma sala de aula e quer fazer um sistema aonde você coloca o nome de seus alunos(no exemplo limitamos a quantidade de alunos a 3, porém pode colocar a quantidade máxima que desejar)
O código ficaria assim:

`cont = 0
`while cont != 3:
   `alunos = str(input("Insira o nome dos alunos: "))
   `cont += 1
`print("Número limite de alunos excedido")`

definimos a variável `cont` com o valor de 0
`cont = 0`
enquanto a variável `cont` não for igual a 3
`while cont != 3` 
vai pedir para o usuário inserir o nome do aluno
	`alunos = str(input("Insira o nome dos alunos"))`

quando o usuário inserir o nome de um aluno, a var `cont` é atualizada adicionando + 1 na contagem
	`cont += 1`

quando o usuário inserir o nome de três alunos, chega ao fim 
do loop, assim exibindo a mensagem "número limite de alunos excedido"
`print("Número limite de alunos excedido")`

Se quiser que a contagem pare em um número específico
pode se usar o break:

`cont = 0`
`while cont <10:
   `` aluno = input("Insira o nome do aluno: ")
    `cont += 1
    `if cont == 5:
        `break
`print("Fim")

quando o cont chegar no número 5, a contagem irá parar
e vai ser impresso a mensagem "Fim"

# Sempre que o loop #while ver um #break, ele irá terminar o loop imediatamente.

# #continue - comporta-se como se o programa tivesse subitamente chegado ao fim do corpo; inicia-se a volta seguinte e a expressão da condição é testada imediatamente.

LAB 3.2.1.9 #while #continue

`ani = input("Insira o nome de um animal: ")
`while ani != "cachorro":
   `` ani = str(input("Insira o nome de um animal:"))
    `continue
`while ani == "cachorro":
    `print("You've successfully left the loop.")
    `break

  
criei uma varável chamada (ani) para pedir ao usuário que insira um nome de um animal
enquanto #while ani (var) não for igual (!=) a cachorro
vai pedir novamente para o usuário inserir um nome
usei o #continue para que o programa continue perguntando infinitamente um nome ao usuário até ele digitar "cachorro"
se ele digitar "cachorro" o programa exibe uma mensagem (you've successfully left the loop.) e para (break)


# Exemplo: 

`while True: 
	`c = 0 
	`num = int(input("Quer ver a tabuada de qual valor?: ")) 
	`if num < 0: 
		`print("Programa tabuada encerrado. Volte sempre!") 
		`break 
	`else: 
	``	while c < 10: 
			`c += 1 
			`tabuada = num * c 
			`print(f"{num} x {c} = {tabuada}")

1. **Loop Infinito:**
    

    `while True:`
    - Inicia um loop infinito que só será interrompido por um `break`.

2. **Inicialização do Contador:**
    
    `c = 0`
    
    - Inicializa o contador `c` com 0. Este contador será usado para controlar a multiplicação na tabuada.


3. **Entrada do Usuário:**
    
    `num = int(input("Quer ver a tabuada de qual valor?: "))`
    
    - Solicita ao usuário que insira um número para o qual deseja ver a tabuada.
    - Converte a entrada do usuário para um inteiro e armazena em `num`.


4. **Verificação de Número Negativo:**
    
    `if num < 0:
        `` print("Programa tabuada encerrado. Volte sempre!")    
        ``  break`
    
    - Se o número inserido pelo usuário for negativo, imprime uma mensagem de encerramento e usa `break` para sair do loop infinito.


5. **Exibição da Tabuada:**
    
    `else:
        `` while c < 10:
                ``  c += 1         
                ``  tabuada = num * c         
                ``  print(f"{num} x {c} = {tabuada}")`
    
    - Se o número não for negativo, entra em um loop `while` que continua enquanto `c` for menor que 10.
    - Em cada iteração do loop, incrementa `c` em 1.
    - Calcula o resultado da multiplicação `num * c` e armazena em `tabuada`.
    - Imprime a multiplicação e o resultado no formato `"{num} x {c} = {tabuada}"`.

### Fluxo do Código

1. O programa começa e entra no loop infinito.
2. Pede ao usuário um número para calcular a tabuada.
3. Se o número for negativo, imprime uma mensagem e encerra o programa.
4. Se o número for positivo, calcula e imprime a tabuada de 1 a 10 para o número fornecido.
5. Volta ao início do loop infinito para solicitar um novo número ou verificar se deve encerrar.


# Código Melhorado com Alguns Ajustes

1. **Mantém a mesma lógica, mas com algumas melhorias de clareza e eficiência.**

python

Copiar código

`while True:
	`num = int(input("Quer ver a tabuada de qual valor?: "))    
	`if num < 0:         
		`print("Programa tabuada encerrado. Volte sempre!")         
		`break     
	`for c in range(1, 11):        
		`tabuada = num * c         
		`print(f"{num} x {c} = {tabuada}")`

### Explicação do Código Melhorado

1. **Substituição do Loop Interno:**
    
    - Substitui o loop `while c < 10` por um loop `for c in range(1, 11)`, que é mais claro e conciso.
    - O `for` loop vai de 1 a 10 diretamente, simplificando a lógica do contador.
2. **Manutenção da Estrutura Principal:**
    
    - Mantém a estrutura principal do loop infinito `while True`.
    - Solicita o número do usuário e verifica se é negativo para encerrar o programa.
3. **Cálculo e Impressão da Tabuada:**
    
    - Calcula e imprime a tabuada de forma clara e eficiente dentro do loop `for`.