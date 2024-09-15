
#### **1. Introdução**

- **Erro vs Exceção:**
    - **Erro:** Problema no código que impede sua execução.
    - **Exceção:** Evento que interrompe o fluxo normal do programa.
- **Finalidade:** Manter o fluxo do programa mesmo quando surgem problemas.

#### **2. Tipos de Erros Comuns**

- **SyntaxError:** Erro na sintaxe do código.
- **IndentationError:** Erro de indentação.
- **TypeError:** Operação realizada em tipos de dados incompatíveis.
- **NameError:** Uso de uma variável que não foi definida.
- **ValueError:** Função recebe um argumento com valor inapropriado.
- **IndexError:** Tentativa de acessar um índice inexistente em uma lista.
- **KeyError:** Tentativa de acessar uma chave inexistente em um dicionário.
- **AttributeError:** Tentativa de acessar um atributo que um objeto não possui.
- **IOError:** Erros de entrada e saída, como ao tentar abrir um arquivo inexistente.

#### **3. Bloco try-except**

- **Estrutura Básica:**
    
    ```python
    try:     
	    # Código que pode gerar uma exceção 
	except TipoDeExceção:     
		# Código a ser executado em caso de exceção`
    ```
- **Múltiplos except:**
    
    
```python
try:     
    # Código que pode gerar exceções 
except TipoDeExceção1:     
	# Tratamento para TipoDeExceção1 
except TipoDeExceção2:     
	# Tratamento para TipoDeExceção2
````
    
- **Captura de Exceções Genéricas:**
    
    
```python
try:     
    # Código que pode gerar exceções 
except Exception as e:     
	print(f"Ocorreu um erro: {e}")`
```
    
- **Exemplo:**
    
    ```python
    try:     
	    resultado = 10 / 0 
	except ZeroDivisionError:     
		print("Não é possível dividir por zero.")`

```
    

#### **4. Bloco else**

- **Uso:**
    - Executa código se nenhuma exceção for levantada.
- **Exemplo:**
    
    ```python
    try:     
	    resultado = 10 / 2 
	except ZeroDivisionError:     
		print("Não é possível dividir por zero.") 
	else:     
		print("Divisão realizada com sucesso:", resultado)`
    
```

#### **5. Bloco finally**

- **Uso:**
    - Executa código independente da ocorrência de exceções.
- **Exemplo:**
    
    ```python
    try:     
	    arquivo = open("meuarquivo.txt", "r") 
	except FileNotFoundError:     
		print("Arquivo não encontrado.") 
	finally:     
		print("Execução finalizada.")`
    
```

#### **6. Levantando Exceções**

- **Uso do comando raise:**
    - Levanta uma exceção manualmente.
- **Exemplo:**
    
```python
    
    x = -5 if x < 0:     
	    raise ValueError("O valor não pode ser negativo")`
    
```

#### **7. Definindo Exceções Personalizadas**

- **Criando uma classe de exceção:**
    
    
  ```python
  class MinhaExcecao(Exception):     
	  pass  
  def verificar_valor(x):     
	  if x < 0:         
		  raise MinhaExcecao("Valor negativo não é permitido")`
```

#### **8. Uso de try-except aninhado**

- **Estrutura:**
    
```python
    
    `try:     
	    # Bloco externo     
	    try:         
		    # Bloco interno     
		except ExcecaoInterna:         
			# Tratamento da exceção interna 
	except ExcecaoExterna:     
		# Tratamento da exceção externa`
    
```

#### **9. Considerações Finais**

- **Boas Práticas:**
    - Evite capturar exceções genéricas, sempre que possível.
    - Mantenha o bloco try-except o mais específico possível.
    - Use finally para liberar recursos, como fechar arquivos ou conexões de rede.
    - Documente suas exceções personalizadas para facilitar a manutenção do código.