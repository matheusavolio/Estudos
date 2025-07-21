#Fatiamento #strings 

#### 1. **Fatiamento de Strings**

- **Definição**
    - Extração de partes específicas de uma string usando índices.
- **Sintaxe**
    - `string[início:fim:passo]`
- **Exemplos**
    - Fatiamento simples:
        
        
        
        `s = "Hello, World!" 
	        `print(s[0:5])  # Saída: Hello`
        
    - Fatiamento com passo:
        
        
        `print(s[::2])  
	        `# Saída: Hlo ol!`
        
    - Fatiamento reverso:
        

        
        `print(s[::-1])  
	        `# Saída: !dlroW ,olleH`
        

#### 2. **Análise de Strings**

- **Comprimento**
    - `len(string)`
    - Exemplo:
        
        `print(len("Python"))  # Saída: 6`
        
- **Contagem de Substrings**
    - `string.count(substring)`
    - Exemplo:
        
        
        `s = "banana" 
	    `print(s.count('a'))  # Saída: 3`
        
- **Encontrar Substrings**
    - `string.find(substring)`
    - `string.index(substring)`
    - Exemplo:
        
        
        `s = "hello" 
        `print(s.find('e'))  # Saída: 1`
        
- **Verificações de Conteúdo**
    - `string.startswith(prefix)`
    - `string.endswith(suffix)`
    - Exemplo:
        
        
        `s = "hello" 
        `print(s.startswith('he'))  # Saída: True 
        `print(s.endswith('o'))     # Saída: True`
        
- **Verificações de Caracteres**
    - `string.isalpha()`
    - `string.isdigit()`
    - `string.isalnum()`
    - `string.isspace()`
    - Exemplo:
        
        
        `s = "Python3" 
        `print(s.isalpha())  # Saída: False 
        `print("123".isdigit())  # Saída: True`
        

#### 3. **Transformação de Strings**

- **Mudança de Caso**
    - `string.upper()`
    - `string.lower()`
    - `string.capitalize()`
    - `string.title()`
    - `string.swapcase()`
    - Exemplo:
        
        
        `s = "hello world" 
        `print(s.upper())  # Saída: HELLO WORLD 
        `print(s.title())  # Saída: Hello World`
        
- **Remoção de Espaços**
    - `string.strip()`
    - `string.rstrip()`
    - `string.lstrip()`
    - Exemplo:
        
        
        `s = "  hello  " 
        `print(s.strip())  # Saída: "hello"`
        
- **Substituição**
    - `string.replace(old, new)`
    - Exemplo:
        
        `s = "hello world" 
        `print(s.replace("world", "Python"))  # Saída: hello Python`
        

#### 4. **Divisão de Strings**

- **Divisão Simples**
    - `string.split(separator)`
    - Exemplo:
        
        `s = "hello world" 
        `print(s.split())  # Saída: ['hello', 'world']`
        
- **Divisão em Linhas**
    - `string.splitlines()`
    - Exemplo:
        
        
        `s = "hello\nworld" 
        `print(s.splitlines())  # Saída: ['hello', 'world']`
        
- **Divisão em Partes Específicas**
    - `string.partition(separator)`
    - `string.rpartition(separator)`
    - Exemplo:
        
        
        `s = "hello world" 
        `print(s.partition(" "))  # Saída: ('hello', ' ', 'world')`


### Exemplos de Código

# Fatiamento de Strings
`# Fatiamento simples 
`s = "Hello, World!" 
`print(s[0:5])  # Saída: Hello  
`# Fatiamento com passo 
`print(s[::2])  # Saída: Hlo ol!  
`# Fatiamento reverso 
`print(s[::-1])  # Saída: !dlroW ,olleH`


# Análise de Strings
`# Comprimento 
`print(len("Python"))  # Saída: 6  

`# Contagem de substrings 
`s = "banana" 
`print(s.count('a'))  # Saída: 3  
`
`# Encontrar substrings 
`s = "hello" 
`print(s.find('e'))  # Saída: 1  
`
`# Verificações de conteúdo 
`s = "hello" 
`print(s.startswith('he'))  # Saída: True 
`print(s.endswith('o'))     # Saída: True  

`# Verificações de caracteres 
`s = "Python3" 
`print(s.isalpha())  # Saída: False 
`print("123".isdigit())  # Saída: True`

# Transformação de Strings

`# Mudança de caso 
`s = "hello world" 
`print(s.upper())  # Saída: HELLO WORLD 
`print(s.title())  # Saída: Hello World  

`# Remoção de espaços 
`s = "  hello  " 
`print(s.strip())  # Saída: "hello"  

`# Substituição 
`s = "hello world" 
`print(s.replace("world", "Python"))  # Saída: hello Python`

# Divisão de Strings
`# Divisão simples 
`s = "hello world" 
`print(s.split())  # Saída: ['hello', 'world']  

`# Divisão em linhas 
`s = "hello\nworld" p
`print(s.splitlines())  # Saída: ['hello', 'world']  

`# Divisão em partes específicas 
`s = "hello world" 
`print(s.partition(" "))  # Saída: ('hello', ' ', 'world')`