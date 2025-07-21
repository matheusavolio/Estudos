# Aula24 - Saída de dados

Para imprimir um texto qualquer:
#printNoJava
```java
// sem quebra de linha
System.out.print("Hello World!");
```

```java
// com quebra de linha no final
System.out.println("Hello World!");
```

Para especificar quantas casas decimais você quer que seja exibida no output do programa:
```java
System.out.printf("%.2%n", <var>)
// após o "%." vem o número de casas decimais que deseja exibir, e após o número vem a quebra de linha, que pode ser feita com "\n" ou "%n"
```

Para configurarmos a localização do nosso programa e substituir a " , " por " . " utilizamos a biblioteca #Locale 
```java
import java.util.Locale;
System.out.printf("%.2f\n", x); // imprime com vírgula
Locale.setDefault(Locale.US); // muda a configuração para o sistema Americano
System.out.printf("%.2f\n", x); // imprime com ponto
```

#concatenaçãoNoJava
`elemento1 + elemento2 + elemento3 + ... + elementoN
```java
System.out.println("RESULTADO = " +  x + " METROS");
System.out.printf("RESULTADO = %.2f metros\n", x); // o valor de x vai entrar no lugar de " %.2f" e irá ser impresso no output o valor de x formatado para duas casas decimais
```

#ImpressãoFormatada
```java
IMPRESSÃO FORMATADA
String nome = "Matheus";
int idade = 19;
double peso = 97.2;
System.out.printf("%s tem %d anos e pesa %.2f", nome, idade, peso); // a variavel é inserida na ordem de chamada
%f = ponto flutuante
%d = num inteiro
%s = String
\n = quebra de linha
%.2f = delimitando número de casas decimais, e é substítuido pela váriavel
```

