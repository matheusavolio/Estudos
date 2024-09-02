#Dicionários

Nas #Listas, para acessarmos algum elemento dela, iteramos sobre os índices, por exemplo:
`my_list = ["hamburguer", "suco", "pizza", "pudim"]
`print(my_list[0])
```output
hamburguer
```

Já nos #Dicionários podemos acessar esses elementos através de literais (strings) ao invés de índices. Podemos então personalizar os índices

# Por exemplo:
`dicionario = {"índice":"elemento"}`
se for definir mais de um índice e elemento, separar por vírgulas, então ficaria assim:
`dicionario = {"índice":"elemento", "idade":25}`
a esquerda dos " : " fica o nome do índice, e a direita dos " : " fica o elemento

Exemplo prático:
`dados = {"nome":"pedro", "idade": 25}
`print(dados["nome"])
```output
pedro
```


para adicionarmos um elemento no final, podemos fazer assim:
`dados = {"nome":"pedro", "idade": 25}
`dados["sexo] = "m"
então nosso dicionário ficaria assim:
`dados = {"nome":"pedro", "idade": 25, "sexo": "m"}


E para removermos elementos utilizamos o #del 
`dados = {"nome":"pedro", "idade": 25}
`print(dados)
`dados["sexo"] = "m"
`print(dados)
`del dados["idade"]
`print(dados)
o output ficaria assim:
```output
{'nome': 'pedro', 'idade': 25}
{'nome': 'pedro', 'idade': 25, 'sexo': 'm'}
{'nome': 'pedro', 'sexo': 'm'}
```

Vamos fazer um outro exemplo:

`filme = {"titulo":"Star Wars",
			`"ano":1977,
			`"diretor":"George Lucas"
			`}

Nesse exemplo, temos a estrutura de dados filme, os índices titulo, ano e diretor, com os elementos de star wars, 1977 e george lucas.

e se usarmos o
`print(filme.values())`
será impressos todos os elementos, que no caso dos dicionários são chamados de valores

e para acessar os índices, utilizamos o 
`print(filme.keys())`
será impresso os índices, que no dicionário são conhecidos como chaves

e para pegar todos os valores, tanto as chaves quanto os valores, utilizamos o 
`print(filme.items())`

`values() = imprime os valores(os elementos)
`keys() = imprime as chaves(os índices)`
`items() = imprime todos as chaves com seus respectivos valores`

e podemos utilizar as funções acima para #iterar sobre os #dicionários, é parecido com o uso do #enumerate

`for k, v in filme.items():
    `print(f"O {k} é {v}"
```output
O titulo é Star Wars
O ano é 1977
O diretor é George Lucas
```

Podemos misturar listas, tuplas e dicionários:
`filme = {"titulo":"Star Wars",
            `"ano":1977,
            `"diretor":"George Lucas"}

`filme1 = {"titulo":"avengers",
          `"ano":2012,
          `"diretor":"joss whedon"}

`filme2 = {"titulo":"matrix",
          `"ano":2012,
          `"diretor":"wachowski"}
          
`lista = []
`lista.append(filme)
`lista.append(filme1)
`lista.append(filme2)

`print(f"índice 0 da lista é o dicionario filme {lista[0]}")
`print(f"Índice 1 da lista é o dicionario filme1 {lista[1]}")
`print(f"Índice 2 da lista é o dicionario filme2 {lista[2]}")
`print(f"A lista inteira é dividida pelos respectivos dicionários: {lista}")
```output
índice 0 da lista é o dicionario filme {'titulo': 'Star Wars', 'ano': 1977, 'diretor': 'George Lucas'}
Índice 1 da lista é o dicionario filme1 {'titulo': 'avengers', 'ano': 2012, 'diretor': 'joss whedon'}
Índice 2 da lista é o dicionario filme2 {'titulo': 'matrix', 'ano': 2012, 'diretor': 'wachowski'}
A lista inteira é dividida pelos respectivos dicionários: [{'titulo': 'Star Wars', 'ano': 1977, 'diretor': 'George Lucas'}, {'titulo': 'avengers', 'ano': 2012, 'diretor': 'joss whedon'}, {'titulo': 'matrix', 'ano': 2012, 'diretor': 'wachowski'}]
```

E utilizando o mesmo exemplo acima, podemos iterar sobre a lista para imprimir seus elementos

`for k, v in enumerate(lista):
    `print(f"Localização do dicionário: {k} e seus items: {v}")
```output
Localização do dicionário: 0 e seus items: {'titulo': 'Star Wars', 'ano': 1977, 'diretor': 'George Lucas'}
Localização do dicionário: 1 e seus items: {'titulo': 'avengers', 'ano': 2012, 'diretor': 'joss whedon'}
Localização do dicionário: 2 e seus items: {'titulo': 'matrix', 'ano': 2012, 'diretor': 'wachowski'}    
```


para imprimir corretamente, pode esquecer de utilizar aspas(se estiver usando aspas duplas para a string, utilizar aspas simples para os colchetes) dentro dos colchetes
`pessoas = {"nome":"Matheus",
	          `"idade":19,
	          `` "sexo":"Masculino"}
`print(f"O {pessoas['nome']} tem {pessoas['idade']} anos")
```output
O Matheus tem 19 anos
```


utilizando o `.keys()
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`print(pessoas.keys())
```output
dict_keys(['nome', 'idade', 'sexo'])
```

Utilizando o `.values()`
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`print(pessoas.keys())
```output
dict_values(['Matheus', 19, 'Masculino'])
```

Utilizando o `.items()`
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`print(pessoas.items())
```output
dict_items([('nome', 'Matheus'), ('idade', 19), ('sexo', 'Masculino')])
```

Iteração com os dicionários(`.keys()`)
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`for k in pessoas.keys():
	`print(k)
```output
nome
idade
sexo
```

Iteração com os dicionários (`.values()`)
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`for k in pessoas.values():
	`print(k)
```output
Matheus
19
Masculino
```


Iteração com os dicionários (`.items()`)
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`for k in pessoas.items():
	`print(k)
```output
('nome', 'Matheus')
('idade', 19)        
('sexo', 'Masculino')
```


f print na iteração com (`.items()`)
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
`for k, v in pessoas.items():
	`print(f"{k} = {v}")`
```output
nome = Matheus
idade = 19      
sexo = Masculino
```


substituindo um valor de dentro de um dicionário
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
 `pessoas["nome"] = 'Lucas'
`for k, v in pessoas.items():
	`print(f"{k} = {v}")`
```output
nome = Lucas
idade = 19      
sexo = Masculino
```


também podemos adicionar novas chaves e valores a um dicionário
`pessoas = {"nome":"Matheus",
           `"idade":19,
           `"sexo":"Masculino"}
 `pessoas["peso"] = '98'
`for k, v in pessoas.items():
	`print(f"{k} = {v}")`



dicionários dentro de uma lista
`estado1 = {"uf":"Rio de Janeiro",
	         `` "silga":"RJ"}

`estado2 = {"uf":"São Paulo",
	           `"silga":"SP"}

`brasil = []
`brasil.append(estado1)
`brasil.append(estado2)
`print(f" dicionário 0: {estado1}")
`print(f" dicionário 1: {estado2}")
`print(f"Lista com os dicionários: {brasil}")
```output
dicionário 0: {'uf': 'Rio de Janeiro', 'silga': 'RJ'}
 dicionário 1: {'uf': 'São Paulo', 'silga': 'SP'}
Lista com os dicionários: [{'uf': 'Rio de Janeiro', 'silga': 'RJ'}, {'uf': 'São Paulo', 'silga': 'SP'}]
```


iteração dos dicionário dentro de uma lista
`estado1 = {"uf":"Rio de Janeiro",
	         `` "silga":"RJ"}

`estado2 = {"uf":"São Paulo",
	           `"silga":"SP"}

`brasil = []
`brasil.append(estado1)
`brasil.append(estado2)
`print(f"Lista com os dicionários: {brasil[0]}")
```output
Lista com os dicionários: {'uf': 'Rio de Janeiro', 'silga': 'RJ'}
```

iteração dos dicionário dentro de uma lista
`estado1 = {"uf":"Rio de Janeiro",
	         `` "silga":"RJ"}

`estado2 = {"uf":"São Paulo",
	           `"silga":"SP"}

`brasil = []
`brasil.append(estado1)
`brasil.append(estado2)
`print(f"Lista com os dicionários: {brasil[0]['uf']}")
```output
Lista com os dicionários: Rio de Janeiro
```


Copiando elementos de um dicionário para adicionar eles á uma lista e utilizando o input nos dicionários
`estado = {}
`brasil = []
`dados = []
`for c in range(0, 3):
    `estado['uf'] = str(input("Unidade Federativa: "))
    `estado['sigla'] = str(input("Sigla: "))
    `dados.append(estado.copy())
    `brasil.append(dados.copy())
    `dados.clear()
`print(brasil)
```output
[[{'uf': 'Minas Gerais', 'sigla': 'MG'}], [{'uf': 'Paraná', 'sigla': 'PR'}], [{'uf': 'Acre', 'sigla': 'AC'}]]
```



Copiando elementos de um dicionário para adicionar eles á uma lista, utilizando o input nos dicionários e utilizando o for para imprimir os items separados
`estado = {}
`brasil = []
`dados = []
`for c in range(0, 3):
    `estado['uf'] = str(input("Unidade Federativa: "))
    `estado['sigla'] = str(input("Sigla: "))
    `dados.append(estado.copy())
    `brasil.append(dados.copy())
    `dados.clear()
`for v in brasil:
	`print(f"{v}")
```output
Unidade Federativa: São Paulo
Sigla: SP
Unidade Federativa: Rio de Janeiro
Sigla: RJ
Unidade Federativa: Santa Catarina
Sigla: SC
[{'uf': 'São Paulo', 'sigla': 'SP'}]     
[{'uf': 'Rio de Janeiro', 'sigla': 'RJ'}]
[{'uf': 'Santa Catarina', 'sigla': 'SC'}]
```



`estado = {}
`brasil = []
`for c in range(0, 3):
    `estado['uf'] = str(input("Unidade Federativa: "))
    `estado['sigla'] = str(input("Sigla: "))
    `brasil.append(estado.copy())
`for e in brasil:
    `for k, v in e.items():
        `print(f"O campo {k} tem valor {v}")
```output
Unidade Federativa: São Paulo
Sigla: SP
Unidade Federativa: Rio de Janeiro
Sigla: RJ
Unidade Federativa: Goiás
Sigla: GO
O campo uf tem valor São Paulo     
O campo sigla tem valor SP
O campo uf tem valor Rio de Janeiro
O campo sigla tem valor RJ
O campo uf tem valor Goiás
O campo sigla tem valor GO
```

`estado = {}`

1. **Inicialização do Dicionário `estado`:**
    - `estado = {}`: Cria um dicionário vazio que será usado para armazenar informações sobre unidades federativas (UF) e suas siglas.



`# Inicializa uma lista vazia chamada 'brasil' 
`brasil = []`

2. **Inicialização da Lista `brasil`:**
    - `brasil = []`: Cria uma lista vazia que será usada para armazenar cópias do dicionário `estado`.



`# Loop para coletar informações de 3 estados 
`for c in range(0, 3):     
	`estado['uf'] = str(input("Unidade Federativa: "))     
	`estado['sigla'] = str(input("Sigla: "))     
	`brasil.append(estado.copy())`

3. **Coleta de Informações dos Estados:**
    - `for c in range(0, 3):`: Inicia um loop que itera 3 vezes (de 0 a 2) para coletar informações sobre 3 unidades federativas.
    - `estado['uf'] = str(input("Unidade Federativa: "))`: Solicita ao usuário a unidade federativa e armazena o valor na chave `'uf'` do dicionário `estado`.
    - `estado['sigla'] = str(input("Sigla: "))`: Solicita ao usuário a sigla da unidade federativa e armazena o valor na chave `'sigla'` do dicionário `estado`.
    - `brasil.append(estado.copy())`: Adiciona uma cópia do dicionário `estado` à lista `brasil`. O método `.copy()` é usado para evitar que alterações subsequentes ao dicionário `estado` afetem as cópias já adicionadas à lista.



`# Loop para imprimir as informações de cada estado 
`for e in brasil:     
	`for k, v in e.items():         
		`print(f"O campo {k} tem valor {v}")`

4. **Impressão das Informações dos Estados:**
    - `for e in brasil:`: Itera sobre cada dicionário na lista `brasil`.
    - `for k, v in e.items():`: Itera sobre cada par chave-valor em cada dicionário `e`.
    - `print(f"O campo {k} tem valor {v}")`: Imprime a chave `k` e o valor `v` de cada par chave-valor.

### Resumo

- **Inicialização:** O dicionário `estado` e a lista `brasil` são inicializados vazios.
- **Coleta de Dados:** O loop coleta informações sobre unidades federativas e siglas, armazenando cada entrada como uma cópia do dicionário `estado` na lista `brasil`.
- **Impressão de Dados:** Um loop aninhado itera sobre a lista `brasil` e imprime as informações armazenadas em cada dicionário.

### Observações

- **Uso de `.copy()`:** É crucial usar `estado.copy()` para adicionar uma cópia do dicionário `estado` à lista `brasil`. Sem isso, todas as referências na lista `brasil` apontariam para o mesmo dicionário `estado`, e as alterações subsequentes afetariam todas as entradas.

- **Formatação de Saída:** A formatação `f"O campo {k} tem valor {v}"` proporciona uma saída clara e legível.


ou podemos imprimir apenas os items
`estado = {}
`brasil = []
`for c in range(0, 3):
    `estado['uf'] = str(input("Unidade Federativa: "))
    `estado['sigla'] = str(input("Sigla: "))
    `brasil.append(estado.copy())
`for e in brasil:
    `for  v in e.items():
        `print(v)


# Exercício 1:

`aluno = {}
`aluno['Nome'] = str(input("Nome: "))
`aluno['Media'] = float(input("Media: "))
`if aluno['Media'] >= 7:
    `aluno['Situação']= 'Aprovado'
`elif aluno['Media'] >3 and aluno['Media'] <7:
    `aluno['Situação']= 'Recuperação'
`elif aluno['Media'] <=3:
    `aluno['Situação']= 'Reprovado!'
`print("-="*10)
`for k, v in aluno.items():
    `print(f"    {k} é igual a {v}")
`print("-="*10)


`aluno = {}`

1. **Inicialização do Dicionário `aluno`:**
    - `aluno = {}`
        - Inicializa um dicionário vazio chamado `aluno` para armazenar informações sobre o aluno, como nome, média e situação.



`aluno['Nome'] = str(input("Nome: "))`

2. **Entrada do Nome do Aluno:**
    - `aluno['Nome'] = str(input("Nome: "))`
        - Solicita ao usuário que insira o nome do aluno. O valor inserido é convertido para uma string e armazenado no dicionário `aluno` com a chave `'Nome'`.



`aluno['Media'] = float(input("Media: "))`

3. **Entrada da Média do Aluno:**
    - `aluno['Media'] = float(input("Media: "))`
        - Solicita ao usuário que insira a média do aluno. O valor inserido é convertido para um número do tipo `float` e armazenado no dicionário `aluno` com a chave `'Media'`.


`if aluno['Media'] >= 7:     
	`aluno['Situação'] = 'Aprovado'`

4. **Verificação da Situação: Aprovado**
    - `if aluno['Media'] >= 7:`
        - Verifica se a média do aluno é maior ou igual a 7.
    - `aluno['Situação'] = 'Aprovado'`
        - Se a condição for verdadeira, o dicionário `aluno` é atualizado com a chave `'Situação'` e o valor `'Aprovado'`.



`elif aluno['Media'] > 3 and aluno['Media'] < 7:     
	`aluno['Situação'] = 'Recuperação'`

5. **Verificação da Situação: Recuperação**
    - `elif aluno['Media'] > 3 and aluno['Media'] < 7:`
        - Verifica se a média do aluno está entre 3 (exclusivo) e 7 (exclusivo).
    - `aluno['Situação'] = 'Recuperação'`
        - Se a condição for verdadeira, o dicionário `aluno` é atualizado com a chave `'Situação'` e o valor `'Recuperação'`.



`elif aluno['Media'] <= 3:     
	`aluno['Situação'] = 'Reprovado!'`

6. **Verificação da Situação: Reprovado**
    - `elif aluno['Media'] <= 3:`
        - Verifica se a média do aluno é menor ou igual a 3.
    - `aluno['Situação'] = 'Reprovado!'`
        - Se a condição for verdadeira, o dicionário `aluno` é atualizado com a chave `'Situação'` e o valor `'Reprovado!'`.


`print("-=" * 10)`

7. **Impressão de Separador:**
    - `print("-=" * 10)`
        - Imprime uma linha separadora composta por 20 caracteres "-=".



`for k, v in aluno.items():     
	`print(f"    {k} é igual a {v}")`

8. **Impressão das Informações do Aluno:**
    - `for k, v in aluno.items():`
        - Inicia um loop que itera sobre os pares chave-valor (`k`, `v`) do dicionário `aluno`.
    - `print(f" {k} é igual a {v}")`
        - Imprime cada chave `k` e seu respectivo valor `v` no formato `" {k} é igual a {v}"`.


`print("-=" * 10)`

9. **Impressão de Separador Final:**
    - `print("-=" * 10)`
        - Imprime novamente uma linha separadora composta por 20 caracteres "-=".

### Resumo do Código

1. **Inicialização:** O código inicializa um dicionário `aluno`.
2. **Entrada de Dados:** O usuário é solicitado a inserir o nome e a média do aluno.
3. **Avaliação da Situação:** Com base na média inserida, o código avalia a situação do aluno, que pode ser "Aprovado", "Recuperação" ou "Reprovado".
4. **Impressão dos Dados:** As informações armazenadas no dicionário `aluno` são impressas em um formato organizado.



# Exercício 2:
