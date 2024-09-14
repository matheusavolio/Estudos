1. Fazer um programa para ler os valores da largura e altura de um retângulo. Em seguida, mostrar na tela o valor de sua área, perímetro e diagonal. Usar uma classe como mostrado no projeto ao lado.
![[ex_fixação_1.jpg]]

![[Diagram 3.svg]]


---
---

2. Fazer um programa para ler os dados de um funcionário (nome, salário bruto e imposto). Em seguida, mostrar os dados do funcionário (nome e salário líquido). Em seguida, aumentar o salário do funcionário com base em uma porcentagem dada (somente o salário bruto é afetado pela porcentagem) e mostrar novamente os dados do funcionário. Use a classe projetada abaixo
![[ex_fixação_2.jpg]]

## Código 1 e análise
```java
CÓDIGO 1
import java.util.Scanner;
import java.util.Locale;

public class Program4 {
    public static void main(String[] args) {
        Locale.setDefault(Locale.US);
        Scanner sc = new Scanner(System.in);


        Employee employ = new Employee();

        System.out.print("Name: ");
        employ.Name = sc.nextLine();

        System.out.print("Gross Salary: U$");
        employ.GrossSalary = sc.nextDouble();

        System.out.print("Tax: U$");
        employ.Tax = sc.nextDouble();

        System.out.println("");
        System.out.printf("Employee: %s, U$%.2f\n", employ.Name, employ.NetSalary());
        System.out.println("");

        System.out.print("which percentage to increase salary? ");
        double perce = sc.nextDouble();

  
        System.out.println("");
        employ.IncreaseSalary(perce);

        System.out.println("Updated data: " + employ);

        sc.close();
    }
}
```

```java
ANÁLISE 
### Linha 1-2:

`import java.util.Scanner; import java.util.Locale;`
- **Explicação:**
    - **`import java.util.Scanner;`**: Importa a classe `Scanner`, usada para ler a entrada de dados do usuário via console.
    - **`import java.util.Locale;`**: Importa a classe `Locale`, usada para definir o formato de regiões específicas, como o formato decimal.

---

### Linha 4:

`public class Program4 {`

- **Explicação:** Declara a classe pública `Program4`. Esta será a classe principal onde a execução do programa ocorrerá.

---

### Linha 6:

`public static void main(String[] args) {`

- **Explicação:** O método `main` é o ponto de entrada do programa. Tudo que está dentro deste método será executado ao rodar o programa.

---

### Linha 7:

`Locale.setDefault(Locale.US);`

- **Explicação:** Define o local/região padrão para os EUA, garantindo que o formato de números (especialmente decimais) siga o padrão dos EUA, com o ponto (`.`) como separador decimal.

---

### Linha 8:

`Scanner sc = new Scanner(System.in);`

- **Explicação:** Cria um objeto `Scanner` chamado `sc`, que será utilizado para capturar a entrada do usuário a partir do console (teclado).

---

### Linha 10:

`Employee employ = new Employee();`

- **Explicação:** Cria um novo objeto da classe `Employee`, chamado `employ`. A classe `Employee` não está no código fornecido, mas presume-se que ela armazena informações sobre um empregado, como nome, salário bruto e imposto.

---

### Linha 12-13:

`System.out.print("Name: "); employ.Name = sc.nextLine();`

- **Explicação:**
    - **`System.out.print("Name: ");`**: Exibe a mensagem "Name: " no console, solicitando que o usuário insira o nome do empregado.
    - **`employ.Name = sc.nextLine();`**: Captura o nome digitado pelo usuário e armazena-o no atributo `Name` do objeto `employ`. O método `nextLine()` lê toda a linha de entrada do usuário.

---

### Linha 15-16:

`System.out.print("Gross Salary: U$"); employ.GrossSalary = sc.nextDouble();`

- **Explicação:**
    - **`System.out.print("Gross Salary: U$");`**: Exibe a mensagem solicitando ao usuário o salário bruto do empregado.
    - **`employ.GrossSalary = sc.nextDouble();`**: Lê o valor digitado para o salário bruto (um número decimal) e armazena-o no atributo `GrossSalary` do objeto `employ`.

---

### Linha 18-19:

`System.out.print("Tax: U$"); employ.Tax = sc.nextDouble();`

- **Explicação:**
    - **`System.out.print("Tax: U$");`**: Exibe a mensagem pedindo ao usuário o valor do imposto.
    - **`employ.Tax = sc.nextDouble();`**: Lê o valor do imposto (um número decimal) e armazena-o no atributo `Tax` do objeto `employ`.

---

### Linha 21-22:


`System.out.println(""); System.out.printf("Employee: %s, U$%.2f\n", employ.Name, employ.NetSalary());`

- **Explicação:**
    - **`System.out.println("");`**: Exibe uma linha em branco para espaçamento no console.
    - **`System.out.printf("Employee: %s, U$%.2f\n", employ.Name, employ.NetSalary());`**: Usa `printf` para formatar a saída. Ele imprime o nome do empregado (`employ.Name`) e o salário líquido (`employ.NetSalary()`), formatado com duas casas decimais (`%.2f`). Presume-se que o método `NetSalary()` calcula o salário líquido, subtraindo o imposto do salário bruto.

---

### Linha 24:


`System.out.println("");`

- **Explicação:** Exibe mais uma linha em branco para separação no console.

---

### Linha 26-27:


`System.out.print("which percentage to increase salary? "); double perce = sc.nextDouble();`

- **Explicação:**
    - **`System.out.print("which percentage to increase salary? ");`**: Exibe a mensagem solicitando ao usuário que insira a porcentagem de aumento salarial.
    - **`double perce = sc.nextDouble();`**: Lê a porcentagem digitada pelo usuário e armazena-a na variável `perce`.

---

### Linha 29:

`System.out.println("");`

- **Explicação:** Exibe outra linha em branco no console.

---

### Linha 30:

`employ.IncreaseSalary(perce);`

- **Explicação:** Chama o método `IncreaseSalary` no objeto `employ`, passando como argumento a porcentagem de aumento salarial (`perce`). Presume-se que este método aumenta o salário bruto em função dessa porcentagem.

---

### Linha 32:

`System.out.println("Updated data: " + employ);`

- **Explicação:** Exibe os dados atualizados do empregado. Como o objeto `employ` está sendo usado diretamente na impressão, o método `toString()` da classe `Employee` deve estar implementado para exibir as informações do empregado de maneira formatada.

---

### Linha 34:

`sc.close();`

- **Explicação:** Fecha o objeto `Scanner` para liberar os recursos. É uma boa prática fechar o `Scanner` após o uso.

---

### Resumo Geral

O programa solicita ao usuário informações sobre um empregado, como nome, salário bruto e valor de imposto. Ele calcula e exibe o salário líquido, que é o salário bruto menos o imposto. O programa também permite ao usuário aumentar o salário com base em uma porcentagem inserida e, em seguida, exibe os dados atualizados do empregado.

A classe `Employee` é fundamental neste programa, mas não foi fornecida. Presume-se que ela contém os atributos `Name`, `GrossSalary`, `Tax` e métodos como `NetSalary()` e `IncreaseSalary()`.
```

## Código 2 e análise
```java
CÓDIGO 2
public class Employee {

    public String Name;
    public double GrossSalary;
    public double Tax;
    
    public double NetSalary(){
        return GrossSalary - Tax;
    }

    public void IncreaseSalary(double percentage){
        GrossSalary += GrossSalary * percentage / 100;
    }

    public String toString() {
        return Name + ", $ " + String.format("%.2f", NetSalary());
        }
}
```

```java
ANÁLISE
### Linha 1:

`public class Employee {`

- **Explicação:** Declara a classe `Employee`. Esta classe é pública, ou seja, pode ser acessada de outras classes. Ela vai armazenar e manipular as informações de um empregado.

---

### Linha 2-4:


`public String Name; public double GrossSalary; public double Tax;`

- **Explicação:** Estas são as variáveis de instância públicas da classe `Employee`:
    - **`Name`**: Armazena o nome do empregado, um valor do tipo `String`.
    - **`GrossSalary`**: Armazena o salário bruto do empregado, um valor do tipo `double` (número decimal).
    - **`Tax`**: Armazena o valor do imposto a ser subtraído do salário bruto, também do tipo `double`.

---

### Linha 6-8:

`public double NetSalary(){     return GrossSalary - Tax; }`

- **Explicação:**
    - **`NetSalary()`**: Este é um método público que retorna o salário líquido do empregado. Ele é do tipo `double` e não recebe parâmetros.
    - **`return GrossSalary - Tax;`**: Calcula o salário líquido subtraindo o valor do imposto (`Tax`) do salário bruto (`GrossSalary`) e retorna o valor.

---

### Linha 10-12:


`public void IncreaseSalary(double percentage){     GrossSalary += GrossSalary * percentage / 100; }`

- **Explicação:**
    - **`IncreaseSalary(double percentage)`**: Este é um método público que recebe uma porcentagem como argumento (`percentage`) e aumenta o salário bruto do empregado com base nessa porcentagem.
    - **`GrossSalary += GrossSalary * percentage / 100;`**: O salário bruto é aumentado ao multiplicar o valor atual do `GrossSalary` pela porcentagem fornecida e dividir por 100, o que corresponde ao cálculo de aumento percentual. Esse valor é então somado ao salário bruto.

---

### Linha 14-16:

`public String toString() {     return Name + ", $ " + String.format("%.2f", NetSalary()); }`

- **Explicação:**
    - **`toString()`**: Este é um método sobrescrito da classe `Object` que retorna uma representação em formato de `String` do objeto `Employee`. Ele será automaticamente chamado sempre que o objeto `Employee` for usado em um contexto onde uma string é necessária (por exemplo, ao imprimir o objeto).
    - **`return Name + ", $ " + String.format("%.2f", NetSalary());`**: A saída consiste no nome do empregado, seguido por ", $ " e o salário líquido, formatado com duas casas decimais usando `String.format()`.

---

### Resumo Geral

A classe `Employee` possui três atributos públicos (`Name`, `GrossSalary` e `Tax`) que armazenam as informações básicas de um empregado. Ela inclui métodos para:

- **`NetSalary()`**: Calcular e retornar o salário líquido do empregado, subtraindo o imposto do salário bruto.
- **`IncreaseSalary(double percentage)`**: Aumentar o salário bruto com base em uma porcentagem fornecida.
- **`toString()`**: Retornar uma string formatada com o nome e o salário líquido do empregado.
```





---
---

3. Fazer um programa para ler o nome de um aluno e as três notas que ele obteve nos três trimestres do ano (primeiro trimestre vale 30 e o segundo e terceiro valem 35 cada). Ao final, mostrar qual a nota final do aluno no ano. Dizer também se o aluno está aprovado (PASS) ou não (FAILED) e, em caso negativo, quantos pontos faltam para o aluno obter o mínimo para ser aprovado (que é 60% da nota). Você deve criar uma classe Student para resolver este problema
![[Ex_fixação_3.jpg]]
