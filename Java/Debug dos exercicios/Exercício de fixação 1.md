
```java
package Exercicios;
// importo o pacote de localizaões para utilizar o " . " no lugar da " , "
import java.util.Locale;
public class exFixacao {
    public static void main(String[] args) {
        // Declarando as váriaveis
        String product1 = "Computer";
        String product2 = "Office desk";
        int age = 30;
        int code = 5290;
        char gender = 'F';
        double price1 = 2100.0;
        double price2 = 650.50;
        double measure = 53.234567;
        // Impressões formatadas
        System.out.println("Products:");
        System.out.printf("%s, which price is $ %.2f\n", product1, price1);
        System.out.printf("%s, which price is %.2f\n", product2, price2);
        System.out.println("");
        System.out.printf("Record: %d years old, code %d and gender: %s\n", age, code, gender);
        System.out.println("");
        System.out.printf("Measue with eight decimal places: %.8f\n", measure);
        System.out.printf("Rouded (three decimal places): %.3f\n", measure);
        Locale.setDefault(Locale.US);
        System.out.printf("US decimal point: %.3f\n", measure);
    }
}
```

#### Debug:


`package Exercicios;`

- **Linha 1**: Declaração do pacote onde o código está localizado. Isso organiza o código em um namespace (um agrupamento lógico de classes), útil quando temos múltiplos arquivos Java.
---

`import java.util.Locale;`

- **Linha 2**: Importa a classe `Locale` da biblioteca `java.util`. Essa classe permite configurar a localidade para que o programa utilize convenções regionais, como o formato de números.
---

`public class exFixacao {`

- **Linha 3**: Declaração da classe pública chamada `exFixacao`. Toda aplicação Java é composta de classes, e aqui estamos criando uma com esse nome.

---

    `public static void main(String[] args) {`

- **Linha 4**: Método principal (`main`), ponto de entrada da aplicação. É onde a execução do programa começa.

---

        `// Declarando as váriaveis         
        String product1 = "Computer";         
        String product2 = "Office desk";`

- **Linhas 5 e 6**: Declaração de variáveis `product1` e `product2` do tipo `String`, que armazenam os nomes dos produtos "Computer" e "Office desk", respectivamente.

---
        `int age = 30;         
        int code = 5290;         
        char gender = 'F';`

- **Linhas 7 a 9**: Variáveis do tipo primitivo:
    - `age`: tipo `int`, armazena o valor 30, representando a idade.
    - `code`: tipo `int`, armazena o código 5290.
    - `gender`: tipo `char`, armazena o caractere 'F', representando o gênero.

---

        `double price1 = 2100.0;         
        double price2 = 650.50;         
        double measure = 53.234567;`

- **Linhas 10 a 12**: Variáveis do tipo `double`:
    - `price1` e `price2`: armazena os preços dos produtos com casas decimais.
    - `measure`: valor numérico com várias casas decimais para ser exibido mais tarde com diferentes formatos.

---

        `// Impressões formatadas         
        System.out.println("Products:");`

- **Linha 13**: Imprime a string `"Products:"` no console.

---
	        `System.out.printf("%s, which price is $ %.2f\n", product1, price1);         System.out.printf("%s, which price is %.2f\n", product2, price2);`

- **Linhas 14 e 15**: `System.out.printf` permite imprimir strings formatadas. Os placeholders (`%s` e `%.2f`) são substituídos por:
    - `%s`: string (nome do produto).
    - `%.2f`: número decimal com duas casas após o ponto.
    - O preço de `product1` e `product2` será exibido com esse formato.

---

        `System.out.println("");`

- **Linha 16**: Imprime uma linha em branco para separar visualmente as seções no console.
---

`System.out.printf("Record: %d years old, code %d and gender: %s\n", age, code, gender);`

- **Linha 17**: Imprime uma linha formatada com:
    - `%d`: número inteiro (idade e código).
    - `%s`: string (gênero).

---

        `System.out.println("");`

- **Linha 18**: Mais uma linha em branco para separação.

---

`System.out.printf("Measue with eight decimal places: %.8f\n", measure);         System.out.printf("Rouded (three decimal places): %.3f\n", measure);`

- **Linhas 19 e 20**: Exibe o valor de `measure` com:
    - `%.8f`: oito casas decimais.
    - `%.3f`: três casas decimais.

---

        `Locale.setDefault(Locale.US);`

- **Linha 21**: Altera a localidade padrão para os Estados Unidos. Isso muda a formatação de números, utilizando ponto `.` como separador decimal, em vez de vírgula.

---

        `System.out.printf("US decimal point: %.3f\n", measure);     } }`

- **Linha 22**: Agora que a localidade foi configurada para `US`, imprime o número `measure` com ponto decimal.
---
