# Aula120 - #Enumerações 

### *Enumeração*
- É um tipo especial que serve para especificar de forma literal um conjunto de constantes relacionadas
- *Palavra chave em Java*: #enum
- *Vantagem*: 
	- Melhor semântica, código mais legível e auxiliado pelo compilador

### *Exemplo de um ciclo de vida de um pedido*
![[enum.jpg]]

*Para representar esses estados de uma forma semanticamente boa, utilizamos as #Enumerações*

```java
package entities.enums;
public enum OrderStatus{
	PENDING_PAYMENT,
	PROCESSING,
	SHIPPED,
	DELIVERED;
	//definindo os valores possíveis para os status de pedidos
}
```

E em posse desse tipo enumerado,  podemos então criar uma classe pedido, podemos declarar um atributo `status` 
```java
package entities
import java.util.Date;
import entities.enums.OrderStatus;

public class Order {
	private Integer id;
	private Date moment;
	priavte OrderStatus status;
}
```


---
---

### *Convertendo de String para enum*
Utilizamos um #valueOf para converter do tipo String para o tipo order:
```java
Order order = new Order(1080, new Date(), OrderStatus.PENDING_PAYMENT); // instanciando  
  
OrderStatus os1 = OrderStatus.DELIVERED;  
OrderStatus os2 = OrderStatus.valueOf("DELIVERED"); 
// convertendo do tipo String para o tipo order
```


---
---

### Diagramas UML de Enums

![[Diagram 4.svg]]

---
---

## Exemplo completo: 

#### *Classe Program*
```java

package application;  
import entities.Order;  
import entities_enums.OrderStatus;  
import java.util.Date;  
  
public class Program {  
    public static void main(String[] args) {  
        Order order = new Order(1080, new Date(), OrderStatus.PENDING_PAYMENT); // instanciando  
  
        OrderStatus os1 = OrderStatus.DELIVERED;  
        OrderStatus os2 = OrderStatus.valueOf("DELIVERED"); // convertendo do tipo String para o tipo order  
  
        System.out.println(order);  
        System.out.println(os1);  
        System.out.println(os2);  
    }  
}
```

**Explicação:**

- **`package application;`**: Define o pacote onde a classe `Program` está localizada.
- **`import entities.Order;`** e **`import entities_enums.OrderStatus;`**: Importa as classes `Order` e `OrderStatus` de outros pacotes, permitindo seu uso na classe `Program`.
- **`public class Program { ... }`**: Declara a classe principal da aplicação.
- **`public static void main(String[] args) { ... }`**: O ponto de entrada da aplicação. O Java inicia a execução a partir desse método.
- **`Order order = new Order(1080, new Date(), OrderStatus.PENDING_PAYMENT);`**: Cria uma nova instância da classe `Order`, inicializando-a com um ID (`1080`), a data atual (`new Date()`), e um status inicial (`OrderStatus.PENDING_PAYMENT`).
- **`OrderStatus os1 = OrderStatus.DELIVERED;`**: Atribui diretamente um valor da enumeração `OrderStatus` à variável `os1`.
- **`OrderStatus os2 = OrderStatus.valueOf("DELIVERED");`**: Converte a string `"DELIVERED"` para o correspondente valor da enumeração `OrderStatus`. Isso é útil para situações em que o estado do pedido pode ser representado como uma string (por exemplo, em entradas do usuário ou dados de um banco de dados).
- **`System.out.println(order);`**: Imprime os detalhes do pedido, utilizando o método `toString()` da classe `Order`.
- **`System.out.println(os1);` e `System.out.println(os2);`**: Imprime os valores das variáveis `os1` e `os2`, que representam o status do pedido.

#### *Classe Order*
```java
package entities;  
import entities_enums.OrderStatus;  
import java.util.Date;  
  
public class Order {  
    private Integer id;  
    private Date moment;  
    private OrderStatus status;  
  
    public Order(){  
    }  
    public Order(Integer id, Date moment, OrderStatus status) {  
        this.id = id;  
        this.moment = moment;  
        this.status = status;  
    }  
  
    public Integer getId() {  
        return id;  
    }  
  
    public void setId(Integer id) {  
        this.id = id;  
    }  
  
    public Date getMoment() {  
        return moment;  
    }  
  
    public void setMoment(Date moment) {  
        this.moment = moment;  
    }  
  
    public OrderStatus getStatus() {  
        return status;  
    }  
  
    public void setStatus(OrderStatus status) {  
        this.status = status;  
    }  
  
    @Override  
    public String toString() {  
        return "Order{" +  
                "id=" + id +  
                ", moment=" + moment +  
                ", status=" + status +  
                '}';  
    }  
}
```

**Explicação:**

- **`package entities;`**: Define o pacote da classe `Order`.
- **`import entities_enums.OrderStatus;`** e **`import java.util.Date;`**: Importa a enumeração `OrderStatus` e a classe `Date`, permitindo seu uso na classe `Order`.
- **`public class Order { ... }`**: Declara a classe que representa um pedido.
- **Atributos**:
    - **`private Integer id;`**: Armazena o ID do pedido.
    - **`private Date moment;`**: Armazena a data e hora em que o pedido foi criado.
    - **`private OrderStatus status;`**: Armazena o status atual do pedido, utilizando a enumeração `OrderStatus`.
- **Construtores**:
    - **`public Order() {}`**: Construtor padrão que permite a criação de um pedido sem inicialização.
    - **`public Order(Integer id, Date moment, OrderStatus status) { ... }`**: Construtor que inicializa os atributos da classe ao criar um novo pedido.
- **Métodos Getter e Setter**: Fornecem acesso aos atributos privados, permitindo a leitura e modificação dos valores.
- **`@Override public String toString() { ... }`**: Método sobrescrito que define como a instância da classe `Order` será representada como uma string. Útil para depuração e impressão de informações sobre o pedido.

#### *Enum OrderStatus*
```java
package entities_enums;  
public enum OrderStatus {  
    PENDING_PAYMENT,  
    PROCESSING,  
    SHIPPED,  
    DELIVERED;  
}
```

**Explicação:**

- **`package entities_enums;`**: Define o pacote da enumeração `OrderStatus`.
- **`public enum OrderStatus { ... }`**: Declara uma enumeração chamada `OrderStatus`, que lista os possíveis estados de um pedido. As enumerações são úteis para limitar os valores que uma variável pode assumir e melhorar a legibilidade do código.
- **Valores da Enum**:
    - **`PENDING_PAYMENT`**: Indica que o pagamento está pendente.
    - **`PROCESSING`**: Indica que o pedido está sendo processado.
    - **`SHIPPED`**: Indica que o pedido foi enviado.
    - **`DELIVERED`**: Indica que o pedido foi entregue.


---
---
# Aula122 - #Composições

- É um tipo de associação que permite que um objeto contenha outro
- *Relação* "tem-um" ou "tem-vários"
- *Vantagens:*
	- Organização: divisão de responsabilidade 
	- Coesão
	- Flexibilidade
	- Reuso
- *Nota:*
	- Embora o símbolo UML para composição (todo-parte) seja o diamante preto, neste contexto estamos chamando de composição qualquer associação tipo "tem-um" ou "tem-vários"
![[entities.jpg]]

![[services.jpg]]

Quando houver uma composição do tipo "tem-vários" essa composição precisa ser declarada no tipo List e já instanciada. Além disso, uma declaração do tipo "tem-vários" não é incluída no construtor
```java
private List<HourContract> contracts = new ArrayList<>();
```


 ![[worker.jpg]]

```java
package application;  
import entities.Department;  
import entities.HourContract;  
import entities.Worker;  
import entities.enums.WorkerLevel;  
import java.text.ParseException;  
import java.text.SimpleDateFormat;  
import java.util.Date;  
import java.util.Locale;  
import java.util.Scanner;  
  
public class Program {  
    public static void main(String[] args)  throws ParseException {  
        Locale.setDefault(Locale.US);  
        Scanner sc = new Scanner(System.in);  
        SimpleDateFormat sdf = new SimpleDateFormat("dd/mm/yyyy");  
  
        System.out.print("Enter a department name: ");  
        String departmentName = sc.nextLine();  
        System.out.println("Enter worker data: ");  
        System.out.print("Name: ");  
        String  workerName = sc.nextLine();  
        System.out.print("Level: ");  
        String workerLevel = sc.nextLine();  
        System.out.print("Base salary: U$");  
        double baseSalary = sc.nextDouble();  
  
        Worker worker = new Worker(workerName, WorkerLevel.valueOf(workerLevel), baseSalary, new Department(departmentName));  
  
        System.out.print("How many contracts to this worker? ");  
        int n = sc.nextInt();  
  
        for (int i=1;i<=n;i++){  
            System.out.println("Enter contract #"+i + " data:");  
            System.out.print("Data (DD/MM/YYYY): ");  
            Date contractDate = sdf.parse(sc.next());  
            System.out.print("Value per hour: U$");  
            double valuePerHour = sc.nextDouble();  
            System.out.print("Duration (hours): ");  
            int hours = sc.nextInt();  
            HourContract contract = new HourContract(contractDate, valuePerHour, hours);  
            worker.addContract(contract);  
        }  
        System.out.println();  
        System.out.print("Enter month and year to calculate income (MM/YYYY): ");  
        String monthAndYear = sc.next();  
        int month =Integer.parseInt(monthAndYear.substring(0, 2));  
        int year = Integer.parseInt(monthAndYear.substring(3));  
        System.out.println("Name: "+ worker.getName());  
        System.out.println("Department: "+ worker.getDepartment().getName());  
        System.out.println("Income for: "+ monthAndYear + ": U$" + String.format("%.2f", worker.income(year, month)));  
    }  
}

package entities;  
  
public class Department {  
    private String name;  
  
    public Department(){  
    }  
    public Department(String name) {  
        this.name = name;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public void setName(String name) {  
        this.name = name;  
    }  
}

package entities;  
  
import java.util.Date;  
  
public class HourContract {  
    private Date date;  
    private Double valuePerHour;  
    private Integer hours;  
  
    public HourContract() {  
    }  
    public HourContract(Date date, Double valuePerHour, Integer hours) {  
        this.date = date;  
        this.valuePerHour = valuePerHour;  
        this.hours = hours;  
    }  
  
    public Date getDate() {  
        return date;  
    }  
  
    public void setDate(Date date) {  
        this.date = date;  
    }  
  
    public Double getValuePerHour() {  
        return valuePerHour;  
    }  
  
    public void setValuePerHour(Double valuePerHour) {  
        this.valuePerHour = valuePerHour;  
    }  
  
    public Integer getHours() {  
        return hours;  
    }  
  
    public void setHours(Integer hours) {  
        this.hours = hours;  
    }  
  
    public double totalValue(){  
        return valuePerHour * hours;  
    }  
}

package entities.enums;  
  
public enum WorkerLevel {  
    JUNIOR,  
    MID_LEVEL,  
    SENIOR;  
}

package entities;  
import entities.enums.WorkerLevel;  
import java.util.ArrayList;  
import java.util.Calendar;  
import java.util.List;  
  
public class Worker {  
    private String name;  
    private WorkerLevel level;  
    private Double baseSalary;  
    private Department department;  
    private List<HourContract> contracts = new ArrayList<>();  
  
    public Worker() {  
    }  
    public Worker(String name, WorkerLevel level, Double baseSalary, Department department) {  
        this.name = name;  
        this.level = level;  
        this.baseSalary = baseSalary;  
        this.department = department;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public void setName(String name) {  
        this.name = name;  
    }  
  
    public WorkerLevel getLevel() {  
        return level;  
    }  
  
    public void setLevel(WorkerLevel level) {  
        this.level = level;  
    }  
  
    public Double getBaseSalary() {  
        return baseSalary;  
    }  
  
    public void setBaseSalary(Double baseSalary) {  
        this.baseSalary = baseSalary;  
    }  
  
    public Department getDepartment() {  
        return department;  
    }  
  
    public void setDepartment(Department department) {  
        this.department = department;  
    }  
  
    public List<HourContract> getContracts() {  
        return contracts;  
    }  
  
    public void addContract(HourContract contract){  
        contracts.add(contract);  
    }  
  
    public void removeContract(HourContract contract){  
        contracts.remove(contract);  
    }  
  
    public double income(int year, int month){  
        double sum = baseSalary;  
        Calendar cal = Calendar.getInstance();  
        for (HourContract c: contracts){  
            cal.setTime(c.getDate());  
            int c_year = cal.get(Calendar.YEAR);  
            int c_month = 1 + cal.get(Calendar.MONTH);  
            if (year == c_year && month == c_month){  
                sum += c.totalValue();  
            }  
        }  
        return sum;  
    }  
}
```

#### *Análise:*
### 1. **Classe `Program` (Classe principal)**

Esta é a classe que contém o método `main`, onde o programa é executado. O propósito desta classe é gerenciar a interação com o usuário via console e coletar os dados para criar um objeto `Worker` e adicionar contratos para este trabalhador.

- **Importações**:
    
    - São importados pacotes como `Scanner`, `Locale`, `SimpleDateFormat`, e classes do próprio projeto, como `Worker`, `Department`, e `HourContract`.
    - `Locale.setDefault(Locale.US)` define o formato numérico para o padrão americano (ponto decimal, em vez de vírgula).
- **SimpleDateFormat e ParseException**:
    
    - O formato de data definido como `"dd/mm/yyyy"` será usado para interpretar as datas inseridas pelo usuário. O `ParseException` é declarado no método `main` para tratar exceções quando o formato de data inserido pelo usuário não corresponde ao esperado.
- **Entrada do usuário**:
    
    - O código solicita diversas informações ao usuário, como o nome do departamento, nome do trabalhador, nível de trabalhador (junior, mid-level, senior) e salário base.
    
    ```java
Worker worker = new Worker(workerName,WorkerLevel.valueOf(workerLevel), baseSalary, new Department(departmentName));
```    
    Aqui, é criado um objeto `Worker` passando o nome, nível (convertido de `String` para enum usando `WorkerLevel.valueOf()`), salário base, e um novo departamento.
    
- **Contratos de trabalho**:
    
    - O loop for coleta os contratos (data, valor por hora e duração em horas).
```java
HourContract contract = new HourContract(contractDate,valuePerHour, hours); 
worker.addContract(contract);
 ```

    A cada iteração, um novo contrato é criado e adicionado ao trabalhador usando o método `addContract`.
    
- **Cálculo de rendimento**:
    
    - Após a entrada de contratos, o usuário insere um mês e ano para calcular o rendimento daquele mês.
    

    ```java
int month = Integer.parseInt(monthAndYear.substring(0, 2)); 
int year = Integer.parseInt(monthAndYear.substring(3));
    ```
    Isso extrai o mês e o ano da string fornecida pelo usuário e os converte para inteiros.
    
    - O método `income(year, month)` é chamado para calcular o rendimento do trabalhador naquele mês, levando em conta o salário base e os contratos daquele período.

### 2. **Classe `Department`**

Esta classe é bastante simples, sendo utilizada para armazenar o nome de um departamento e fornecer métodos getters e setters.

- **Construtores**:
    
    - Um construtor padrão (vazio) e um que inicializa o `name` do departamento.
- **Getters e Setters**:
    
    - Métodos que permitem acessar e modificar o nome do departamento.

### 3. **Classe `HourContract`**

Esta classe representa um contrato por hora, ou seja, a relação de uma tarefa ou projeto que um trabalhador realiza baseado em horas.

- **Atributos**:
    
    - `date` (data do contrato),
    - `valuePerHour` (valor pago por hora),
    - `hours` (quantidade de horas trabalhadas).
- **Construtores**:
    
    - Um construtor padrão e um que inicializa os atributos.
- **Getters e Setters**:
    
    - Métodos que permitem acessar e modificar os valores de `date`, `valuePerHour` e `hours`.
- **Método `totalValue()`**:
    
    - O método mais importante desta classe (apesar de não estar explicitamente listado aqui) seria o cálculo do valor total do contrato: `totalValue()`, que multiplicaria o `valuePerHour` pelo número de `hours`.

### 4. **Enum `WorkerLevel`**

Esta é uma enumeração (`enum`) que define os níveis possíveis de um trabalhador:

- **Valores**:
    - `JUNIOR`, `MID_LEVEL`, `SENIOR`.
    - Usar uma enum neste caso é uma boa prática, pois evita erros com strings incorretas e proporciona um conjunto fixo de opções.

### 5. **Classe `Worker`**

Esta é a classe central da aplicação, representando um trabalhador.

- **Atributos**:
    
    - `name`: Nome do trabalhador.
    - `level`: O nível do trabalhador, do tipo `WorkerLevel`.
    - `baseSalary`: Salário base.
    - `department`: Um objeto do tipo `Department`, associando o trabalhador a um departamento.
    - `contracts`: Lista de contratos (`HourContract`) que o trabalhador possui.
- **Construtores**:
    
    - Um construtor padrão e um que inicializa o nome, nível, salário e departamento.
- **Métodos**:
    
    - **`addContract(HourContract contract)`**: Adiciona um contrato à lista de contratos.
        
    - **`removeContract(HourContract contract)`**: Remove um contrato da lista.
        
    - **`income(int year, int month)`**:
        
        - Calcula o rendimento total do trabalhador para um determinado mês e ano.
        - Ele começa com o salário base e adiciona o valor total de todos os contratos cujo mês e ano coincidam com os passados como parâmetros.
        ```java
        if (year == c_year && month == c_month) {     
	        sum += c.totalValue(); }
        ```
        O `Calendar` é usado para extrair o ano e o mês do contrato e verificar se correspondem ao ano e mês desejados.
        

### Decisões de Design:

- **Separação de Responsabilidades**: Cada classe tem uma responsabilidade única e bem definida:
    
    - `Program` cuida da lógica de entrada e saída e chama os métodos apropriados.
    - `Worker` encapsula os dados do trabalhador e seus contratos.
    - `HourContract` é responsável por armazenar informações sobre contratos específicos.
    - `Department` mantém os dados de um departamento.
    - `WorkerLevel` é um enum para representar os níveis de trabalho, o que melhora a clareza e a segurança do código.
- **Coesão**: Todas as classes têm alta coesão, ou seja, seus atributos e métodos estão intimamente relacionados à função de cada classe.
    
- **Flexibilidade e Expansibilidade**: O uso de listas e enumerações torna o código facilmente expansível, pois novos níveis de trabalhador ou tipos de contrato podem ser adicionados sem grandes mudanças na estrutura do código.


---
---

### Análise detalhada de blocos:
```java
public double income(int year, int month){  
    double sum = baseSalary;  
    for (HourContract c: contracts){  
        LocalDate contractDate = c.getDate().toInstant().atZone(ZoneId.systemDefault()).toLocalDate();  
        int c_year = contractDate.getYear();  
        int c_month = contractDate.getMonthValue();  
        if (year == c_year && month == c_month){  
            sum += c.totalValue();  
        }  
    }  
    return sum;  
}
```

### Declaração e Inicialização de Variáveis

```java

public double income(int year, int month) {     
	double sum = baseSalary;
```
- **`double sum = baseSalary;`**: A variável `sum` é inicializada com o valor do salário base do trabalhador. Isto significa que o cálculo começa com o salário base, e os contratos daquele mês específico serão adicionados a esse valor.

### Iteração sobre os contratos
```java
for (HourContract c : contracts) {     
	LocalDate contractDate = c.getDate().toInstant().atZone(ZoneId.systemDefault()).toLocalDate();
```
- **`for (HourContract c : contracts)`**: O laço `for-each` percorre todos os contratos de trabalho (`contracts`) que o trabalhador possui. Cada contrato é representado pela variável `c`, que é do tipo `HourContract`.
    
- **Conversão para `LocalDate`**:
    
    ```java
    LocalDate contractDate = c.getDate().toInstant().atZone(ZoneId.systemDefault()).toLocalDate();
  ```  
    - O contrato contém uma data no formato `Date` (um tipo antigo da API de datas do Java). Para facilitar o manuseio, ele é convertido para um `LocalDate`, que faz parte da API mais moderna de datas no Java 8+.
    - A sequência `c.getDate().toInstant().atZone(ZoneId.systemDefault()).toLocalDate()` faz a conversão.
        - `c.getDate().toInstant()` converte o objeto `Date` para um `Instant`, que é um ponto no tempo.
        - `atZone(ZoneId.systemDefault())` define o fuso horário do sistema (necessário para a conversão).
        - Finalmente, `toLocalDate()` converte o instante de tempo em um objeto `LocalDate`, que contém apenas a data (sem o horário).

### Extração do Ano e Mês do Contrato

```java
int c_year = contractDate.getYear(); int c_month = contractDate.getMonthValue();
```
- **`int c_year = contractDate.getYear();`**: Extraímos o ano da data do contrato usando o método `getYear()` do `LocalDate`.
    
- **`int c_month = contractDate.getMonthValue();`**: Extraímos o mês da data do contrato com o método `getMonthValue()`. Aqui, ao contrário do `Calendar`, o mês já é baseado em 1 (janeiro = 1, dezembro = 12), então não é necessário adicionar `1`.
    

### Verificação de Ano e Mês

```java
`if (year == c_year && month == c_month) {     
	sum += c.totalValue(); 
	}
```
- **`if (year == c_year && month == c_month)`**: Este bloco verifica se o ano (`c_year`) e o mês (`c_month`) do contrato correspondem ao ano e mês fornecidos como parâmetros para o método.
    - Se a data do contrato coincide com o ano e mês informados, o valor do contrato será somado ao rendimento.
- **`sum += c.totalValue();`**: Se a condição for verdadeira, o valor total do contrato (`c.totalValue()`) é adicionado à variável `sum`. O método `totalValue()` de `HourContract` retorna o valor total do contrato, calculado como o número de horas trabalhadas multiplicado pelo valor pago por hora.

### Retorno do Valor Total


```java
return sum;
```
- Após o laço percorrer todos os contratos, o método retorna o valor acumulado em `sum`, que representa o rendimento total do trabalhador para o mês e ano fornecidos. Esse valor inclui tanto o salário base quanto o total dos contratos realizados naquele período.

### Decisões de Design e Benefícios do `LocalDate`

1. **Uso da API Moderna de Datas (`LocalDate`)**:
    
    - A API antiga de `Date` e `Calendar` tem algumas limitações e é considerada menos intuitiva. O `LocalDate` oferece métodos mais claros e diretos para trabalhar com datas, como `getYear()` e `getMonthValue()`, sem a necessidade de ajustes adicionais (como adicionar 1 ao mês).
    - Isso torna o código mais legível e menos propenso a erros, além de mais compatível com as boas práticas modernas de programação Java.
2. **Filtro por Mês e Ano**:
    
    - O método filtra os contratos de trabalho para o mês e ano específicos fornecidos, permitindo que o trabalhador veja o rendimento de um período específico. Isso é útil em situações onde o trabalhador pode ter contratos em diferentes meses, e o cálculo foca apenas no mês desejado.
3. **Acumulação Incremental**:
    
    - Usar `sum +=` permite que o cálculo seja incremental: a cada contrato que corresponde ao mês e ano, seu valor total é somado ao salário base.

### Resumo:

Este método faz uma filtragem eficiente de contratos por data e calcula o rendimento total de um trabalhador para um mês e ano específicos. A utilização de `LocalDate` facilita o trabalho com datas, tornando o código mais legível e mantendo a clareza do processo de extração de ano e mês de cada contrato.

---
---

### Análise de blocos 2:
Esse bloco de código faz parte da classe `Worker` e define os **atributos** que descrevem as características e relacionamentos de um trabalhador (ou "worker") em um sistema. Vamos analisar detalhadamente cada um dos componentes desse bloco:

### Declaração da Classe

```java
public class Worker {
```
- **`public class Worker`**: A palavra-chave `public` define que a classe `Worker` pode ser acessada por outras classes dentro e fora do pacote. A palavra-chave `class` indica que estamos definindo uma nova classe em Java chamada `Worker`, que provavelmente representa um trabalhador no contexto do sistema. Essa classe armazenará as informações básicas sobre um trabalhador e seus relacionamentos, como departamento e contratos.

### Atributos da Classe

A seguir, cada atributo da classe `Worker` é declarado com diferentes tipos de dados.

---
```java
private String name;
```
- **`private`**: O modificador `private` indica que esse atributo só pode ser acessado diretamente dentro da própria classe `Worker`. Isso faz parte do princípio de encapsulamento, garantindo que outras classes não possam modificar ou acessar o atributo diretamente, mas somente por meio de métodos (getters e setters).
    
- **`String name`**: Este atributo armazena o **nome** do trabalhador, que é uma sequência de caracteres (`String`). Ele é crucial para identificar o trabalhador dentro do sistema.
    

---

```
private WorkerLevel level;
```
- **`WorkerLevel level`**: O atributo `level` é do tipo `WorkerLevel`, que é um **enumerador** (enum) definido em outro lugar no código. O `WorkerLevel` provavelmente contém os diferentes níveis de experiência ou posição do trabalhador, como **Junior**, **Mid-Level** e **Senior**.
    
    - O uso de um enum ajuda a restringir os valores possíveis do nível do trabalhador a uma lista pré-definida, prevenindo erros como atribuir valores inválidos ao nível.

---
```java
private Double baseSalary;
```
- **`Double baseSalary`**: Este atributo armazena o **salário base** do trabalhador. O tipo `Double` permite armazenar números de ponto flutuante, ou seja, valores que podem ter casas decimais, como um salário que inclua centavos (por exemplo, 2500.50).
    
    - O **salário base** é o valor fixo que o trabalhador recebe, independentemente de outros pagamentos variáveis, como aqueles derivados de contratos por hora. Ele serve como ponto de partida para cálculos relacionados ao salário total.

---
```java
private Department department;
```
- **`Department department`**: Este atributo define a relação entre um trabalhador e o seu **departamento**. O tipo `Department` é uma **classe** separada que armazena informações relacionadas ao departamento onde o trabalhador atua.
    
    - Essa estrutura reflete um relacionamento típico de agregação: o trabalhador **pertence** a um departamento, o que significa que cada trabalhador tem um departamento associado, mas o departamento pode existir independentemente de um trabalhador específico.

---
```
private List<HourContract> contracts = new ArrayList<>();
```
- **`List<HourContract> contracts`**: O atributo `contracts` é uma lista de contratos de trabalho por hora (`HourContract`). A classe `HourContract` armazena os detalhes de contratos temporários ou eventuais que o trabalhador pode ter.
    
    - O tipo `List` vem da **interface** genérica `List` da biblioteca de coleções do Java, que permite armazenar múltiplos objetos do tipo `HourContract`. Neste caso, o trabalhador pode ter **vários contratos** ao longo de sua carreira.
        
    - O operador `<HourContract>` é usado para especificar que a lista conterá apenas objetos do tipo `HourContract`, garantindo a segurança de tipo (type safety).
        
    - **`= new ArrayList<>();`**: O atributo é inicializado com uma nova instância de `ArrayList`, que é uma implementação concreta da interface `List`. Isso significa que, desde o início, `contracts` é uma lista vazia que pode ser populada ao longo do tempo com diferentes contratos.
        
        - O uso de um `ArrayList` é uma decisão que oferece operações rápidas de acesso e adição de elementos, o que é útil ao armazenar e manipular contratos.

---

### Análise Geral

#### Encapsulamento:

Todos os atributos são declarados como `private`, seguindo as boas práticas de encapsulamento. Isso protege os dados internos da classe de serem acessados ou modificados diretamente de fora da classe. Para interagir com esses atributos, provavelmente existem **métodos públicos** (`getters` e `setters`) que permitem um controle adequado sobre o acesso e a modificação.

#### Design Orientado a Objetos:

A classe `Worker` reflete um design orientado a objetos robusto, onde diferentes objetos, como `Department` e `HourContract`, são agregados à classe `Worker`, permitindo uma representação clara e natural das relações entre o trabalhador, seu departamento e seus contratos.

#### Importância dos Atributos:

- O **nome** identifica o trabalhador.
- O **nível** descreve sua posição na empresa.
- O **salário base** define a remuneração fixa.
- O **departamento** mostra a estrutura organizacional.
- A **lista de contratos** representa trabalhos adicionais que afetam o cálculo de sua remuneração total.


---
---
### Análise de bloco 3:
```java
for (int i=1;i<=n;i++){  
    System.out.println("Enter contract #"+i + " data:");  
    System.out.print("Data (DD/MM/YYYY): ");  
    Date contractDate = sdf.parse(sc.next());  
    System.out.print("Value per hour: U$");  
    double valuePerHour = sc.nextDouble();  
    System.out.print("Duration (hours): ");  
    int hours = sc.nextInt();  
    HourContract contract = new HourContract(contractDate, valuePerHour, hours);  
    worker.addContract(contract);  
}
```

Esse bloco de código é responsável por coletar dados sobre contratos de trabalho de um trabalhador específico e adicionar esses contratos à lista de contratos do trabalhador. Vamos analisar cada parte do código detalhadamente:

### Estrutura do Laço `for`

```java
for (int i = 1; i <= n; i++) {`
```
- **`for (int i = 1; i <= n; i++)`**: Este é um laço `for` que itera de 1 até `n`, onde `n` representa o número total de contratos que o usuário deseja adicionar para o trabalhador.
    - A variável `i` é usada como um contador que inicia em 1 e é incrementada a cada iteração até que o valor de `i` seja maior que `n`.
    - A contagem começa em 1 para que as mensagens exibidas ao usuário (como "contract #1", "contract #2", etc.) sejam mais intuitivas.

### Coleta de Dados do Usuário

Dentro do laço, o código solicita informações sobre cada contrato:

```java
System.out.println("Enter contract #" + i + " data:"); System.out.print("Data (DD/MM/YYYY): "); 
Date contractDate = sdf.parse(sc.next());`
```
- **`System.out.println("Enter contract #" + i + " data:");`**: Exibe uma mensagem pedindo ao usuário para inserir os dados do contrato correspondente ao contador `i`.
    
- **`System.out.print("Data (DD/MM/YYYY): ");`**: Solicita que o usuário insira a data do contrato no formato "DD/MM/YYYY".
    
- **`Date contractDate = sdf.parse(sc.next());`**: Aqui, a data é lida a partir da entrada do usuário.
    
    - `sc.next()` captura a entrada do usuário como uma `String`.
    - `sdf.parse(...)` usa um objeto `SimpleDateFormat` (denotado por `sdf`) para converter essa `String` em um objeto `Date`.
    - Esse método pode lançar uma `ParseException` caso a data não esteja no formato correto. Por isso, é importante garantir que o usuário insira a data no formato especificado.

---

```java
System.out.print("Value per hour: U$"); 
double valuePerHour = sc.nextDouble();
```
- **`System.out.print("Value per hour: U$");`**: Pede ao usuário para inserir o valor pago por hora para o contrato.
    
- **`double valuePerHour = sc.nextDouble();`**: Captura a entrada do usuário e a armazena em `valuePerHour`. Este valor deve ser um número do tipo `double`, representando quanto o trabalhador ganha por cada hora de trabalho.
    

---

```java
System.out.print("Duration (hours): "); int hours = sc.nextInt();
```
- **`System.out.print("Duration (hours): ");`**: Solicita ao usuário que insira a duração do contrato em horas.
    
- **`int hours = sc.nextInt();`**: Captura a entrada do usuário e a armazena na variável `hours`, que é do tipo `int`. Isso indica o número total de horas que o trabalhador vai trabalhar sob esse contrato.
    

---

### Criação do Objeto `HourContract`
```java
HourContract contract = new HourContract(contractDate, valuePerHour, hours);
```
- **`HourContract contract = new HourContract(contractDate, valuePerHour, hours);`**: Um novo objeto `HourContract` é criado utilizando as informações coletadas.
    - O construtor da classe `HourContract` aceita três parâmetros: a data do contrato (`contractDate`), o valor por hora (`valuePerHour`) e a duração em horas (`hours`).
    - Esse objeto `contract` agora contém todas as informações relevantes sobre o contrato específico do trabalhador.

### Adição do Contrato à Lista de Contratos

```
worker.addContract(contract);
```
- **`worker.addContract(contract);`**: Este método chama o método `addContract` da classe `Worker`, que é responsável por adicionar o novo contrato à lista de contratos do trabalhador.
    - A lista de contratos é armazenada no atributo `contracts` da classe `Worker`, e esse método encapsula a lógica de manipulação da lista, garantindo que os contratos sejam gerenciados corretamente.

### Resumo do Bloco

Este bloco de código serve para coletar informações sobre vários contratos de trabalho, um por vez, e adicioná-los à lista de contratos de um trabalhador específico.

#### Principais Pontos:

1. **Interatividade**: O código utiliza a entrada do usuário para coletar dados, tornando a aplicação interativa.
2. **Estrutura de Laço**: Um laço `for` é usado para iterar sobre a quantidade de contratos, permitindo a coleta de dados para cada contrato.
3. **Validação de Data**: O uso de `SimpleDateFormat` para a conversão de data é uma prática comum, embora possa exigir um tratamento de exceções para evitar erros em entradas inválidas.
4. **Objetos**: Cada contrato é encapsulado em um objeto da classe `HourContract`, que fornece uma estrutura clara para representar e manipular os dados do contrato.
5. **Encapsulamento**: O método `addContract` do trabalhador encapsula a lógica de adicionar contratos, mantendo a integridade da lista de contratos.

---
---
### Análise de bloco 4:

```java
Worker worker = new Worker(workerName, WorkerLevel.valueOf(workerLevel), baseSalary, new Department(departmentName));
```

#### 1. **Tipo do Objeto**

- **`Worker worker`**: Aqui, estamos declarando uma variável chamada `worker` do tipo `Worker`. Essa variável irá armazenar a nova instância da classe `Worker` que será criada.

#### 2. **Construtor da Classe `Worker`**

- **`new Worker(...)`**: A palavra-chave `new` é utilizada para criar uma nova instância do objeto. A classe `Worker` possui um construtor que aceita quatro parâmetros:

#### 3. **Parâmetros do Construtor**

- **`workerName`**: Este parâmetro é uma `String` que representa o nome do trabalhador. O valor é obtido anteriormente a partir da entrada do usuário.
    
- **`WorkerLevel.valueOf(workerLevel)`**: Aqui, o parâmetro `workerLevel` (também uma `String`) é convertido para o tipo `WorkerLevel` usando o método estático `valueOf()`.
    
    - O método `valueOf` busca uma constante no enum `WorkerLevel` que corresponda à string fornecida (como **JUNIOR**, **MID_LEVEL** ou **SENIOR**).
    - Se o valor da string não corresponder a nenhuma constante do enum, uma `IllegalArgumentException` será lançada, então é importante garantir que a entrada do usuário esteja correta.
- **`baseSalary`**: Este parâmetro é um `double` que representa o salário base do trabalhador. Ele é obtido da entrada do usuário e será utilizado para inicializar o atributo `baseSalary` na instância do `Worker`.
    
- **`new Department(departmentName)`**: Aqui, estamos criando uma nova instância da classe `Department`, que representa o departamento do trabalhador.
    
    - O construtor da classe `Department` é chamado com o parâmetro `departmentName`, que é uma `String` representando o nome do departamento, coletada da entrada do usuário.
    - Isso cria um novo objeto `Department` que é passado para o construtor do `Worker`, estabelecendo a associação entre o trabalhador e o seu departamento.

### Resumo do Bloco

Este bloco de código é responsável por instanciar um novo trabalhador com os seguintes atributos:

- **Nome**: O nome do trabalhador é atribuído a partir da entrada do usuário.
- **Nível**: O nível do trabalhador é determinado por uma string convertida para o tipo `WorkerLevel`, permitindo uma categorização clara do trabalhador.
- **Salário Base**: O salário base é um valor numérico que define quanto o trabalhador receberá por seu trabalho.
- **Departamento**: O departamento ao qual o trabalhador pertence é representado por um objeto da classe `Department`.

#### Principais Pontos:

1. **Interatividade**: O código depende da entrada do usuário para definir as propriedades do trabalhador.
2. **Enumeração**: O uso do enum `WorkerLevel` garante que apenas valores válidos sejam atribuídos ao nível do trabalhador, aumentando a segurança do tipo e evitando erros.
3. **Composição**: O trabalhador é composto por um departamento, refletindo uma relação de agregação, onde um trabalhador pode estar associado a um departamento, mas um departamento pode existir independentemente de um trabalhador específico.
4. **Encapsulamento**: O uso de construtores permite que a classe `Worker` inicialize seus atributos de forma organizada, protegendo a integridade dos dados e ocultando a complexidade da criação de objetos.

---
---
### Análise de bloco 5:
```java
String monthAndYear = sc.next();  
int month =Integer.parseInt(monthAndYear.substring(0, 2));  
int year = Integer.parseInt(monthAndYear.substring(3));  
System.out.println("Name: "+ worker.getName());  
System.out.println("Department: "+ worker.getDepartment().getName());  
System.out.println("Income for: "+ monthAndYear + ": U$" + String.format("%.2f", worker.income(year, month)));
```

### 1. Coleta do Mês e Ano

```java
String monthAndYear = sc.next();
```
- **`String monthAndYear = sc.next();`**: Aqui, o programa lê uma entrada do usuário na forma de uma string que representa um mês e um ano (por exemplo, "09/2024"). O método `sc.next()` captura a próxima entrada de texto do usuário.

### 2. Extração do Mês e do Ano


```java
int month = Integer.parseInt(monthAndYear.substring(0, 2)); 
int year = Integer.parseInt(monthAndYear.substring(3));
```
- **`int month = Integer.parseInt(monthAndYear.substring(0, 2));`**: Este trecho utiliza o método `substring` para extrair os dois primeiros caracteres da string `monthAndYear`, que correspondem ao mês.
    
    - `substring(0, 2)` retorna os caracteres de índice 0 até 2 (não inclusivo), resultando na parte que representa o mês.
    - `Integer.parseInt(...)` converte essa substring para um inteiro, que será armazenado na variável `month`.
- **`int year = Integer.parseInt(monthAndYear.substring(3));`**: Aqui, o código extrai a parte do ano da string `monthAndYear`.
    
    - `substring(3)` retorna todos os caracteres a partir do índice 3, que correspondem ao ano.
    - O método `Integer.parseInt(...)` converte essa parte da string para um inteiro, que será armazenado na variável `year`.

### 3. Exibição das Informações do Trabalhador

```
System.out.println("Name: " + worker.getName());
```
- **`System.out.println("Name: " + worker.getName());`**: Esta linha exibe o nome do trabalhador, utilizando o método `getName()` da classe `Worker`, que retorna o nome do trabalhador armazenado na instância `worker`.

```java
System.out.println("Department: " + worker.getDepartment().getName());
```
- **`System.out.println("Department: " + worker.getDepartment().getName());`**: Aqui, o programa exibe o nome do departamento do trabalhador.
    - O método `getDepartment()` retorna o objeto `Department` associado ao trabalhador.
    - Em seguida, `getName()` é chamado nesse objeto `Department` para obter o nome do departamento, que é então impresso.

### 4. Cálculo e Exibição da Renda

```java
System.out.println("Income for: " + monthAndYear + ": U$" + String.format("%.2f", worker.income(year, month)));
```
- **`System.out.println("Income for: " + monthAndYear + ": U$" + String.format("%.2f", worker.income(year, month)));`**: Esta linha imprime a renda do trabalhador para o mês e ano especificados pelo usuário.
    - **`worker.income(year, month)`**: Chama o método `income` da classe `Worker`, passando o ano e o mês. Esse método calcula a renda total do trabalhador, incluindo o salário base e a renda proveniente dos contratos para o mês e ano especificados.
    - **`String.format("%.2f", ...)`**: Formata o valor retornado pelo método `income` para que apareça com duas casas decimais. Isso é importante para apresentação monetária, garantindo que o valor esteja no formato correto (por exemplo, "2500.00").
    - A renda é então concatenada à string que especifica o mês e o ano, formando uma mensagem completa que é impressa no console.

### Resumo do Bloco

Esse bloco de código é responsável por coletar o mês e o ano para o qual a renda do trabalhador deve ser calculada e exibir as informações do trabalhador, incluindo seu nome, o nome do departamento e a renda total para o mês e ano especificados.

#### Principais Pontos:

1. **Entrada do Usuário**: O código coleta informações do usuário de forma simples e direta, permitindo que ele especifique o mês e o ano desejados.
2. **Manipulação de Strings**: O uso de `substring` para extrair partes específicas da string é uma maneira eficiente de separar dados em formato conhecido.
3. **Formatação Monetária**: O uso de `String.format("%.2f", ...)` garante que a renda seja exibida de forma legível e apropriada, destacando a importância da apresentação em aplicações financeiras.
4. **Métodos de Acesso**: O uso de métodos como `getName()` e `getDepartment()` demonstra a prática de encapsulamento, que é um princípio fundamental da programação orientada a objetos, promovendo a organização e a segurança dos dados. 

---
---

### Aula125 - Exercício resolvido 2 (demo #StringBuilder)

![[StringBuilder.jpg]]

Quando temos uma composição do tipo "tem-vários" nós não deixamos o método #setters,  porém nós fazemos o método add e remove:
```java
private List<Comment> comments = new ArrayList<>(); // "tem-vários"
public void addComment (Comment comment){  
    comments.add(comment);  
}  
public void removeComment(Comment comment){  
    comments.remove(comment);  
}
```

---
---

## *Análise de código de 2*

### Classe `Comment`
```java
package entities;

public class Comment {
    private String text;

    public Comment() {
    }

    public Comment(String text) {
        this.text = text;
    }

    public String getText() {
        return text;
    }

    public void setText(String text) {
        this.text = text;
    }
}
```
#### Análise:

1. **Pacote:** `package entities;` — Define que esta classe faz parte do pacote `entities`, agrupando-a com outras classes relacionadas.
    
2. **Atributo `text`:**
    
    - `private String text;` — O atributo é privado para proteger o acesso direto, seguindo o princípio de encapsulamento.
3. **Construtores:**
    
    - `public Comment() {}` — Construtor padrão sem parâmetros. Isso é útil para instanciar um objeto sem definir o texto imediatamente, podendo ser preenchido depois.
    - `public Comment(String text) { this.text = text; }` — Construtor com um parâmetro que inicializa o texto do comentário.
4. **Métodos Getter e Setter:**
    
    - `public String getText() { return text; }` — Permite acessar o texto do comentário.
    - `public void setText(String text) { this.text = text; }` — Permite modificar o texto do comentário após a criação do objeto.

### Classe `Post`
```java
package entities;  
import java.time.LocalDateTime;  
import java.time.format.DateTimeFormatter;  
import java.util.ArrayList;  
import java.util.List;  
  
public class Post {  
    private LocalDateTime moment;  
    private String title;  
    private String content;  
    private Integer likes;  
  
    private List<Comment> comments = new ArrayList<>();  
  
    public Post() {  
    }  
    public Post(LocalDateTime moment, String title, String content, Integer likes) {  
        this.moment = moment;  
        this.title = title;  
        this.content = content;  
        this.likes = likes;  
    }  
  
    public LocalDateTime getMoment() {  
        return moment;  
    }  
  
    public void setMoment(LocalDateTime moment) {  
        this.moment = moment;  
    }  
  
    public String getTitle() {  
        return title;  
    }  
  
    public void setTitle(String title) {  
        this.title = title;  
    }  
  
    public String getContent() {  
        return content;  
    }  
  
    public Integer getLikes() {  
        return likes;  
    }  
  
    public void setLikes(Integer likes) {  
        this.likes = likes;  
    }  
  
    public List<Comment> getComments() {  
        return comments;  
    }  
  
    public void setComments(List<Comment> comments) {  
        this.comments = comments;  
    }  
  
    public void addComment (Comment comment){  
        comments.add(comment);  
    }  
  
    public void removeComment(Comment comment){  
        comments.remove(comment);  
    }  
    private static DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");  
  
    public String toString(){  
        StringBuilder sb = new StringBuilder();  
        sb.append(title + "\n");  
        sb.append(likes);  
        sb.append(" Likes - ");  
        sb.append(moment.format(fmt1) + "\n");  
        sb.append(content + "\n");  
        sb.append("Comments: \n");  
        for (Comment c : comments){  
            sb.append(c.getText() + "\n");  
        }  
        return sb.toString();  
    }  
}

```
#### Análise:

1. **Pacote e Imports:**
    
    - `package entities;` — Mantém a classe dentro do mesmo pacote.
    - As importações de `LocalDateTime`, `DateTimeFormatter`, `ArrayList`, e `List` são necessárias para trabalhar com data/hora e listas.
2. **Atributos:**
    
    - `private LocalDateTime moment;` — Armazena a data e hora da postagem.
    - `private String title;` — O título da postagem.
    - `private String content;` — O conteúdo da postagem.
    - `private Integer likes;` — O número de curtidas da postagem.
    - `private List<Comment> comments = new ArrayList<>();` — Inicializa uma lista vazia para armazenar comentários.
3. **Construtores:**
    
    - `public Post() {}` — Construtor padrão que permite instanciar um objeto sem inicializar os atributos imediatamente.
    - `public Post(LocalDateTime moment, String title, String content, Integer likes) { ... }` — Construtor que inicializa todos os atributos da postagem, permitindo que um objeto `Post` seja criado com todos os dados necessários.

**Getters e Setters:** Métodos que permitem acessar e modificar os atributos da classe de maneira controlada. Isso garante que os dados internos da classe possam ser manipulados de forma segura.

- **Métodos para Manipulação de Comentários:**
    - `public void addComment(Comment comment) { comments.add(comment); }` — Adiciona um novo comentário à lista de comentários da postagem.
    - `public void removeComment(Comment comment) { comments.remove(comment); }` — Remove um comentário da lista, se presente.

- **Formatador de Data:** `private static DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");` — Define como a data e hora serão formatadas quando impressas.
    
- **Método `toString`:**
    
    - Utiliza um `StringBuilder` para montar uma string com o título, número de likes, data formatada e conteúdo, além de listar todos os comentários.
    - O uso de `StringBuilder` é uma boa prática para otimizar a concatenação de strings, principalmente quando há várias adições.


### Classe `Program`
```java
package application;  
import entities.Comment;  
import entities.Post;  
import java.time.LocalDateTime;  
import java.time.format.DateTimeFormatter;  
  
public class Program {  
    public static void main(String[] args) {  
        DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");  
  
        // first post  
        LocalDateTime moment1 = LocalDateTime.parse("21/06/2018 13:06:44", fmt1);  
        Comment c1 = new Comment("Have a nice trip!");  
        Comment c2 = new Comment("Wow, that's awesome!");  
  
        Post p1 = new Post(  
            moment1,  
            "Traveling to New Zealand",  
            "I'm going to visit this wonderful country!",  
            12  
        );  
  
        // add comments to first post  
        p1.addComment(c1);  
        p1.addComment(c2);  
  
        // Second post  
        LocalDateTime moment2 = LocalDateTime.parse("28/07/2018 23:14:19", fmt1);  
        Comment c3 = new Comment("Good night");  
        Comment c4 = new Comment("May the force be with you");  
  
        Post p2 = new Post(  
            moment2,  
            "Good night guys!",  
            "See you tomorrow",  
            5  
        );  
  
        // add comments to second post  
        p2.addComment(c3);  
        p2.addComment(c4);  
  
        System.out.println(p1);  
        System.out.println(p2);  
    }  
}
```
#### Análise:

1. **Pacote e Imports:**
    
    - Mantém a classe `Program` dentro do pacote `application`.
    - Importa as classes necessárias para o funcionamento do programa.
2. **Método `main`:**
    
    - `DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");` — Cria um formatador para a data e hora, igual ao utilizado na classe `Post`.
3. **Primeiro Post:**
    
    - `LocalDateTime moment1 = LocalDateTime.parse("21/06/2018 13:06:44", fmt1);` — Converte uma string em um objeto `LocalDateTime` usando o formatador.
    - Cria dois comentários (`c1` e `c2`).
    - Cria a postagem `p1` com a data, título, conteúdo e número de likes.

4.  - **Segundo Post:** Segue o mesmo padrão do primeiro post, criando uma nova data, dois novos comentários e a postagem correspondente (`p2`).
- **Adição de Comentários:** Adiciona os comentários à postagem `p2`.
- **Impressão no Console:** `System.out.println(p1);` e `System.out.println(p2);` — Utiliza o método `toString` da classe `Post` para exibir os detalhes das postagens no console.

