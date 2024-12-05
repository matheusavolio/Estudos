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