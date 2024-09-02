#tuplas 
### #TuplasEmPython

#### 1. **Criação de #Tuplas**

- **Sintaxe Básica**:
    - `tupla = (1, 2, 3)`
- #TuplaVazia:
    - `tupla_vazia = ()`
- **Tupla de um Único Elemento**:
    - `tupla_unica = (1,)`

#### 2.  #AcessoAElementos

- **Por Índice**:
    - `tupla[0]`
- **Fatiamento**:
    - `tupla[1:3]`
- **Desempacotamento**:
    - `a, b, c = tupla`

#### 3. #Imutabilidade

- **Característica**:
    - Tuplas não podem ser modificadas após a criação.
- **Exceção**:
    - Tentativa de modificação gera erro (`TypeError`).

#### 4. #MétodosDeTuplas

- **Contagem**:
    - `tupla.count(x)`
- **Índice**:
    - `tupla.index(x)`

#### 5. #OperaçõesComTuplas

- **Concatenar**:
    - `tupla1 + tupla2`
- **Repetir**:
    - `tupla * 3`
- **Pertencimento**:
    - `x in tupla`
- **Comprimento**:
    - `len(tupla)`

#### 6. #UsosComunsTuplas

- **Retornar múltiplos valores de uma função**:
    - `return (a, b)`
- **Agrupar dados relacionados**:
    - `dados = (nome, idade, sexo)`
- **Usar como chaves em dicionários** (se as tuplas contêm elementos imutáveis):
    - `dicionario[(chave1, chave2)] = valor`
- **Iterar em loops**:
    - `for item in tupla:`

#### 7. #ComparaçãoComListas

- **Mutabilidade**:
    - Listas são mutáveis, tuplas são imutáveis.
- **Sintaxe**:
    - Listas: `[]`
    - Tuplas: `()`
- **Desempenho**:
    - Tuplas podem ser mais rápidas em algumas operações devido à imutabilidade.

### #MapaMentalTuplas

Você pode visualizar este mapa mental com um nó central "Tuplas em Python" e ramificações principais para cada uma das categorias mencionadas. Cada ramificação principal pode se dividir em sub-ramificações conforme necessário:



                      `Tuplas em Python                            /       \           Criação de Tuplas        Acesso a Elementos          /      |      \               /         \   Básica   Vazia    Única         Índices    Fatiamento                                               \                                           Desempacotamento        |                                        |   Imutabilidade                      Métodos de Tuplas        |                                      /        \   Característica                  Contagem   Índice        |                                        |   Tentativa de modificação   Operações com Tuplas          gera erro                    /   |   |    \                                      +    *   in   len                                          |                                     Usos Comuns                            /        |          |          \              Retornar   Agrupar    Chaves em  Iterar              múltiplos   dados    dicionários  em loops              valores    relacionados   |                                       |                            Comparação com Listas                            /           |            \                  Mutabilidade  Sintaxe     Desempenho`



`# Criação de tupla 
`minha_tupla = (10, 20, 30, 40) 

`#  Acesso a elementos 
`print(minha_tupla[1])  # Saída: 20 
`print(minha_tupla[-1]) # Saída: 40 

`# Fatiamento 
`print(minha_tupla[1:3]) # Saída: (20, 30) 

`# Desempacotamento
`a, b, c, d = minha_tupla 
`print(a, b, c, d) # Saída: 10 20 30 40  

`# Métodos 
`print(minha_tupla.count(20)) # Saída: 1 
`print(minha_tupla.index(30)) # Saída: 2  

`# Operações 
`nova_tupla = minha_tupla + (50, 60) 
`print(nova_tupla) # Saída: (10, 20, 30, 40, 50, 60)  
`repeticao_tupla = minha_tupla * 2 
`print(repeticao_tupla) # Saída: (10, 20, 30, 40, 10, 20, 30, 40)`