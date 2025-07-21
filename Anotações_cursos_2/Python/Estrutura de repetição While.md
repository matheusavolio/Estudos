O loop de repetição #while é uma estrutura de controle de fluxo que permite executar repetidamente um bloco de código enquanto uma condição especificada for verdadeira. A sintaxe básica é:


`while condição:     
	` bloco de código a ser repetido`

### Funcionamento do Loop #while

1. **Avaliação da Condição:** Antes de cada iteração, a condição é avaliada. Se a condição for verdadeira (`True`), o bloco de código dentro do loop é executado. Se a condição for falsa (`False`), o loop termina e o controle do programa passa para a próxima instrução após o loop.
    
2. **Execução do Bloco de Código:** Se a condição for verdadeira, o bloco de código dentro do loop é executado.
    
3. **Reavaliação:** Após a execução do bloco de código, a condição é reavaliada. Se ainda for verdadeira, o bloco de código é executado novamente. Isso continua até que a condição se torne falsa.
    

### Exemplo:


`contador = 0 
`while contador < 5:     
	`print(f"Contador: {contador}")     contador += 1`

Neste exemplo:

1. Inicialmente, `contador` é 0.
2. A condição `contador < 5` é verdadeira, então o bloco de código dentro do `while` é executado.
3. A instrução `print` exibe o valor atual de `contador`.
4. A instrução `contador += 1` incrementa `contador` em 1.
5. O loop continua até que `contador` seja 5, momento em que a condição `contador < 5` se torna falsa e o loop termina.

### Considerações:

- **Condição Infinita:** Se a condição nunca se tornar falsa, o loop se tornará um loop infinito. É importante garantir que a condição eventualmente se torne falsa para evitar travar o programa.
- **Interrupção de Loop:** O loop pode ser interrompido antecipadamente usando a instrução `break`.
- **Continuação de Loop:** A instrução `continue` pode ser usada para pular o restante do bloco de código na iteração atual e passar para a próxima iteração.

### Exemplo com #break e #continue:


`contador = 0 
`while contador < 10:     
	`contador += 1     
	`if contador == 5:        
		`continue  # Pula a iteração atual quando contador é 5     
	`print(f"Contador: {contador}")     
`if contador == 8:         
	`break  # Interrompe o loop quando contador é 8`

Neste exemplo:

- Quando `contador` é 5, a instrução `continue` faz com que o loop pule a iteração atual, não executando a instrução `print`.
- Quando `contador` é 8, a instrução `break` interrompe o loop, mesmo que a condição `contador < 10` ainda seja verdadeira.

O loop `while` é uma ferramenta poderosa para repetição condicional e deve ser usado com cuidado para evitar loops infinitos e garantir que o código seja claro e eficiente.


Exemplo da #EstruturaDeRepetiçãoWhile

`sexo = str(input("Insira o sexo da pessoa: [M/F]: ")).lower().strip()
`while sexo not in "MmFf":
    `sexo = str(input("Dados inválidos. Por favor informe o seu sexo: "))
`print(f"Sexo {sexo} registrado com")

`sexo = str(input("Insira o sexo da pessoa: [M/F]: ")).lower().strip()`

1. `input("Insira o sexo da pessoa: [M/F]: ")` solicita que o usuário insira o sexo, exibindo a mensagem entre parênteses. O valor inserido pelo usuário é uma string.
2. `str(...)` garante que o valor retornado pelo `input` seja convertido para uma string (embora isso não seja estritamente necessário, já que `input` já retorna uma string).
3. `.lower()` converte todos os caracteres da string para minúsculas, para uniformizar a entrada e facilitar a comparação.
4. `.strip()` remove quaisquer espaços em branco extras no início e no final da string, para evitar problemas com entradas acidentais.


`while sexo not in "MmFf":`

5. Este `while` verifica se o valor de `sexo` não está na string `"MmFf"`, ou seja, se o valor inserido pelo usuário não é uma das letras 'M' ou 'F' (em maiúsculas ou minúsculas).
6. Se o valor de `sexo` não for válido, o loop continua a execução, solicitando novamente a entrada do usuário.


    `sexo = str(input("Dados inválidos. Por favor informe o seu sexo: "))`

7. Dentro do loop `while`, se a entrada anterior não foi válida, o programa solicita novamente que o usuário insira o sexo. A mensagem desta vez informa que os dados foram inválidos.
8. O valor inserido pelo usuário é novamente convertido para uma string, embora isso seja redundante.
9. O loop continuará até que o usuário insira um valor válido ('M' ou 'F').


`print(f"Sexo {sexo} registrado com sucesso")`

10. Quando o usuário finalmente insere um valor válido, o loop `while` termina.
11. Esta linha imprime uma mensagem confirmando que o sexo foi registrado com sucesso. A string formatada `f"Sexo {sexo} registrado com sucesso"` inclui o valor de `sexo` dentro da mensagem.

Em resumo, este código solicita ao usuário que insira seu sexo, verifica se a entrada é válida ('M' ou 'F'), e continua solicitando até que uma entrada válida seja fornecida, após o que confirma o registro.


# Outro exemplo:

`num1 = float(input("Insira um número: "))
`num2 = float(input("Insira um número: "))
`opcao = 0
`while opcao != 5:
    `print("Para prosseguir, selecione alguma das opções abaixo: ")
    `print("[1]somar")
    `print("[2]multiplicar")
    `print("[3]maior")
    `print("[4]novos números")
    `print("[5]sair")    
    `opcao = int(input("Qual é sua opção? "))
    `if opcao == 1:
        `soma = num1 + num2
        `print(f"A soma de {num1} + {num2} é {soma}")
    `elif opcao == 2:
        `multiplicacao = num1 * num2
        `print(f"A multiplicação de {num1} * {num2} é {multiplicacao}")
    `elif opcao == 3:
        `if num1 > num2:
            `maior = num1
        `else:
            `maior = num2
        `print(f"O maior número é {maior}")
    `elif opcao == 4:
        `print("Insira os números novamente ")
        `num1 = float(input("Insira um número: "))
        `num2 = float(input("Insira um número: "))
    `elif opcao == 5:
        `print("Volte sempre!")
    `else:
        `print("Opcao invalida, tente novamente!")





`num1 = float(input("Insira um número: ")) 
`num2 = float(input("Insira um número: ")) 
`opcao = 0`

1. **Entrada de Dados**:
    - **Linha 1**: `num1 = float(input("Insira um número: "))`
        - Solicita ao usuário um número, que é convertido para um tipo de dado `float` (número decimal), e armazena-o na variável `num1`.
    - **Linha 2**: `num2 = float(input("Insira um número: "))`
        - Solicita ao usuário outro número, que é convertido para `float`, e armazena-o na variável `num2`.
    - **Linha 3**: `opcao = 0`
        - Inicializa a variável `opcao` com o valor 0. Esta variável será usada para controlar o loop `while`.


`while opcao != 5:     
	`print("Para prosseguir, selecione alguma das opções abaixo: ")     
	`print("[1]somar")     
	`print("[2]multiplicar")     
	`print("[3]maior")     
	`print("[4]novos números")     
	`print("[5]sair")     
	`opcao = int(input("Qual é sua opção? "))`

2. **Loop de Opções**:
    - **Linha 4**: `while opcao != 5:`
        - Inicia um loop `while` que continuará enquanto `opcao` não for igual a 5.
    - **Linha 5-10**: `print(...)`
        - Exibe um menu de opções para o usuário escolher.
    - **Linha 11**: `opcao = int(input("Qual é sua opção? "))`
        - Solicita ao usuário que insira uma opção, que é convertida para `int` (inteiro) e armazenada na variável `opcao`.


`if opcao == 1:
	`` soma = num1 + num2         
	`` print(f"A soma de {num1} + {num2} é {soma}")     
`elif opcao == 2:         
	`multiplicacao = num1 * num2         
	`print(f"A multiplicação de {num1} * {num2} é {multiplicacao}")     
`elif opcao == 3:         
	`if num1 > num2:            
		`maior = num1         
	`else:             
		`maior = num2         
	`print(f"O maior número é {maior}")     
`elif opcao == 4:         
	`print("Insira os números novamente ")         
	`num1 = float(input("Insira um número: "))         
	`num2 = float(input("Insira um número: "))     
`elif opcao == 5:         
	`print("Volte sempre!")     
`else:
	`print("Opcao invalida, tente novamente!")`

3. **Execução das Opções**:
    - **Linha 12**: `if opcao == 1:`
        
        - Verifica se a opção escolhida é 1.
        - **Linha 13**: `soma = num1 + num2`
            - Calcula a soma de `num1` e `num2`, e armazena o resultado na variável `soma`.
        - **Linha 14**: `print(f"A soma de {num1} + {num2} é {soma}")`
            - Exibe o resultado da soma.
    - **Linha 15**: `elif opcao == 2:`
        
        - Verifica se a opção escolhida é 2.
        - **Linha 16**: `multiplicacao = num1 * num2`
            - Calcula a multiplicação de `num1` e `num2`, e armazena o resultado na variável `multiplicacao`.
        - **Linha 17**: `print(f"A multiplicação de {num1} * {num2} é {multiplicacao}")`
            - Exibe o resultado da multiplicação.
    - **Linha 18**: `elif opcao == 3:`
        - Verifica se a opção escolhida é 3.
        - **Linha 19-22**: `if num1 > num2: ... else: ...`
            - Compara `num1` e `num2` para determinar qual é o maior.
            - **Linha 19**: `if num1 > num2:`
                - Se `num1` for maior que `num2`, armazena `num1` na variável `maior`.
            - **Linha 21**: `else:`
                - Caso contrário, armazena `num2` na variável `maior`.
            - **Linha 22**: `print(f"O maior número é {maior}")`
                - Exibe o maior número.
    - **Linha 23**: `elif opcao == 4:`
        - Verifica se a opção escolhida é 4.
        - **Linha 24**: `print("Insira os números novamente ")`
            - Exibe uma mensagem solicitando novos números.
        - **Linha 25-26**: `num1 = float(input(...)) ... num2 = float(input(...))`
            - Solicita ao usuário novos valores para `num1` e `num2`.
    - **Linha 27**: `elif opcao == 5:`
        - Verifica se a opção escolhida é 5.
        - **Linha 28**: `print("Volte sempre!")`
            - Exibe uma mensagem de despedida.
    - **Linha 29**: `else:`
        - Caso `opcao` não seja nenhuma das opções anteriores.
        - **Linha 30**: `print("Opcao invalida, tente novamente!")`
            - Exibe uma mensagem informando que a opção é inválida e solicita outra tentativa.

Este código implementa um menu de operações básicas (soma, multiplicação, verificação do maior número e reinserção de números), que se repete até que o usuário escolha a opção de sair (opção 5).




`pa = int(input("Insira a pa: ")) 
`razao = int(input("Insira a razao: ")) 
`calculo = pa + razao 
`cont = 1  
`while cont != 10:     
	`print(calculo)     
	`calculo = calculo + razao    
	`cont+=1 
`print(calculo)`

1. **Entrada de Dados**:
    
    - **Linha 1**: `pa = int(input("Insira a pa: "))`
        - Solicita ao usuário que insira o primeiro termo (`pa`) da progressão aritmética.
    - **Linha 2**: `razao = int(input("Insira a razao: "))`
        - Solicita ao usuário que insira a razão (`razao`) da progressão aritmética.
    - **Linha 3**: `calculo = pa + razao`
        - Calcula o segundo termo da progressão (primeiro termo + razão) e armazena-o na variável `calculo`.
    - **Linha 4**: `cont = 1`
        - Inicializa a variável `cont` com o valor 1.
2. **Loop para Exibir os Termos**:
    
    - **Linha 5**: `while cont != 10:`
        - Inicia um loop `while` que continuará enquanto `cont` não for igual a 10.
    - **Linha 6**: `print(calculo)`
        - Exibe o valor atual de `calculo`, que representa o próximo termo da progressão aritmética.
    - **Linha 7**: `calculo = calculo + razao`
        - Atualiza o valor de `calculo` adicionando a razão.
    - **Linha 8**: `cont += 1`
        - Incrementa a variável `cont` em 1.
    - **Linha 9**: `print(calculo)`
        - Exibe o valor final de `calculo` após o loop ter terminado.





`termos = str(input("\nQuer mostrar mais termos? [S/N]:"))
`termos = termos.lower() 
`if termos == "s":     
	`termos1 = int(input("Insira quantos termos você quer ver: "))     
	`while termos != termos1:         
		`print(calculo)         
		`calculo = calculo + razao         
		`cont+=1     
	`else:         
		`print("Progressão aritmética encerrada!")     
	`print(calculo, end=" ")`

3. **Solicitar Mais Termos**:
    - **Linha 10**: `termos = str(input("\nQuer mostrar mais termos? [S/N]:"))`
        - Pergunta ao usuário se ele deseja mostrar mais termos.
    - **Linha 11**: `termos = termos.lower()`
        - Converte a resposta do usuário para minúsculas.
    - **Linha 12**: `if termos == "s":`
        - Verifica se o usuário respondeu "s" (sim).
    - **Linha 13**: `termos1 = int(input("Insira quantos termos você quer ver: "))`
        - Solicita ao usuário quantos termos adicionais ele deseja ver.
    - **Linha 14**: `while termos != termos1:`
        - **Erro**: Aqui, `termos` é uma string ('s' ou 'n') e `termos1` é um número inteiro. A condição correta seria baseada no contador e no número de termos a serem exibidos.
    - **Linha 15-18**: `print(calculo) ... calculo = calculo + razao ... cont += 1 ... else: print("Progressão aritmética encerrada!")`
        - Imprime os termos adicionais da progressão, incrementando o valor de `calculo` e `cont`.



# Exemplo:

`from sympy import fibonacci as fibo
`termos = int(input("Quantos termos você quer mostrar? "))
`cont = 1
`while cont < termos:
    `fibonacci = fibo(cont)
    `print(fibonacci, end=" -> ")
    `cont+=1
`print("fim")


- **Importação da Biblioteca:**
    `from sympy import fibonacci as fibo`
    - Esta linha importa a função `fibonacci` da biblioteca `sympy` e a renomeia como `fibo`. Isso facilita o uso da função com um nome mais curto.



- **Solicitação de Entrada ao Usuário:**
    
    `termos = int(input("Quantos termos você quer mostrar? "))`
    - Solicita ao usuário que insira o número de termos da sequência de Fibonacci que ele deseja exibir.
    - `input()` lê a entrada do usuário como uma string.
    - `int()` converte a string em um inteiro e armazena esse valor na variável `termos`.

- **Inicialização do Contador:**
    `cont = 1`
    
    - Inicializa a variável `cont` com o valor 1. Este será o contador que rastreia quantos termos foram exibidos até agora.
    - Note que começando de 1, você ignorará o primeiro termo (0) da sequência de Fibonacci. Isso será corrigido na análise.


- **Loop While:**
    `while cont < termos:`
    
    - Inicia um loop `while` que continuará enquanto `cont` for menor que `termos`.
    - Isto significa que se `termos` for 5, o loop executará enquanto `cont` for 1, 2, 3, ou 4.


- **Cálculo do Termo Fibonacci:**
    `fibonacci = fibo(cont)`
    
    - Chama a função `fibo` (que é `fibonacci` da biblioteca `sympy`) com o valor atual de `cont` para calcular o termo correspondente da sequência de Fibonacci.
    - Armazena o resultado na variável `fibonacci`.


- **Impressão do Termo Fibonacci:**
    `print(fibonacci, end=" -> ")`
    
    - Imprime o termo de Fibonacci calculado, seguido por `->` sem quebrar a linha.
    - `end=" -> "` especifica que, em vez de quebrar a linha após a impressão, deve adicionar `->` após cada termo.



- **Incremento do Contador:**
    `cont += 1`
    
    - Incrementa `cont` em 1 para passar ao próximo termo da sequência de Fibonacci na próxima iteração do loop.

- **Fim do Loop:**
    `print("fim")`
    
    - Quando o loop `while` termina (quando `cont` não é mais menor que `termos`), imprime "fim" para indicar que a sequência foi completada.



# Correção: 

O contador `cont` começa em 1, portanto o primeiro termo da sequência (0) é ignorado. Se você deseja incluir o primeiro termo, `cont` deve começar em 0 e a condição do loop deve ser `<= termos`.

`from sympy import fibonacci as fibo  
`termos = int(input("Quantos termos você quer mostrar? ")) 
`cont = 0   
`while cont < termos:    
	`fibonacci = fibo(cont)    
	`print(fibonacci, end=" -> ")     
	`cont += 1 
`print("fim")`

### Explicação da Correção:

- **Inicialização do Contador:**
    
    
    `cont = 0`
    - Inicializa `cont` com 0 para incluir o primeiro termo (0) da sequência de Fibonacci.


- **Condição do Loop:**
    `while cont < termos:`
    
    - A condição `while cont < termos` permanece a mesma, o loop executará até que `cont` seja igual ao número de termos solicitados.

Este código garantirá que todos os termos da sequência de Fibonacci até o número solicitado pelo usuário sejam exibidos corretamente.





`num = c = soma = 0
`continuar = "s"
`while continuar == "s":
    `num = int(input("Insira um número: "))
    `c +=1
    `soma +=num
    `continuar = str(input("Quer continuar? [S/N]: ")).lower().strip()
    `if c == 1:
        `maior = menor = num
    `else:
        `if num > maior:
            `maior = num
        `if num < menor:
            `menor = num
    `if continuar == "n":
        `media = soma / c
`print(f"Você digitou {c} números e a media dos números mostrados foi: {media:.2f}")
`print(f"O maior número foi {maior} e o menor número foi {menor}")


- **Inicialização das Variáveis:**
    
    
    `num = c = soma = 0 continuar = "s"`
    
    - `num` será usado para armazenar cada número inserido pelo usuário.
    - `c` será o contador de quantos números foram inseridos.
    - `soma` será usada para somar todos os números inseridos.
    - `continuar` é inicializado com "s" (sim) para entrar no loop `while`.


- **Loop `while` Principal:**

    `while continuar == "s":`

- Este loop continua enquanto `continuar` for igual a "s".


- **Entrada de Dados e Atualização das Variáveis:**
    
    `num = int(input("Insira um número: ")) c += 1 soma += num continuar = str(input("Quer continuar? [S/N]: ")).lower().strip()`
    
    - Solicita ao usuário para inserir um número e converte-o para inteiro.
    - Incrementa o contador `c` em 1.
    - Adiciona o número inserido à `soma`.
    - Pergunta ao usuário se ele quer continuar e converte a resposta para minúsculas, removendo espaços extras.


- **Determinação do Maior e Menor Número:**
    

    `if c == 1:     
	    `maior = menor = num 
    `else:     
	    `if num > maior:         
		    `maior = num     
	    `if num < menor:        
	     `menor = num`
    
    - Na primeira iteração (`c == 1`), inicializa `maior` e `menor` com o primeiro número inserido.
    - Em iterações subsequentes, atualiza `maior` e `menor` se o número atual for maior ou menor, respectivamente.


- **Cálculo da Média:**

    `if continuar == "n":
         `media = soma / c`
    
    - Se o usuário decide não continuar (`continuar == "n"`), calcula a média dos números inseridos.


- **Impressão dos Resultados:**
    
    `print(f"Você digitou {c} números e a média dos números mostrados foi: {media:.2f}") 
    `print(f"O maior número foi {maior} e o menor número foi {menor}")`
    
    - Após sair do loop, imprime o total de números inseridos e a média, formatando-a com duas casas decimais.
    - Também imprime o maior e o menor número inserido.