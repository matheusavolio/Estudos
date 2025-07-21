### Aula158 - #FileWriter e #BufferedWriter

- #FileWriter (Stream de escrita de caracteres em arquivos)
	- Cria/recria o arquivo `new FileWriter(path)`
	- Acrescenta ao arquivo existente: `new FileWriter(path, true)`
- `BufferedWriter`(Mais rápido)

```java
String[] lines = new String[]{sc.nextLine()}; 
// Lê uma linha de entrada do usuário e a armazena em um array. 
String path = "d://testeArq3"; 
// Define o caminho do arquivo onde os dados serão gravados. 
try (BufferedWriter bw = new BufferedWriter(new FileWriter(path, true))) { 
// Bloco try-with-resources: garante que o BufferedWriter será fechado automaticamente. 
	
	for (String line : lines) { 
	// Itera sobre as linhas armazenadas no array. 
	
	bw.write(line); 
	// Escreve a linha no arquivo.
	 
	bw.newLine(); 
	// Adiciona uma nova linha no arquivo (equivalente a "\n"). 
	} 
} catch (IOException e) { 
// Captura e trata possíveis exceções de I/O. 
	
	e.printStackTrace(); 
	// Imprime a pilha de erros no console. }****
```

### **Resumo detalhado do código**

1. **`String[] lines = new String[]{sc.nextLine()};`**
    
    - Lê uma linha de entrada do usuário usando o objeto `sc` (um `Scanner`) e armazena em um array de strings chamado `lines`.
    - O array foi criado para permitir a gravação de múltiplas linhas, embora aqui seja apenas uma linha por vez.
2. **`String path = "d://testeArq3";`**
    
    - Define o caminho do arquivo onde as linhas serão gravadas. Neste caso, o arquivo será chamado **`testeArq3`** e estará localizado no diretório **`d://`**.
3. **`try (BufferedWriter bw = new BufferedWriter(new FileWriter(path, true)))`**
    
    - **Bloco #Try-with-Resources:**  
        Garante que o **`BufferedWriter`** será fechado automaticamente ao final da operação, mesmo que ocorra uma exceção.
    - **`new FileWriter(path, true)`**:  
        Cria ou abre o arquivo no caminho especificado para escrita. O parâmetro **`true`** ativa o modo _append_:
        - Caso o arquivo já exista, os dados serão adicionados ao final do arquivo.
        - Se o arquivo não existir, ele será criado.
    - **`BufferedWriter`**:  
        Envolve o `FileWriter` para otimizar a escrita de dados no arquivo, permitindo operações mais eficientes, como escrever em blocos ou usar métodos convenientes, como **`newLine()`**.
4. **`for (String line : lines) { ... }`**
    
    - Itera sobre o array de strings `lines`, escrevendo cada linha no arquivo.
5. **`bw.write(line);`**
    
    - Escreve o conteúdo da string `line` no arquivo.
6. **`bw.newLine();`**
    
    - Adiciona uma quebra de linha no arquivo, garantindo que cada entrada seja gravada em uma nova linha.
7. **`catch (IOException e) { e.printStackTrace(); }`**
    
    - Captura e trata qualquer exceção relacionada a operações de entrada/saída.
    - **`e.printStackTrace();`**: Exibe a pilha de erros no console para depuração.

### Aula159 - Manipulando pastas com #File 

```java
System.out.println("Enter a folder path: "); 
// Solicita ao usuário o caminho de uma pasta. 

String strPath = sc.nextLine(); 
// Lê a entrada do usuário e a armazena como uma string. 

File path = new File(strPath); 
// Cria um objeto File representando o diretório informado. 

// Lista os subdiretórios dentro do diretório especificado. 
File[] folders = path.listFiles(File::isDirectory); System.out.println("FOLDERS: "); 

for (File folder : folders){
	System.out.println(folder);
	 // Imprime o caminho de cada subdiretório encontrado. 
	 }; 
	 
	 // Lista os arquivos dentro do diretório especificado. 
	 
File[] files = path.listFiles(File::isFile); System.out.println("FILES: "); 
for (File filess : files) { 
// Nota: O loop deveria iterar sobre `files` em vez de `folders`. 
	System.out.println(filess); 
	// Imprime o caminho de cada arquivo encontrado. 
} 

// Cria um novo subdiretório chamado "folderTeste" dentro do diretório especificado. 
boolean success = new File(strPath + "\\folderTeste").mkdir(); 
System.out.println("Directory created successfully " + success); 
// Indica se a criação foi bem-sucedida.
```

### **Resumo detalhado do código**

1. **`System.out.println("Enter a folder path: ");`**
    
    - Exibe uma mensagem solicitando que o usuário insira o caminho de um diretório.
2. **`String strPath = sc.nextLine();`**
    
    - Lê o caminho do diretório fornecido pelo usuário e o armazena na variável `strPath`.
3. **`File path = new File(strPath);`**
    
    - Cria um objeto `File` que representa o diretório especificado.
4. **`File[] folders = path.listFiles(File::isDirectory);`**
    
    - Usa o método **`listFiles`** para listar todos os subdiretórios no diretório especificado.
    - O método **`File::isDirectory`** é usado como um filtro para retornar apenas os diretórios.
5. **`for (File folder : folders) { System.out.println(folder); }`**
    
    - Itera sobre o array `folders` e imprime os caminhos dos subdiretórios encontrados.
6. **`File[] files = path.listFiles(File::isFile);`**
    
    - Usa o método **`listFiles`** para listar todos os arquivos no diretório especificado.
    - O método **`File::isFile`** é usado como um filtro para retornar apenas os arquivos.
7. **Erro no Loop**
    
    - **`for (File filess : folders)`**: O loop deveria iterar sobre `files` em vez de `folders`. A correção seria:
        
        
```java
for (File filess : files) {     
	System.out.println(filess); }
```


        
8. **`boolean success = new File(strPath + "\\folderTeste").mkdir();`**
    
    - Tenta criar um subdiretório chamado **`folderTeste`** dentro do diretório especificado.
    - Retorna `true` se o diretório foi criado com sucesso, ou `false` se já existir ou a operação falhar.
9. **`System.out.println("Directory created successfully " + success);`**
    
    - Exibe uma mensagem indicando se o subdiretório foi criado com sucesso.
