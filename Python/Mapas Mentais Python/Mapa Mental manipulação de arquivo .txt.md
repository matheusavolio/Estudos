**Manipulação de Arquivos `.txt` em Python**

1. **Abrindo Arquivos**
    
    - `open()`
        - **Modos de Abertura**
            - `'r'`: Leitura (padrão)
            - `'w'`: Escrita (sobrescreve)
            - `'a'`: Escrita (anexa)
            - `'b'`: Modo binário
            - `'x'`: Criação exclusiva (erro se o arquivo já existir)
            - `'r+'`: Leitura e Escrita
            - `'w+'`: Escrita e Leitura (sobrescreve)
            - `'a+'`: Escrita e Leitura (anexa)
2. **Leitura de Arquivos**
    
    - **Métodos de Leitura**
        - `read(size)`: Lê todo o conteúdo ou até `size` caracteres
        - `readline()`: Lê uma linha
        - `readlines()`: Lê todas as linhas e retorna uma lista
    - **Iteração Sobre Linhas**
        - `for line in file`: Itera sobre cada linha do arquivo
3. **Escrita em Arquivos**
    
    - **Métodos de Escrita**
        - `write(string)`: Escreve uma string no arquivo
        - `writelines(list)`: Escreve uma lista de strings no arquivo
    - **Comportamento em Modos**
        - `'w'`: Sobrescreve o arquivo
        - `'a'`: Anexa ao final do arquivo
4. **Fechando Arquivos**
    
    - **Fechamento Manual**
        - `file.close()`: Fecha o arquivo manualmente
    - **Gerenciamento Automático**
        - `with open() as file:`: Garante o fechamento automático do arquivo
5. **Trabalhando com Exceções**
    
    - **Tratamento de Erros Comuns**
        - `FileNotFoundError`: Arquivo não encontrado
        - `IOError`: Erros de entrada/saída
        - **Exemplo de Tratamento**
            
            ```python
            `try:     
	            with open('arquivo.txt', 'r') as file:         
		            data = file.read() 
		        except FileNotFoundError:     
			        print("Arquivo não encontrado.")`
            ```

            
6. **Manipulação Avançada**
    
    - **Seek e Tell**
        - `file.seek(offset)`: Move o cursor de leitura/escrita
        - `file.tell()`: Retorna a posição atual do cursor
    - **Flush**
        - `file.flush()`: Força a gravação do buffer para o disco
    - **Context Manager**
        - `with open('file.txt', 'r') as file:`: Abertura e fechamento automáticos
7. **Codificação de Arquivos**
    
    - **Especificando Codificação**
        - `open('file.txt', 'r', encoding='utf-8')`: Define a codificação ao abrir o arquivo
    - **Codificações Comuns**
        - `'utf-8'`: Codificação padrão
        - `'ascii'`: Codificação limitada
        - `'latin-1'`: Codificação para caracteres latinos


### Comportamento do `'rt'`

- **Leitura de Arquivos de Texto:** Ao usar `'rt'`, você está dizendo ao Python que quer abrir o arquivo para leitura como um arquivo de texto. Isso é equivalente a usar apenas `'r'`, pois `'t'` é implícito e padrão.
    
- **Uso Comum:**
    
    - É utilizado quando você precisa abrir um arquivo de texto (como um `.txt`, `.csv`, etc.) para leitura, especialmente quando quer deixar explícito que o arquivo será tratado como texto.
    - **Exemplo:**
        
        ```python
        with open('arquivo.txt', 'rt') as file:     
		    conteudo = file.read()`
        ```
        