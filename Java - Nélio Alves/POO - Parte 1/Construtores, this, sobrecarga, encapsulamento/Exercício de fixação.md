Em um banco, para se cadastrar uma conta bancária, é necessário informar o número da conta, o nome do titular da conta, e o valor de depósito inicial que o titular depositou ao abrir a conta. Este valor de depósito inicial, entretanto, é opcional, ou seja: se o titular não tiver dinheiro a depositar no momento de abrir sua conta, o depósito inicial não será feito e o saldo inicial da conta será, naturalmente, zero. Importante: uma vez que uma conta bancária foi aberta, o número da conta nunca poderá ser alterado. Já o nome do titular pode ser alterado (pois uma pessoa pode mudar de nome por ocasião de casamento, por exemplo). Por fim, o saldo da conta não pode ser alterado livremente. É preciso haver um mecanismo para proteger isso. O saldo só aumenta por meio de depósitos, e só diminui por meio de saques. Para cada saque realizado, o banco cobra uma taxa de $ 5.00. Nota: a conta pode ficar com saldo negativo se o saldo não for suficiente para realizar o saque e/ou pagar a taxa. Você deve fazer um programa que realize o cadastro de uma conta, dando opção para que seja ou não informado o valor de depósito inicial. Em seguida, realizar um depósito e depois um saque, sempre mostrando os dados da conta após cada operação

![[exfixação.jpg]]

# Análise da classe Account

```java
CÓDIGO 
package entities;  
public class Account {  
    private int number;  
    private String holder;  
    private double balance;  
  
    public Account(int number, String holder) {  
        this.number = number;  
        this.holder = holder;  
    }  
    public Account(double initialDeposit, String holder, int number) {  
        deposit(initialDeposit);  
        this.holder = holder;  
        this.number = number;  
    }  
  
    public double getBalance() {  
        return balance;  
    }  
    public String getHolder() {  
        return holder;  
    }  
    public void setHolder(String holder) {  
        this.holder = holder;  
    }  
    public int getNumber() {  
        return number;  
    }  
    public void deposit(double amount){  
        balance += amount;  
    }  
    public void withdraw(double amount){  
        balance -= amount + 5.0;  
    }  
  
    public String toString() {  
        return "Account "  
                + number  
                + ", Holder: "  
                + holder  
                + ", Balance: U$"  
                + String.format("%.2f", balance);  
    }  
}
```

```java
ANÁLISE
### Linha 1:


`package entities;`

- **Explicação:** Declara que a classe `Account` faz parte do pacote `entities`. Pacotes ajudam a organizar classes em diferentes grupos lógicos.

---

### Linha 2:


`public class Account {`

- **Explicação:** Declara a classe pública `Account`, que representa uma conta bancária.

---

### Linha 3-5:


`private int number; 
 private String holder; 
 private double balance;`

- **Explicação:** Declara três atributos privados da classe `Account`:
    - **`number`**: Um número inteiro que identifica a conta.
    - **`holder`**: Uma string que representa o nome do titular da conta.
    - **`balance`**: Um valor `double` que representa o saldo atual da conta. Ele começa com o valor padrão `0.0`.

---

### Linha 7-9:


`public Account(int number, String holder) {     
	this.number = number;     
	this.holder = holder; }`

- **Explicação:**
    - Este é o **construtor** da classe que recebe dois parâmetros: `number` e `holder`.
    - **`this.number = number;`**: Atribui o valor do parâmetro `number` ao atributo `number` da classe.
    - **`this.holder = holder;`**: Atribui o valor do parâmetro `holder` ao atributo `holder` da classe.

---

### Linha 10-13:



public Account(double initialDeposit, String holder, int number) { 
	deposit(initialDeposit);     
	this.holder = holder;     
	this.number = number; }`

- **Explicação:**
    - Este é outro **construtor** que recebe um depósito inicial, o nome do titular e o número da conta.
    - **`deposit(initialDeposit);`**: Chama o método `deposit()` para adicionar o valor do depósito inicial ao saldo.
    - **`this.holder = holder;`** e **`this.number = number;`**: Atribuem os valores de `holder` e `number` aos atributos correspondentes.

---

### Linha 15-17:


`public double getBalance() {     
	return balance; }`

- **Explicação:** Este é um **getter** para o saldo da conta. Retorna o valor atual de `balance`.

---

### Linha 18-20:


`public String getHolder() {     return holder; }`

- **Explicação:** Este é um **getter** para o nome do titular da conta. Retorna o valor atual de `holder`.

---

### Linha 21-23:


`public void setHolder(String holder) {     
	this.holder = holder; }`

- **Explicação:** Este é um **setter** que permite alterar o nome do titular da conta. Atribui o valor de `holder` ao atributo `holder`.

---

### Linha 24-26:


`public int getNumber() {     
	return number; }`

- **Explicação:** Este é um **getter** para o número da conta. Retorna o valor de `number`.

---

### Linha 27-29:


`public void deposit(double amount){     
	balance += amount; }`

- **Explicação:** Este método **adiciona** um valor ao saldo da conta.
    - **`balance += amount;`**: O valor de `amount` é somado ao saldo atual da conta (`balance`).

---

### Linha 30-32:



`public void withdraw(double amount){     
	balance -= amount + 5.0; }`

- **Explicação:** Este método realiza um **saque** da conta. A operação inclui uma taxa de saque de **5.0 unidades monetárias**.
    - **`balance -= amount + 5.0;`**: O valor de `amount` mais a taxa de 5.0 é subtraído do saldo atual.

---

### Linha 34-40:


`public String toString() {     
	return "Account "             
	+ number             
	+ ", Holder: "             
	+ holder             
	+ ", Balance: U$"             
	+ String.format("%.2f", balance); }`

- **Explicação:**
    - O método **`toString()`** é sobrescrito da classe `Object` e retorna uma string formatada com as informações da conta.
    - **`String.format("%.2f", balance);`**: Formata o saldo com duas casas decimais para exibir o valor de forma legível.

---

### Resumo Geral:

- **Atributos:**
    
    - `number` (número da conta), `holder` (nome do titular), e `balance` (saldo da conta).
- **Construtores:**
    
    - Um construtor que inicializa a conta com número e titular.
    - Outro construtor que além de inicializar com número e titular, também permite fazer um depósito inicial.
- **Métodos:**
    
    - **`getBalance()`**, **`getHolder()`**, e **`getNumber()`**: Getters que retornam o saldo, o titular e o número da conta.
    - **`setHolder(String holder)`**: Um setter para alterar o nome do titular.
    - **`deposit(double amount)`**: Método para depositar um valor na conta.
    - **`withdraw(double amount)`**: Método para sacar um valor da conta, com uma taxa adicional de 5.0 unidades.
    - **`toString()`**: Retorna uma representação legível da conta com as informações do número, titular e saldo.
```

# Análise da classe Program

```java
CÓDIGO
package application;  
import entities.Account;  
import java.util.Locale;  
import java.util.Scanner;  
  
public class Program {  
    public static void main(String[] args) {  
        Locale.setDefault(Locale.US);  
        Scanner sc = new Scanner(System.in);  
        Account account;  
  
        System.out.print("Enter account number: ");  
        int number = sc.nextInt();  
  
        System.out.print("Enter account holder: ");  
        sc.nextLine();  
        String holder = sc.nextLine();  
  
        System.out.print("Is there na initial deposit: (y/n)");  
        double response = sc.next().toLowerCase().charAt(0);  
  
        if (response == 'y') {  
            System.out.print("Enter initial deposit value: U$");  
            double initialDeposit = sc.nextDouble();  
            account = new Account(initialDeposit, holder, number);  
        } else {  
            account = new Account(number, holder);  
        }  
  
        System.out.println();  
        System.out.println("Account data: ");  
        System.out.println(account);  
  
        System.out.println();  
        System.out.print("Enter a deposit value: ");  
        double depositValue = sc.nextDouble();  
        account.deposit(depositValue);  
        System.out.println("Updated account data: ");  
        System.out.println(account);  
  
        System.out.println();  
        System.out.print("Enter a withdraw value: U$");  
        double withdrawValue = sc.nextDouble();  
        account.withdraw(withdrawValue);  
        System.out.println("Updated account data: ");  
        System.out.println(account);  
        sc.close();  
    }  
}
```

```java
ANÁLISE
### Linha 1:

`package application;`

- **Explicação:** Declara que a classe `Program` faz parte do pacote `application`.

---

### Linha 2:


`import entities.Account;`

- **Explicação:** Importa a classe `Account` do pacote `entities` para ser utilizada no programa. A classe `Account` define o comportamento e os dados de uma conta bancária.

---

### Linha 3:


`import java.util.Locale;`

- **Explicação:** Importa a classe `Locale` para definir a localidade do programa, usada para padronizar o formato de saída (como números e moeda).

---

### Linha 4:

`import java.util.Scanner;`

- **Explicação:** Importa a classe `Scanner` que será usada para capturar a entrada do usuário via console.

---

### Linha 6:

`public class Program {`

- **Explicação:** Declara a classe `Program`, que contém o método `main` responsável por executar o programa.

---

### Linha 7-9:


`public static void main(String[] args) {     
	Locale.setDefault(Locale.US);     
	Scanner sc = new Scanner(System.in);`

- **Explicação:**
    - **`Locale.setDefault(Locale.US);`**: Define o formato de localidade padrão para os EUA, o que influencia a formatação de valores numéricos (como ponto decimal ao invés de vírgula).
    - **`Scanner sc = new Scanner(System.in);`**: Inicializa um objeto `Scanner` chamado `sc` para capturar a entrada do usuário.

---

### Linha 10:


`Account account;`

- **Explicação:** Declara uma variável do tipo `Account`, chamada `account`, que será usada para armazenar as informações da conta criada posteriormente.

---

### Linha 12-13:


`System.out.print("Enter account number: "); int number = sc.nextInt();`

- **Explicação:** Solicita ao usuário o número da conta e armazena o valor inteiro inserido na variável `number`.

---

### Linha 15-17:


`System.out.print("Enter account holder: "); 
sc.nextLine(); 
String holder = sc.nextLine();`

- **Explicação:**
    - **`sc.nextLine();`**: Este comando "consome" a quebra de linha que ficou no buffer após o uso de `nextInt()`, para evitar problemas ao capturar o próximo `nextLine()`.
    - **`holder = sc.nextLine();`**: Captura o nome do titular da conta (uma string) e armazena na variável `holder`.

---

### Linha 19-20:


`System.out.print("Is there an initial deposit: (y/n)"); 
double response = sc.next().toLowerCase().charAt(0);`

- **Explicação:**
    - Pergunta ao usuário se haverá um depósito inicial, e captura a primeira letra da resposta, convertida para minúscula.
    - **`sc.next().toLowerCase().charAt(0)`**: Captura a próxima entrada como string, converte para minúsculas e seleciona o primeiro caractere (resposta 'y' ou 'n').

---

### Linha 22-26:


`if (response == 'y') {     
	System.out.print("Enter initial deposit value: U$");     
	double initialDeposit = sc.nextDouble();     
	account = new Account(initialDeposit, holder, number); } 
else {     
	account = new Account(number, holder); }`

- **Explicação:**
    - **Se** a resposta for 'y', solicita o valor do depósito inicial e cria uma nova conta (`account`) usando o construtor que aceita `initialDeposit`, `holder` e `number`.
    - **Caso contrário**, cria a conta sem depósito inicial usando o outro construtor, que só aceita `number` e `holder`.

---

### Linha 28-30:


`System.out.println(); 
System.out.println("Account data: "); 
System.out.println(account);`

- **Explicação:** Exibe os dados da conta utilizando o método `toString()` da classe `Account`, que formata a saída com o número da conta, o titular e o saldo.

---

### Linha 32-35:



`System.out.print("Enter a deposit value: "); 
double depositValue = sc.nextDouble(); 
account.deposit(depositValue); 
System.out.println("Updated account data: "); 
System.out.println(account);`

- **Explicação:**
    - Solicita ao usuário o valor a ser depositado e chama o método `deposit()` da classe `Account`, que atualiza o saldo.
    - Exibe os dados atualizados da conta com o saldo após o depósito.

---

### Linha 37-41:


`System.out.print("Enter a withdraw value: U$"); 
double withdrawValue = sc.nextDouble(); 
account.withdraw(withdrawValue); 
System.out.println("Updated account data: "); 
System.out.println(account);`

- **Explicação:**
    - Solicita o valor a ser sacado e chama o método `withdraw()`, que subtrai o valor do saldo (com uma taxa adicional de 5.0 unidades monetárias).
    - Exibe os dados atualizados da conta após o saque.

---

### Linha 42:

`sc.close();`

- **Explicação:** Fecha o `Scanner` para liberar os recursos associados à entrada de dados.
```
