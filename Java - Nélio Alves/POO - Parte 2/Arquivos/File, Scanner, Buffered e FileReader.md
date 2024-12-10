### Aula155 #File e #Scanner

- #File é a representação abstrata de um arquivo e seu caminho
- #Scanner - é o leitor de texto
- #IOEsception - Exceção padrão de entrada e saída para arquivos (Herda a classe Exception, então o compilador obriga o tratamento dessa exceção)

Para instanciarmos um objeto do tipo #file, utilizamos o caminho até o arquivo:
```java
 File file = new File("D:\\testeArq.txt");
```

Para ler esse arquivo, precisamos instanciar um Scanner
```java
Scanner sc = null;
```

Após instanciar um Scanner, precisamos utilizar um #try-cath para prevenir possíveis erros na abertura do arquivo ou no caminho até o arquivo instanciado
```java
try {  
    sc = new Scanner(file);  
    while (sc.hasNextLine()){  
        System.out.println(sc.nextLine());  
    }  
}  
catch (IOException e){  
    System.out.println("Error: " + e.getMessage());  
}
```

E para sempre fechar o Scanner corretamente, utilizamos o bloco #finally, verificando se tem algo dentro do arquivo:
```java
finally {  
    if (sc != null){  
        sc.close();  
    }
```

### Aula1256 - #FileReader e #BufferedReader

- #FileReader - É um stream(sequência) de leitura de caracteres a partir de arquivos, quando o FileReader for instânciado, vai ser estabelecido uma sequência de leitura a partir de um arquivo
- #BufferedReader - Ele vai ser instanciado a partir do #FileReader e ele implementa algumas otimizações utilizando o buffer de memória.

```java
String path = "D:\\testeArq.txt"; 
FileReader fr = null; 
BufferedReader br = null; 
try { 
	// Cria o FileReader para abrir o arquivo no caminho especificado 
	fr = new FileReader(path); 
	
	// Envolve o FileReader em um BufferedReader para leitura eficiente 
	br = new BufferedReader(fr); 
	
	// Lê a primeira linha do arquivo 
	String line = br.readLine(); 
	
	// Loop para ler todas as linhas do arquivo até que não haja mais (line == null) 
	while (line != null) { 
		
		System.out.println(line); 
		// Imprime a linha no console 
		
		line = br.readLine(); 
		// Lê a próxima linha 
		} 
} catch (IOException e) { 
	// Captura erros relacionados a I/O e imprime a mensagem de erro 
	System.out.println("Error: " + e.getMessage()); } finally { 
	try { 
	// Fecha o BufferedReader se ele foi inicializado 
		if (br != null) { 
			br.close(); } 
		// Fecha o FileReader se ele foi inicializado 
		if (fr != null) { 
			fr.close(); } 
	} catch (IOException e) { 
		e.printStackTrace(); 
		// Exibe a pilha de erro caso haja falha no fechamento } }
```

1. **`String path = "D:\\testeArq.txt";`**
    
    - Define o caminho do arquivo que será lido. O arquivo está localizado em **`D:\testeArq.txt`**.
2. **`FileReader fr = null; BufferedReader br = null;`**
    
    - Declara dois objetos:
        - **`FileReader`**: Utilizado para abrir o arquivo e ler os caracteres.
        - **`BufferedReader`**: Envolvido no `FileReader` para otimizar a leitura, permitindo ler o arquivo linha por linha.
3. **`try { ... }`**
    
    - Bloco onde ocorre a tentativa de abrir e ler o arquivo.
4. **`fr = new FileReader(path);`**
    
    - Inicializa o `FileReader` com o caminho do arquivo. Este objeto é responsável por abrir e ler o conteúdo bruto.
5. **`br = new BufferedReader(fr);`**
    
    - Envolve o `FileReader` em um `BufferedReader` para facilitar e otimizar a leitura, especialmente quando se deseja trabalhar com linhas.
6. **`String line = br.readLine();`**
    
    - Lê a primeira linha do arquivo. Retorna:
        - O texto da linha, se existir.
        - `null` quando o final do arquivo for atingido.
7. **`while (line != null) { ... }`**
    
    - Loop que percorre o arquivo linha por linha até que o valor de `line` seja `null`.
8. **`System.out.println(line);`**
    
    - Imprime no console a linha lida do arquivo.
9. **`line = br.readLine();`**
    
    - Atualiza a variável `line` com o conteúdo da próxima linha.
10. **`catch (IOException e) { ... }`**
    
    - Trata exceções de I/O. Se ocorrer algum erro (como o arquivo não existir ou não puder ser lido), exibe a mensagem de erro no console.
11. **`finally { ... }`**
    
    - Bloco que será executado independentemente do sucesso ou falha do `try`.
12. **`if (br != null) { br.close(); }`**
    
    - Fecha o `BufferedReader`, liberando os recursos associados. Verifica se o objeto foi inicializado antes de tentar fechá-lo.
13. **`if (fr != null) { fr.close(); }`**
    
    - Fecha o `FileReader`, liberando os recursos associados.
14. **`e.printStackTrace();`**
    
    - Exibe a pilha de erros se houver falha ao fechar os recursos.


### Aula157 - Bloco #try-witch-resources

- É um bloco try que declara um ou mais recursos, e garante que esses recursos serão fechados ao final do bloco, ou seja, não será necessário fechar manualmente

Seguindo o mesmo código da aula passada, o novo código ficaria assim:
```java
String path = "D:\\testeArq.txt"; 
try (BufferedReader br = new BufferedReader(new FileReader(path))) { 
	// Lê a primeira linha do arquivo 
	String line = br.readLine(); 
	
	// Loop para ler todas as linhas do arquivo até que não haja mais (line == null) 
	while (line != null) { 
		
		System.out.println(line); 
		// Imprime a linha no console 
		
		line = br.readLine(); 
		// Lê a próxima linha 
		} 
} catch (IOException e) { 
	// Captura erros relacionados a I/O e imprime a mensagem de erro 
	System.out.println("Error: " + e.getMessage()); }
```

1. **`String path = "D:\\testeArq.txt";`**
    
    - Define o caminho do arquivo que será lido. O arquivo está localizado em **`D:\testeArq.txt`**.
2. **`try (BufferedReader br = new BufferedReader(new FileReader(path))) { ... }`**
    
    - Utiliza o **try-with-resources**, um recurso introduzido no Java 7, que permite declarar e inicializar objetos que implementam a interface **`AutoCloseable`**.
    - Garante que os recursos utilizados no bloco `try` (neste caso, `BufferedReader` e `FileReader`) serão automaticamente fechados ao final da execução do bloco, mesmo que ocorra uma exceção.
3. **`BufferedReader br = new BufferedReader(new FileReader(path))`**
    
    - Inicializa um `BufferedReader` para leitura eficiente de texto, envolvendo um `FileReader`, que é responsável por abrir o arquivo e ler os caracteres.
4. **`String line = br.readLine();`**
    
    - Lê a primeira linha do arquivo. Retorna:
        - O texto da linha, se existir.
        - `null` quando o final do arquivo for atingido.
5. **`while (line != null) { ... }`**
    
    - Um loop que percorre o arquivo linha por linha até que não haja mais conteúdo para ler (`line == null`).
6. **`System.out.println(line);`**
    
    - Imprime a linha atual no console.
7. **`line = br.readLine();`**
    
    - Atualiza a variável `line` com o conteúdo da próxima linha do arquivo.
8. **`catch (IOException e) { ... }`**
    
    - Trata exceções relacionadas a operações de entrada/saída (I/O).
    - Exibe a mensagem de erro no console usando **`e.getMessage()`** caso ocorra alguma falha, como:
        - Arquivo não encontrado.
        - Erro ao acessar o arquivo.

---

### **Diferencial do Try-with-Resources**

- **Fechamento Automático:**  
    Não é necessário usar blocos `finally` para fechar explicitamente o `BufferedReader` e o `FileReader`, pois o try-with-resources faz isso automaticamente.
    
- **Menor Risco de Vazamento de Recursos:**  
    Garante que os recursos serão liberados mesmo se ocorrer uma exceção durante a leitura.