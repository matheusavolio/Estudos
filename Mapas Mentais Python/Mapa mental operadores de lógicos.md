### Mapa Mental: Operadores Lógicos em Python

#### 1. #and Lógico (`and`)

- **Descrição**: Retorna True se ambos os operandos forem verdadeiros.
    
- **Exemplo**:
    
    
    `x = True 
    `y = False 
    `print(x and y)  # Saída: False`
    

#### 2. #or Lógico (`or`)

- **Descrição**: Retorna True se pelo menos um dos operandos for verdadeiro.
    
- **Exemplo**:
    
    `x = True 
    `y = False 
    `print(x or y)  # Saída: True`
    

#### 3. #not Lógico (`not`)

- **Descrição**: Retorna True se o operando for falso e False se o operando for verdadeiro.
    
- **Exemplo**:
    
    
    `x = True 
    `print(not x)  # Saída: False`
    

#### 4. #xor Lógico (`^`)

- **Descrição**: Retorna True se exatamente um dos operandos for verdadeiro.
    
- **Exemplo**:
    
    
    `x = True 
    `y = False 
    `print(x ^ y)  # Saída: True`
    

### Exemplos Adicionais

#### #and Lógico com Comparações

- **E Lógico (`and`)**: Verifica múltiplas condições.
    
    
    `a = 5 
    `b = 10 
    `print(a > 0 and b < 20)  # Saída: True`
    

#### #or Lógico com Comparações

- **Ou Lógico (`or`)**: Verifica se pelo menos uma das condições é verdadeira.
    
    
    `a = 5 
    `b = 25 
    `print(a > 0 or b < 20)  # Saída: True`
    

#### #not Lógico com Comparações

- **Não Lógico (`not`)**: Inverte o resultado de uma condição.
    
    
    `a = 5 
    `print(not (a > 0))  # Saída: False`
    

#### #Xor Lógico com Comparações

- **Xor Lógico (`^`)**: Verifica se exatamente uma das condições é verdadeira.
    
    
    `a = True 
    `b = False 
    `print(a ^ b)  # Saída: True`