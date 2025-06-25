#### **1. Preencher datas automaticamente**

Se você quer preencher uma lista de datas (ex: de 24/06/2025 até 03/07/2025), siga este passo a passo:

1. Digite a **primeira data**, por exemplo: `24/06/2025`.
    
2. Clique na célula.
    
3. Vá com o mouse até o **canto inferior direito da célula** (quando o cursor virar um sinal de **"+"**).
    
4. **Clique e arraste para baixo**.
    
5. O Excel completará automaticamente os dias seguintes: `25/06/2025`, `26/06/2025`, etc.
    

> 🔎 **Observação:** Se a data aparecer como número, clique com o botão direito na célula → **Formatar Células** → escolha o tipo **Data**.

---

#### **2. Preencher números em sequência (1, 2, 3...)**

1. Digite o primeiro número (ex: `1`).
    
2. Vá ao canto inferior direito da célula.
    
3. **Segure a tecla `Ctrl` no teclado**, clique e **arraste para baixo**.
    
4. O Excel continuará a sequência: `2`, `3`, `4`...
    

---

#### **3. Preencher sequência com intervalos diferentes (ex: de 1 em 4)**

1. Digite o número inicial (ex: `1`) na primeira célula.
    
2. Na célula de baixo, digite o próximo número da sequência (ex: `5`).
    
    - Aqui, a diferença entre os dois é 4.
        
3. **Selecione as duas células.**
    
4. Vá até o canto inferior direito e **arraste para baixo**.
    
5. O Excel repetirá a lógica: `1`, `5`, `9`, `13`...
    

---

#### **4. Preencher automaticamente sem arrastar**

Se quiser preencher sem usar o mouse para arrastar:

1. Clique na célula inicial com o valor.
    
2. Vá até a aba **Página Inicial**.
    
3. Clique na opção **Preencher** (fica perto do botão **Excluir**).
    
4. Selecione **Série...**.
    
5. Na janela que abrir:
    
    - Escolha a **direção** (para baixo, para o lado...),
        
    - Informe o **valor final** (ex: até 10),
        
    - Defina de quanto em quanto vai pular (ex: de 1 em 1, de 5 em 5, etc.).
        
6. Clique em **OK**.
    

> 🧠 **Isso funciona tanto para números quanto para datas.**

 
## Autopreenchimento de palavras no Excel (meses, dias e listas personalizadas)

#### **1. Preenchendo automaticamente meses, dias e dias da semana**

O Excel reconhece **algumas palavras como sequências automáticas**. Por exemplo:

- Se você digitar `Janeiro` em uma célula e **arrastar o canto inferior direito**, o Excel completará:
    
    - `Fevereiro`, `Março`, `Abril`...
        

O mesmo funciona para:

- **Dias da semana**: `Domingo`, `Segunda-feira`, `Terça-feira`...
    
- **Abreviações**: `Jan`, `Fev`, `Mar` também funcionam.
    

> 🧠 **Importante:** o Excel só reconhece essas palavras **exatamente como estão** nas configurações. Por exemplo, se você digitar só `Segunda`, ele **não** entenderá como uma sequência.

---

#### **2. Criando sua própria sequência personalizada**

Se quiser que o Excel complete uma sequência que **ele não reconhece automaticamente** (como `Segunda`, `Terça`, `Quarta`...), você pode **criar sua própria lista**. Veja como:

1. Clique em **Arquivo** (canto superior esquerdo).
    
2. Vá em **Opções**.
    
3. Na nova janela, clique em **Avançado**.
    
4. Role para baixo até a seção **Geral**.
    
5. Clique em **Editar Listas Personalizadas**.
    
6. Na nova janela:
    
    - Clique em **Nova Lista** (à esquerda).
        
    - No campo à direita, digite os itens da sua sequência, um por linha:
        
        
        ```Excel
		Segunda
		Terça
		Quarta
		Quinta
		Sexta
		```
        
    - Depois clique em **Adicionar** e em **OK**.
        

Agora, sempre que você digitar “Segunda” e arrastar, o Excel vai preencher conforme a lista que você criou!



