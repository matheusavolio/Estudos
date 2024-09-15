#EstruturaSequencial #OperadoresAritméticos #variáveis #tipos #OperadoresDeComparação 
#OperadoresLógicos #Condicionais #Repetição #Funções #Comentarios 

#### 1.  #ConceitoDeEstruturaSequencial

- **Definição**: Execução de instruções na ordem em que aparecem.
- **Características**: Simples e direta; não há ramificação ou repetição.

---

#### 2.  #VariáveisETiposDeDados

- **Definição de Variáveis**: Espaços na memória para armazenar dados.
- **Tipos de Dados**:
    - **Numéricos**: `int`, `float`
    - **Texto**: `str`
    - **Booleanos**: `bool`
    - **Exemplo**:
        
        python
        
        Copiar código
        
        `idade = 25                # int 
        `altura = 1.75             # float 
        `nome = "João"            # str 
        `casado = False           # bool`
        

---

####  3. #Operadores

-  #Aritméticos: `+`, `-`, `*`, `/`, `//`, `%`, `**`
    - **Exemplo**:
        
        `soma = 5 + 3          # 8 
        `produto = 4 * 7      # 28`
        
-  #Comparação: `==`, `!=`, `>`, `<`, `>=`, `<=`
    - **Exemplo**:
        
        `resultado = (5 > 3)  # True`
        
-  #Lógicos: `and`, `or`, `not`
    - **Exemplo**:

        `verdadeiro = (5 > 3) and (8 < 10)  # True`
        

---

#### 4.  #EntradaESaídaDeDados

- #Entrada:
    - `input()`: Captura dados do usuário.
    - **Exemplo**:
        

        
        `nome = input("Digite seu nome: ") 
        `idade = int(input("Digite sua idade: "))`
        
-  #Saída:
    - `print()`: Exibe dados na tela.
    - **Exemplo**:
        
        `print(f"Olá, {nome}. Você tem {idade} anos.")`
        

---

#### 5. #ControleDeFluxoBásico

- #Condicionais: `if`, `elif`, `else`
    - **Exemplo**:
        
        
        `idade = 18 
        `if idade < 18:     
	        `print("Menor de idade") 
	    `elif idade == 18:    
			`print("Tem 18 anos") 
		`else:     
			`print("Maior de idade")`
        

---

#### 6.  #EstruturasDeRepetição

- **`for` Loop**: Itera sobre uma sequência.
    - **Exemplo**:
        
        
        
        `for i in range(5):     
	        `print(i)`
        
- **`while` Loop**: Continua enquanto a condição for verdadeira.
    - **Exemplo**:
        
        `contador = 0 
        `while contador < 5:     
	        `print(contador)    
	        `contador += 1`
        

---

#### 7. #Funções

- **Definição e Uso**: Blocos de código reutilizáveis.
    - **Exemplo**:
        
        `def saudacao(nome):     
	        `return f"Olá, {nome}!"  
	 `mensagem = saudacao("Maria") 
	 `print(mensagem)`
        
- **Parâmetros e Retorno**:
    - **Exemplo**:
        
        
        `def soma(a, b):     
	        `return a + b  
	    `resultado = soma(10, 5) 
	    `print(resultado)  # 15`
        

---

#### 8. #ComentáriosEDocumentação

- **Comentários**: `# Comentário de linha única`
    - **Exemplo**:
        
        `# Este é um comentário`
        
- **Docstrings**: `""" Comentário de múltiplas linhas """`
    - **Exemplo**:
        

        
        `def funcao():     
	        `"""Esta função faz algo."""    
	        `` pass`
        

---

#### 9. #ExemplosCompletos

- **Programa Simples**:
    
    
    `# Entrada de dados 
    `nome = input("Digite seu nome: ") 
    `idade = int(input("Digite sua idade: "))  
    
    `# Processamento 
    `if idade < 18:     
	    `status = "Menor de idade" 
	`else:     
		`status = "Maior de idade"  
	
	`# Saída de dados 
	`print(f"Olá, {nome}. Você é {status}.")`
    
- **Função com Loop**:
    
    
    `def tabuada(n):     
	    `for i in range(1, 11):         
		    `print(f"{n} x {i} = {n * i}")  
		
	`numero = int(input("Digite um número para a tabuada: ")) 
	`tabuada(numero)`
    

---

### Resumo Visual

1. **Conceito Sequencial** → Execução linear de instruções.
2. **Variáveis e Tipos** → `int`, `float`, `str`, `bool`.
3. **Operadores** → Aritméticos, Comparação, Lógicos.
4. **Entrada e Saída** → `input()`, `print()`.
5. **Condicionais** → `if`, `elif`, `else`.
6. **Repetição** → `for`, `while`.
7. **Funções** → Definição, Parâmetros, Retorno.
8. **Comentários** → `#`, `""" """`.
9. **Exemplos** → Programas práticos demonstrando conceitos.