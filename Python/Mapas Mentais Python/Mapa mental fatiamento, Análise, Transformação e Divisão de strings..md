
### #Fatiamento de Strings

O fatiamento #slice permite extrair partes específicas de uma string:

- #start Índice inicial (incluído).
- #end: Índice final (excluído).
- #jump: Passo, ou seja, quantos índices pular.


`texto = "meu nome" 
`print(texto[4:8])  # Saída: nome  

`frase = "programar é difícil" 
`print(frase[0:19:2])  # Saída: pormr édícl  

`print(frase[::2])  # Saída: pormr édícl`

----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------



### #Análise de Strings

Funções para análise e obtenção de informações sobre strings:

- #len(): Retorna o número de caracteres na string.
    
    `print(len(frase))  # Saída: 19`
    
- #count(): Conta quantas vezes um caractere ou substring aparece.
    
    `print(frase.count("a"))  # Saída: 2 
    `print(frase.count("a", 0, 10))  # Saída: 2`
    
- #find(): Encontra o índice inicial de uma substring. Retorna `-1` se não encontrar.
    
    `print(frase.find("pro"))  # Saída: 0`
    
- #index(): Semelhante ao #find(), mas gera uma exceção se a substring não for encontrada.
    
    `print(frase.index("pro"))  # Saída: 0`
    
- #rfind()**: Encontra o índice inicial da última ocorrência de uma substring. Retorna `-1` se não encontrar.
    
    `print(frase.rfind("i"))  # Saída: 14`
    
- #rindex()**: Semelhante ao #rfind(), mas gera uma exceção se a substring não for encontrada.
    
    `print(frase.rindex("i"))  # Saída: 14`
    
- #startswith()**: Verifica se a string começa com uma substring específica.
    
    `print(frase.startswith("pro"))  # Saída: True`
    
- #endswith()**: Verifica se a string termina com uma substring específica.
    
    `print(frase.endswith("difícil"))  # Saída: True`
    
- #isalnum()**: Verifica se todos os caracteres na string são alfanuméricos.
    
    `print("abc123".isalnum())  # Saída: True`
    
- #isalpha()**: Verifica se todos os caracteres na string são alfabéticos.
    
    
    `print("abc".isalpha())  # Saída: True`
    
- #isdigit()**: Verifica se todos os caracteres na string são dígitos.
    
    
    `print("123".isdigit())  # Saída: True`

----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------


### #Transformação de Strings

Funções para modificar ou transformar strings:

- #replace()**: Substitui uma substring por outra.
    
    
    `nova_frase = frase.replace("programar", "desenvolver") 
    `print(nova_frase)  # Saída: desenvolver é difícil`
    
- #upper()**: Converte a string para maiúsculas.
    
    `print(frase.upper())  # Saída: PROGRAMAR É DIFÍCIL`
    
- #lower()**: Converte a string para minúsculas.
    
    `print(frase.lower())  # Saída: programar é difícil`
    
- #capitalize()**: Coloca a primeira letra da string em maiúscula e o resto em minúsculas.
    
    `print(frase.capitalize())  # Saída: Programar é difícil`
    
- #title()**: Coloca a primeira letra de cada palavra em maiúscula.
    
    `print(frase.title())  # Saída: Programar É Difícil`
    
- #strip()**: Remove espaços extras no início e no fim da string.
    
    `print(frase.strip())  # Saída: programar é difícil`
    
- #lstrip()**: Remove espaços extras no início da string.
    
    `print(frase.lstrip())  # Saída: programar é difícil`
    
- #rstrip()**: Remove espaços extras no fim da string.
    
    `print(frase.rstrip())  # Saída: programar é difícil`
    
- #swapcase()**: Troca maiúsculas por minúsculas e vice-versa.
    
    `print(frase.swapcase())  # Saída: PROGRAMAR É DIFÍCIL`
    
- #zfill()**: Preenche a string com zeros à esquerda até o comprimento especificado.
    
    `print("42".zfill(5))  # Saída: 00042`

----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------


### #Divisão e #Junção de Strings

Funções para dividir e unir strings:

- #split()**: Divide a string em uma lista de palavras.
    
    
    `palavras = frase.split() 
    `print(palavras)  # Saída: ['programar', 'é', 'difícil']`
    
    Acessar palavras específicas:
    
    `print(palavras[2])  # Saída: difícil`
    
- #rsplit()**: Divide a string em uma lista de palavras, mas começa a divisão pela direita.
    
    `palavras = frase.rsplit() 
    `print(palavras)  # Saída: ['programar', 'é', 'difícil']`
    
- #splitlines()**: Divide a string em uma lista de linhas.
    
    
    `multiline = """linha 1`
				`linha 2""" 
	`print(multiline.splitlines()) # Saída: ['linha 1', 'linha 2']
	
- #join(): Junta uma lista de palavras em uma string, com um separador.  
	`print("-".join(palavras))  # Saída: programar-é-difícil`

### Imprimindo Mensagens Longas

Para imprimir mensagens longas, use três aspas:

`print("""Esta é uma mensagem que 
	`será impressa 
	`em várias linhas.""")`