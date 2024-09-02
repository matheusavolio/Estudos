#### **1. Conceito de Dicionários**

- Estrutura de dados que armazena pares chave-valor.
- Chaves são únicas e imutáveis (strings, números, tuplas).
- Valores podem ser de qualquer tipo.

#### **2. Criação de Dicionários**

- **Sintaxe Básica**
    
    
    `meu_dicionario = {"chave1": "valor1", "chave2": "valor2"}`
    
- **Usando #dict()
    
    
    `meu_dicionario = dict(chave1="valor1", chave2="valor2")`
    

#### **3. Acessando Valores**

- **Usando Chaves**
    
    
    `valor = meu_dicionario["chave1"]`
    
- **Método #get
    
    
    `valor = meu_dicionario.get("chave1")`
    

#### **4. Modificando Dicionários**

- **Adicionando/Alterando Itens**
    
    
    `meu_dicionario["chave3"] = "valor3"`
    
- **Removendo Itens**
    - **Usando #del
        
        
        `del meu_dicionario["chave2"]`
        
    - **Método #pop
        
        
        `valor_removido = meu_dicionario.pop("chave1")`
        
    - **Método #popitem
        
        
        `chave, valor = meu_dicionario.popitem()`
        

#### **5. Métodos Úteis**

- #keys` - Retorna todas as chaves
    
    
    `chaves = meu_dicionario.keys()`
    
- #values` - Retorna todos os valores
    
    
    `valores = meu_dicionario.values()`
    
- #items` - Retorna pares chave-valor
    
    
    `itens = meu_dicionario.items()`
    

#### **6. Iteração em Dicionários**

- **Iterando sobre Chaves**
    
    
    `for chave in meu_dicionario:
		`print(chave)`
    
- **Iterando sobre Valores**
    
    
    `for valor in meu_dicionario.values():
        `` print(valor)`
    
- **Iterando sobre Pares Chave-Valor**
    
    
    `for chave, valor in meu_dicionario.items():
        `` print(f"{chave}: {valor}")`
    

#### **7. Compreensão de Dicionários**

- **Sintaxe**
    
    
    `dicionario_compreensao = {chave: valor for chave, valor in iteravel}`
    
- **Exemplo**
    
    
    `quadrados = {x: x**2 for x in range(6)}`
    

#### **8. Métodos de Dicionário Avançados**

- #update` - Atualiza o dicionário com outro dicionário ou pares chave-valor
    
    
    `meu_dicionario.update({"chave4": "valor4", "chave1": "novo_valor1"})`
    
- #setdefault` - Retorna o valor da chave; se a chave não existir, adiciona com um valor padrão
    
    
    `valor = meu_dicionario.setdefault("chave5", "valor5")`
    

#### **9. Dicionários Aninhados**

- **Estrutura**
    
    
    `dicionario_aninhado = {     
    `"dicionario1": {"chaveA": "valorA"},     
    `"dicionario2": {"chaveB": "valorB"} }`
    
- **Acessando Valores**
    
    
    `valor = dicionario_aninhado["dicionario1"]["chaveA"]`
    

#### **10. Funções Úteis**

- #len` - Retorna o número de itens
    
    
    `tamanho = len(meu_dicionario)`
    
- #in` - Verifica se uma chave está no dicionário
    
    `existe = "chave1" in meu_dicionario`
    
------------------------------------------------------------------------
------------------------------------------------------------------------

### **Exemplo Completo**

```python

`cont = 0 
`pessoas_lista = [] 
`mulheres_dict = {} 
`pessoas_dicionario = {} 
`mulheres_lista = [] 
`maior_lista = [] 
`while True: 
	  `pessoas_dicionario["Nome"] = str(input("Nome: ")) 
	`pessoas_dicionario["Sexo"] = str(input("Sexo: [M/F] ")) 
	`pessoas_dicionario["Idade"] = int(input("Idade: ")) 
	`cont+=1  
	`pessoas_lista.append(pessoas_dicionario.copy()) 
	`soma_idades = sum(p["Idade"] for p in pessoas_lista) 
	`media_grupo = soma_idades / cont 
	`if pessoas_dicionario["Idade"] > media_grupo: 
		`maior_lista.append(pessoas_dicionario.copy()) 
	`` if pessoas_dicionario["Sexo"] == "f": 
		`mulheres_dict["Nome"] = pessoas_dicionario["Nome"] 
		`mulheres_lista.append(mulheres_dict.copy()) 
	`continuar continuar = str(input("Quer continuar: [S/N] ")).lower().strip()  if "n" in continuar: 
		`print(f"Foram cadastradas: {cont} pessoas") 
		`print(f"A media de idade do grupo foi de {media_grupo:.2f} anos") print(f"Foram cadastradas as mulheres:", end=" ") for e in mulheres_lista: for k, v in e.items(): 
			`print(f"{v}", end=" ") 
			`` print() 
			`print(f"Lista das mulheres que estão acima da media de idade do grupo: ") 
		`print()  
		`for e in maior_lista: 
			`for k, v in e.items(): 
				`print(f"{k} = {v};", end=" ") 
			`print() 
		`break
		
```

```python
OUTPUT
		Nome: pedro
		Sexo: [M/F] m
		Idade: 43
		Quer continuar: [S/N] s
		Nome: ana
		Sexo: [M/F] f
		Idade: 22
		Quer continuar: [S/N] s
		Nome: geovani
		Sexo: [M/F] m
		Idade: 23
		Quer continuar: [S/N] s
		Nome: paula
		Sexo: [M/F] f
		Idade: 41
		Quer continuar: [S/N] n
		-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
		A) Foram cadastradas: 4 pessoas
		B) A media de idade do grupo foi de 32.25 anos
		C) Foram cadastradas as mulheres: ana paula 
		D) Lista das mulheres que estão acima da media de idade do grupo: 
		
		Nome = pedro; Sexo = m; Idade = 43; 
		Nome = paula; Sexo = f; Idade = 41;
```

------------------------------------------------------------------------
------------------------------------------------------------------------


### Explicações Detalhadas

```
1. **Inicialização das Variáveis:**
    
    - `cont`: Conta o número total de pessoas cadastradas.
    - `pessoas_lista`: Armazena todos os cadastros de pessoas.
    - `mulheres_dict`: Temporário para armazenar informações de mulheres.
    - `pessoas_dicionario`: Temporário para armazenar informações de uma pessoa específica.
    - `mulheres_lista`: Armazena informações das mulheres cadastradas.
    - `maior_lista`: Armazena informações das pessoas cuja idade é maior que a média do grupo.
2. **Loop `while True`:**
    
    - O loop continua até que o usuário decida parar (responde com 'n').
3. **Coleta de Dados:**
    
    - Solicita e armazena o nome, sexo e idade da pessoa.
    - Incrementa o contador `cont` para rastrear o número de pessoas cadastradas.
    - Adiciona uma cópia do dicionário `pessoas_dicionario` à lista `pessoas_lista`.
4. **Cálculo da Média e Filtragem:**
    
    - Calcula a soma das idades e a média das idades.
    - Verifica se a idade da pessoa é maior que a média e, se sim, adiciona à lista `maior_lista`.
    - Verifica se o sexo da pessoa é feminino e, se sim, adiciona à lista `mulheres_lista`.
5. **Continuação do Loop:**
    
    - Solicita ao usuário se deseja continuar.
    - Se a resposta for 'n', imprime o total de pessoas cadastradas, a média de idade, e as listas de mulheres e pessoas acima da média.
6. **Impressão dos Resultados:**
    
    - Imprime a lista de mulheres e as pessoas acima da média de idade formatadas.

------------------------------------------------------------------------
------------------------------------------------------------------------

### Análise dos Loops `for`

**Explicação Detalhada:**
#### Loop para Iterar Sobre a Lista de Mulheres

1. **`for e in mulheres_lista:`**
    
    - **Objetivo:** Iterar sobre cada item da lista `mulheres_lista`.
    - **Funcionamento:** Cada item `e` da lista `mulheres_lista` é um dicionário que contém informações de uma mulher (neste caso, apenas o nome).
2. **`for k, v in e.items():`**
    
    - **Objetivo:** Iterar sobre cada chave e valor dentro do dicionário `e`.
    - **Funcionamento:** `e.items()` retorna uma visão de pares (chave, valor) do dicionário `e`. Aqui, `k` é a chave (por exemplo, "Nome"), e `v` é o valor associado a essa chave (o nome da mulher). Neste código, `k` não é usado diretamente, mas `v` é impresso.
3. **`print(f"{v}", end=" ")`**
    
    - **Objetivo:** Imprimir o valor de cada chave do dicionário.
    - **Funcionamento:** Imprime o valor associado a cada chave, com `end=" "` para que os valores sejam impressos na mesma linha, separados por espaço.
------------------------------------------------------------------------
------------------------------------------------------------------------

#### Loop para Iterar Sobre a Lista de Pessoas Acima da Média

**Explicação Detalhada:**

1. **`for e in maior_lista:`**
    
    - **Objetivo:** Iterar sobre cada item da lista `maior_lista`.
    - **Funcionamento:** Cada item `e` da lista `maior_lista` é um dicionário que contém informações de uma pessoa cuja idade é maior que a média do grupo.
2. **`for k, v in e.items():`**
    
    - **Objetivo:** Iterar sobre cada chave e valor dentro do dicionário `e`.
    - **Funcionamento:** Similar ao loop anterior, `e.items()` retorna pares (chave, valor) do dicionário `e`. Aqui, `k` é a chave (por exemplo, "Nome" ou "Idade"), e `v` é o valor associado a essa chave.
3. **`print(f"{k} = {v};", end=" ")`**
    
    - **Objetivo:** Imprimir a chave e o valor de cada item do dicionário.
    - **Funcionamento:** Imprime a chave e o valor de cada item do dicionário `e`, formatado como `chave = valor;`. O `end=" "` garante que a impressão continue na mesma linha, com cada par chave-valor separado por um espaço.
4. **`print()`**
    
    - **Objetivo:** Adicionar uma quebra de linha após imprimir todos os itens do dicionário.
    - **Funcionamento:** Imprime uma nova linha para que o próximo item ou grupo de itens apareça na linha seguinte.

### Resumo

- **Listas:** O loop `for` é utilizado para percorrer cada item na lista, que pode ser um dicionário com várias informações.
- **Dicionários:** O loop aninhado `for` é utilizado para percorrer cada par chave-valor dentro de um dicionário.
```
------------------------------------------------------------------------
------------------------------------------------------------------------


# Exemplo completo 2:
código: 
código

```python
CÓDIGO

`time = []
`soma = 0
`partidas = []
`jogador = {}
`while True:
    `jogador["Nome"] = str(input("Nome do jogador: "))
    `tot = int(input(f"Quantas partidas {jogador['Nome']} jogou? "))
    `partidas.clear()
    `for c in range(0, tot):
        `partidas.append(int(input(f"    Quantos gols na partida {c + 1}? ")))
    `jogador["Gols"] = partidas[:]
    `jogador["Total"] = sum(partidas)
    `time.append(jogador.copy())
    `while True:
        `continuar = str(input("Quer continuar? [S/N] ")).lower()[0]
        `print("-"*40)
        `if continuar in "sn":
            `break
        `print(f"ERRO! Responda apenas [S] para sim e [N] para não.")
    `if continuar == "n":
        `break
`print("-="*30)
`print("cod", end=" ")
`for i in jogador.keys():
    `print(f"{i:<15}", end=" ")
`print()
`print("-"*40)
`for k, v in enumerate(time):
    `print(f"{k:>2}" , end=" ")
    `for d in v.values():
        `print(f"{str(d):<15}", end=" ")
    `print()
`print("-"*40)
`while True:
    `busca = int(input("Mostrar dados de qual jogador? [999 para]: "))
    `if busca == 999:
        `break
    `if busca >= len(time):
        `print(f"Erro! Não existe o jogador com o codigo {busca}")
    `else:
        `print(f"  --  LEVANTAMENTO DO JOGADOR {time[busca]['Nome']}:")
        `for i, g in enumerate(time[busca]["Gols"]):
            `print(f"No jogo {i + 1} fez {g} gols")
    `print("-"*40)
`print("Volte sempre!")
```

```python
OUTPUT

Nome do jogador: yago
Quantas partidas yago jogou? 4
    Quantos gols na partida 1? 6
    Quantos gols na partida 2? 2
    Quantos gols na partida 3? 5
    Quantos gols na partida 4? 1
Quer continuar? [S/N] s
----------------------------------------
Nome do jogador: lucas
Quantas partidas lucas jogou? 2
    Quantos gols na partida 1? 3
    Quantos gols na partida 2? 1
Quer continuar? [S/N] n
----------------------------------------
-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
cod Nome            Gols            Total
----------------------------------------
 0 yago            [6, 2, 5, 1]    14
 1 lucas           [3, 1]          4
----------------------------------------
Mostrar dados de qual jogador? [999 para]: 4
Erro! Não existe o jogador com o codigo 4
----------------------------------------
Mostrar dados de qual jogador? [999 para]: 0
  --  LEVANTAMENTO DO JOGADOR yago:        
No jogo 1 fez 6 gols
No jogo 2 fez 2 gols
No jogo 3 fez 5 gols
No jogo 4 fez 1 gols
----------------------------------------   
Mostrar dados de qual jogador? [999 para]: 1
  --  LEVANTAMENTO DO JOGADOR lucas:
No jogo 1 fez 3 gols
No jogo 2 fez 1 gols
----------------------------------------
Mostrar dados de qual jogador? [999 para]: 999
Volte sempre!
```

```Analise detalhada
1. Inicialização de Variáveis
    
    - time: Lista para armazenar os dicionários de jogadores.
    - soma: Variável inicialmente não utilizada no código.
    - partidas: Lista para armazenar o número de gols em cada partida.
    - jogador: Dicionário para armazenar os dados de cada jogador (nome, gols e total de gols).
2. Loop Principal (while True)
    
    O objetivo é criar um loop infinito que só será interrompido por um break quando o usuário decidir parar.
    
3. Entrada de Dados do Jogador
    
    - jogador["Nome"]: Solicita o nome do jogador e armazena no dicionário jogador.
    - tot: Solicita o número de partidas que o jogador jogou e armazena em tot.
    - partidas.clear(): Limpa a lista partidas para garantir que dados anteriores não interfiram.
4. Loop para Capturar Gols por Partida
    
    O objetivo é iterar sobre o número de partidas (tot) e capturar os gols em cada uma.
    
    Funcionamento:
    
    - for c in range(0, tot): Cria um loop que itera c vezes, onde c varia de 0 a tot-1.
    - partidas.append(...): Adiciona o número de gols da partida c+1 na lista partidas.
5. Armazenamento dos Dados no Dicionário jogador
    
    - jogador["Gols"]: Armazena a lista de gols em jogador["Gols"].
    - jogador["Total"]: Calcula e armazena o total de gols.
    - time.append(jogador.copy()): Adiciona uma cópia do dicionário jogador à lista time.
6. Verificação se o Usuário Deseja Continuar
    
    O objetivo é perguntar ao usuário se deseja continuar ou parar o cadastro.
    
    Funcionamento: O loop interno verifica se o usuário digitou "s" ou "n". Se a resposta for "n", o loop principal é interrompido com break.
    
7. Impressão dos Dados da Tabela de Jogadores
    
    - for i in jogador.keys(): Itera sobre as chaves do dicionário jogador (Nome, Gols, Total).
    - print(f"{i:<15}", end=" "): Imprime cada chave com espaçamento de 15 caracteres.
8. Impressão dos Dados de Cada Jogador
    
    - for k, v in enumerate(time): Objetivo: Iterar sobre cada jogador na lista time, junto com seu índice k.
    - Funcionamento: enumerate(time) gera pares (k, v), onde k é o índice e v é o dicionário do jogador. for d in v.values(): Itera sobre os valores de v (Nome, Gols, Total). print(f"{str(d):<15}", end=" "): Imprime cada valor formatado.
9. Busca de Dados de um Jogador Específico
    
    - busca = int(input(...)): Solicita o índice do jogador a ser buscado.
    - if busca == 999: Condição para encerrar a busca.
    - if busca >= len(time): Verifica se o índice é válido.
    - else: Se o índice for válido, imprime os dados do jogador selecionado.
    - for i, g in enumerate(time[busca]["Gols"]): Objetivo: Iterar sobre a lista de gols do jogador e imprimir a quantidade de gols em cada partida.
    
    Funcionamento:
    
    - enumerate(time[busca]["Gols"]) gera pares (i, g) onde i é o índice e g é o número de gols.
    - print(f"No jogo {i + 1} fez {g} gols"): Imprime a quantidade de gols para cada partida.

### Resumo

Estrutura do Código: O código utiliza loops while e for para coletar, armazenar e imprimir dados sobre jogadores e suas performances em partidas.

O Loop Principal (while True) mantém o fluxo de coleta de dados até que o usuário decida parar.

O Loop for com enumerate é usado para iterar sobre as listas, como a lista de jogadores e a lista de gols de cada jogador, para exibir os dados de forma estruturada.

4o


```