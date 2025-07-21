#EstruturaCondicional 
#If-Elif-Else 

### Estruturas Condicionais em Python

#### 1. **Estrutura Básica**

- **`if`**: Condição simples
    
    
    `if condição:
	    `bloco de código`
    
- **`else`**: Alternativa quando a condição é falsa
    
    
	
`if condição:    
    `bloco de código
 `else:     
	 `` bloco de código alternativo`
    

#### 2. **Condições Múltiplas**

- **`elif`**: Condições adicionais entre `if` e `else`
    
    
    `if condição1:
        `# bloco de código 
    `elif condição2:     
        `# bloco de código 
    `else:     
        `` # bloco de código`
    
- **`else`**: Padrão para condições não cobertas por `if` e `elif`

#### 3. #OperadoresDeComparação

- **Igual a**: `==`
- **Diferente de**: `!=`
- **Maior que**: `>`
- **Menor que**: `<`
- **Maior ou igual a**: `>=`
- **Menor ou igual a**: `<=`

#### 4. #OperadoresLógicos

- **E (AND)**: `and`
- **Ou (OR)**: `or`
- **Não (NOT)**: `not`

#### 5. #EstruturasAninhadas**

- **`if` dentro de `if`**
    
    
	
    `if condição1:
         `if condição2:         
         `# bloco de código`
    
- **`if` dentro de `else`**
    
    python
    
    Copiar código
    
    `if condição1:     
	    `bloco de código 
	`else:     
	    `if condição2:        
	     `bloco de código`
    

#### 6. #CompreensõesCondicionais**

- **List Comprehensions**:
    

    
    `lista = [x for x in range(10) if x % 2 == 0]`
    
- **Dicionário Comprehensions**:
    
    
    `dicionario = {x: x**2 for x in range(5) if x % 2 == 0}`
    

#### 7. **Exemplos Práticos**

- **Verificação de Maioridade**:
    
    
    `idade = 18 
    `if idade >= 18:
	    `print("Você é maior de idade.") 
    `else:     
	    `print("Você é menor de idade.")`
    
- **Classificação de Nota**:
    
    
    `nota = 85 
    `if nota >= 90:     
	    `print("A") 
    `elif nota >= 80:     
	    `print("B") 
    `elif nota >= 70:     
	    `print("C") 
    `else:     
	    `print("D")`
    



### Exemplo de Código Completo

Aqui está um exemplo que usa várias estruturas condicionais:


`idade = int(input("Digite sua idade: "))  
`if idade >= 18:     
	`print("Você é maior de idade.")    
	 `if idade >= 65:         
		`` print("Você é um idoso.") 
`elif idade >= 13:     
	`print("Você é um adolescente.") 
`else:     
	`print("Você é uma criança.")  



# Exemplo completo:

`valor_saque = int(input("Digite o valor do saque (entre 10 e 600 reais): "))
`if valor_saque < 10 or valor_saque > 600:
    `print("Valor inválido. O valor deve estar entre 10 e 600 reais.")
`else:
    `notas = [100, 50, 10, 5, 1]
    `quantidade_notas = {}
    `for nota in notas:
        `quantidade_notas[nota] = valor_saque // nota
        `valor_saque = valor_saque % nota
    `print("Notas fornecidas:")
    `for nota in notas:
        `if quantidade_notas[nota] > 0:
            `print(f"{quantidade_notas[nota]} nota(s) de R${nota}")




# Análise de código:

`# Solicita ao usuário o valor do saque 
`valor_saque = int(input("Digite o valor do saque (entre 10 e 600 reais): "))`

1. **Entrada do Valor do Saque:**
    - `valor_saque = int(input("Digite o valor do saque (entre 10 e 600 reais): "))`
        - `input(...)`: Solicita ao usuário que digite um valor.
        - `int(...)`: Converte a entrada do usuário (que é uma string) para um inteiro.
        - `valor_saque` armazena o valor do saque fornecido pelo usuário.



`# Verifica se o valor do saque está dentro do intervalo permitido 
`if valor_saque < 10 or valor_saque > 600:
	`print("Valor inválido. O valor deve estar entre 10 e 600 reais.")`

2. **Validação do Valor do Saque:**
    - `if valor_saque < 10 or valor_saque > 600:`
        - Verifica se o valor do saque está fora do intervalo permitido (menos de 10 reais ou mais de 600 reais).
    - `print("Valor inválido. O valor deve estar entre 10 e 600 reais.")`
        - Se a condição for verdadeira, imprime uma mensagem de erro informando que o valor é inválido.


`else:     
	`# Define as notas disponíveis     
	`notas = [100, 50, 10, 5, 1]`

3. **Bloco `else`:**
    - Se o valor do saque está dentro do intervalo permitido, o código dentro do bloco `else` é executado.
    - `notas = [100, 50, 10, 5, 1]`
        - Define a lista `notas` com as denominações das notas disponíveis (100, 50, 10, 5 e 1 real).


    `# Armazena a quantidade de cada nota     
    `quantidade_notas = {}`

4. **Inicialização do Dicionário `quantidade_notas`:**
    - `quantidade_notas = {}`
        - Inicializa um dicionário vazio para armazenar a quantidade de cada nota.



    `# Calcula a quantidade de cada nota     
    `for nota in notas:         
	    `quantidade_notas[nota] = valor_saque // nota         
	    `valor_saque = valor_saque % nota`

5. **Cálculo da Quantidade de Cada Nota:**
    - `for nota in notas:`
        - Itera sobre cada valor de nota na lista `notas`.
    - `quantidade_notas[nota] = valor_saque // nota`
        - Calcula quantas notas de valor `nota` podem ser fornecidas com o valor atual do saque. Isso é feito utilizando a divisão inteira (`//`).
    - `valor_saque = valor_saque % nota`
        - Atualiza o valor do saque restante após subtrair o valor das notas fornecidas. Isso é feito utilizando o operador módulo (`%`), que retorna o restante da divisão.



    `# Exibe o resultado     
    `print("Notas fornecidas:")    
     `for nota in notas:        
		`if quantidade_notas[nota] > 0:             
			`print(f"{quantidade_notas[nota]} nota(s) de R${nota}")`

6. **Impressão do Resultado:**
    - `print("Notas fornecidas:")`
        - Imprime um cabeçalho indicando que o próximo texto será sobre as notas fornecidas.
    - `for nota in notas:`
        - Itera sobre cada valor de nota na lista `notas`.
    - `if quantidade_notas[nota] > 0:`
        - Verifica se a quantidade de notas dessa denominação é maior que zero. Isso é feito para evitar a impressão de denominações que não foram usadas.
    - `print(f"{quantidade_notas[nota]} nota(s) de R${nota}")`
        - Imprime a quantidade de notas para cada denominação que foi usada, formatando a saída de acordo com a quantidade e o valor da nota.

### Resumo

1. **Entrada e Validação:** O código começa solicitando um valor de saque ao usuário e valida se ele está dentro do intervalo permitido.
2. **Processamento:** Se o valor for válido, o código calcula quantas notas de cada denominação são necessárias para o saque.
3. **Saída:** Finalmente, o código imprime a quantidade de cada nota fornecida ao usuário.