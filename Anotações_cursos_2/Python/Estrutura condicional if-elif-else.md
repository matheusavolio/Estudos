## Estrutura Condicional em Python

### 1. **Introdução**

As estruturas condicionais em Python permitem executar diferentes blocos de código com base em certas condições. A principal estrutura condicional em Python é a instrução #if

### 2. #If 

A instrução `if` avalia uma condição e, se for verdadeira, executa um bloco de código.


`if condição:     
	`` bloco de código a ser executado se a condição for verdadeira`


`idade = 18 if idade >= 18:     print("Você é maior de idade.")`

### 3. #Else

A instrução `else` é usada em conjunto com o `if` para executar um bloco de código quando a condição do `if` é falsa.



`if condição:     
	`bloco de código a ser executado se a condição for verdadeira
`else:     
	`bloco de código a ser executado se a condição for falsa`

# Exemplo:
`idade = 16 
`if idade >= 18:     
	`print("Você é maior de idade.") 
`else:     
	`print("Você é menor de idade.")`

### 4. #Elif

A instrução `elif` (abreviação de "else if") permite verificar múltiplas condições. É usada após um `if` ou outro `elif` e antes de um `else`.



`if condição1:     
``	bloco de código a ser executado se condição1 for verdadeira 
`elif condição2:     
``	bloco de código a ser executado se condição2 for verdadeira
`else:    
``	 bloco de código a ser executado se todas as condições anteriores forem falsas`

# Exemplo:

`nota = 85 
`if nota >= 90:     
	`print("A")
`elif nota >= 80:     
	`print("B") 
`elif nota >= 70:     
	`print("C") 
`else:     
	`print("F")`

### 5. #CondicionaisAninhadas

Você pode aninhar condicionais para verificar condições adicionais dentro de um bloco de código.

# Exemplo:


`idade = 20 
`sexo = "Feminino"  
`if idade >= 18:     
``	if sexo == "Masculino":         
``		print("Você é um homem adulto.")     
``	else:         
``		print("Você é uma mulher adulta.") 
`else:  
	`print("Você é menor de idade.")`

### 6. #ExpressõesCondicionais #OperadorTernário

Python suporta uma forma concisa de escrever condicionais usando o operador ternário.


`variável = valor1 if condição else valor2`

# Exemplo:

`idade = 18 
`status = "maior de idade" if idade >= 18 else "menor de idade" 
`print(status)`

### 7. #CombinaçãoDeCondicionais

Você pode combinar múltiplas condições usando operadores lógicos ( #and #or #not)

# Exemplo:

`idade = 18 
`tem_carteira = True 
`if idade >= 18 and tem_carteira:    
``	print("Você pode dirigir.") 
`else:    
``	print("Você não pode dirigir.")`