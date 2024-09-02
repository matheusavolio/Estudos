#EstruturasDeRepetição #While-for #while #for 


#### 1. **Loops em Python**

- **`for` loop**
- **`while` loop**

#### 2. **`for` loop**

- **Iteração sobre Sequências**
    - Listas
    - Tuplas
    - Strings
    - Dicionários
    - Conjuntos


- **Sintaxe**
    
    `for item in sequencia:    
     `# bloco de código`


- **Funções Úteis**
    - `range(start, stop, step)`
    - `enumerate(iterable, start=0)`
    - `zip(*iterables)`

#### 3. **`while` loop**

- **Repetição Condicional**
    - Continua enquanto a condição for verdadeira


- **Sintaxe**
    
    
    `while condição:     
	    `# bloco de código`
    

#### 4. **Controle de Fluxo**

- **`break`**
    - Interrompe o loop
- **`continue`**
    - Pula para a próxima iteração do loop
- **`else` com loops**
    - Executado se o loop não for interrompido por `break`

#### 5. **Loops Aninhados**

- **`for` dentro de `for`**
    
    
    `for i in range(3):     
	    `for j in range(3):         
		    `# bloco de código`
    
- **`while` dentro de `while`**
    
    
    `while condição1:     
	    `while condição2:        
	     `# bloco de código`
    

#### 6. **Compreensões**

- **List Comprehensions**
    
    
    `[expressão for item in iterável if condição]`
    
- **Dict Comprehensions**
    
    
    `{chave: valor for item in iterável if condição}`
    
- **Set Comprehensions**
    
    
    `{expressão for item in iterável if condição}`
    
- **Generator Expressions**
    
    
    `(expressão for item in iterável if condição)`
    

#### 7. **Exemplos Práticos**

- **Iteração sobre Lista**
    
    
    `for item in [1, 2, 3]:     
	    `print(item)`
    
- **Iteração Condicional**
    
    
    `x = 0 while x < 5:
         `print(x)     
         `x += 1`
    
- **Uso de `break` e `continue`**
    
    
    `for i in range(10):
	`if i == 5:         
		`` break     
        `if i % 2 == 0:         
	       ``  continue     
		`print(i)`
    
- **List Comprehension**
    
    
    `[x**2 for x in range(10) if x % 2 == 0]`
    

### 
### Exemplos de Código



#### `for` loop


`# Iteração sobre uma lista lista = [1, 2, 3] 
`for item in lista:     
	`print(item)  
	
`# Uso de range 
`for i in range(5):     
	`print(i)  
	
`# Enumerate 
`palavra = "python" 
`for index, letra in enumerate(palavra):     
	`print(index, letra)  

#` Zip 
`nomes = ["Ana", "João", "Maria"] 
`idades = [25, 30, 22] 
`for nome, idade in zip(nomes, idades):     
	`print(f"{nome} tem {idade} anos")`



`while` loop

`# Repetição condicional
`x = 0 
`while x < 5:     
	`print(x)     
	`x += 1`


#### Controle de Fluxo

`# Uso de break e continue 
`for i in range(10):     
	`if i == 5:         
		`break    
	`if i % 2 == 0:        
		`continue    
	`print(i)  



#` Uso de else com loop 
`for i in range(5):     
	`print(i) 
`else:     
	`print("Loop concluído sem interrupção")`