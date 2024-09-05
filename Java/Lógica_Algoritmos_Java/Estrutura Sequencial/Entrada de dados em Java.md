# Aula26 - Entrada de dados 1/2

Conceito de entrada de dados -> É quando o usuário informa dados para o programa, no caso vai ser dentro de variáveis. E para fazer isso, o usuário vai utilizar dispositivos de entrada, como por exemplo o teclado. Também conhecido com Leitura, já que "o programa está Lendo os dados"

Para fazer a entrada de dados, nós vamos criar um objeto do tipo "Scanner" da seguinte forma:
```java
Scanner sc = new Scanner(System.in);
```
O tipo "_Scanner_" é um tipo especial do Java para fazer a entrada de dados.
Não se esquecer de importar o #Scanner:
```java
import java.util.Scanner
```
E quando não precisar mais do objeto _sc_, utilize `sc.close()` para desalocar esse recurso

Para se ler uma _String_, utiliza-se `sc.next();`
```java
import java.util.Scanner
Scanner sc = new Scanner(System.in);
x = sc.next();

```

Para se ler um número _inteiro_, utiliza-se `sc.nextInt();`
```java
import java.util.Scanner
Scanner sc = new Scanner(System.in);
x = sc.nextInt();
```

Para se ler um _double_, utiliza-se `sc.nextDouble`
Porém, se você digitar no console o número com ponto, e não com vírgula, irá acontecer um erro de _java.util.InputMismatchException_.
E para evitar isso, tem que definir a localização como US antes da declaração do `Scanner` 
```java
import java.util.Locale;
import java.util.Scanner
Locale.setDefault(Locale.US);
Scanner sc = new Scanner(System.in);
x = sc.nextDouble();
```

para se ler um _char_ utiliza-se o `sc.next().charAt(0);`
O `charAt(0);` ele pega o primeiro caractere digitado na String
```java
import java.util.Scanner
Scanner sc = new Scanner(System.in);
x = sc.next().charAt(0);
```

# Aula27 - Entrada de dados 2/2

Para ler se a linha inteira de uma _String_ e não só a primeira palavra, utiliza-se o `sc.nextLine();`
```java
import java.util.Scanner
Scanner sc = new Scanner(System.in);
x = sc.nextLine();
```

> [!ATENÇÃO] 
> Quando você usa um comando de leitura diferente do nextLine() e dá alguma quebra de linha, essa quebra de linha fica "pendente" na entrada padrão. Se você então fizer um nextLine(), aquela quebra de linha pendente será absorvida pelo nextLine()

> [!SOLUÇÃO] 
> Solução: Faça um nextLine() extra antes de fazer o nextLine() de seu interesse

#ResumoAulas26-27
- Scanner 
	-  next() 
	- nextInt() 
	-  nextDouble() 
	-  next().charAt(0) 
-  Locale 
- Como ler até a quebra de linha 
	-  nextLine() 
	-  como limpar o buffer de leitura
