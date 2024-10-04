# Aula130 - Herança

#### *Herança*
- É um tipo de associação que permite que uma classe herde *todos* dados e comportamentos de outra. 
- *Definições importantes:*
	- 
- *Vantagens:*
	- Reuso
	- Polimorfismo
- *Sintaxe:*
	- `class A extends B;`



![[herança.jpg]]

A herança permite o reuso de atributos e métodos (dados e comportamentos)  ![[herança2.jpg]]
Ao invés de você reescrever toda uma classe com os mesmo atributos de uma outra classe, podemos utilizar herança para isso, a subclasse vai herdar todos os atributos e métodos da classe principal, facilitando todo trabalho, ai podemos adicionar novos métodos e atributos a subclasse
### *Exemplo do uso de herança:*
##### class Account
```java
public class Account {  
    private Integer number;  
    private String holder;  
    private double balance;  
  
    public Account() {  
    }  
    public Account(Integer number, String holder, double balance) {  
        this.number = number;  
        this.holder = holder;  
        this.balance = balance;  
    }  
  
    public Integer getNumber() {  
        return number;  
    }  
  
    public void setNumber(Integer number) {  
        this.number = number;  
    }  
  
    public String getHolder() {  
        return holder;  
    }  
  
    public void setHolder(String holder) {  
        this.holder = holder;  
    }  
  
    public double getBalance() {  
        return balance;  
    }  
  
    public void withDraw(double amount){  
        balance -= amount;  
    }  
  
    public void deposit(double amount){  
        balance += amount;  
    }  
}
```

##### class BusinessAccount
```java
public class BusinessAccount extends Account{  
	private Double loanLimit;  
  
	public BusinessAccount(){  
	}  
	  
	public BusinessAccount(Integer number, 
						   String holder, 
						   double balance, 
						   Double loanLimit) {  
	    super(number, holder, balance);  
	    this.loanLimit = loanLimit;  
	}
	public void loan (double amount) {  
	    if (amount <= loanLimit) {  
	        deposit(amount);  
    }  
}
}
```
Quando criamos um construtor com argumentos para uma SubClasse, nós reaproveitamos o construtor da SuperClasse.
Podemos também, no construtor sem argumentos chamar o `super()`, caso seja incluída alguma lógica para o construtor padrão na class Account, podemos fazer isso para "resguardar".
##### class Program
```java
public class Program {  
    public static void main(String[] args) {  
	    BusinessAccount account = new BusinessAccount();  
		account.getBalance();
            }  
}
```
 Assim, podemos acessar todos os métodos da classe #Account pela classe #BusinessAccount


### Modificador de acesso #protected 

Quando o membro da classe tem seu acesso como #protected ele pode ser acessado na *própria classe*, em uma *outra classe do mesmo pacote* e em uma *subClasse, independente do pacote*

### Exemplo:
Mantendo o exemplo acima.
![[protected.jpg]]
Como um acesso #private só pode ser acessado dentro da própria classe, utilizamos o acesso #protected para nossa subClasse acessar
```java
protected Double balance; // class Account

public void loan (double amount) {  // class BusinessAccount
    if (amount <= loanLimit) {  
        balance += amount - 10.0;  
    }  
}
```

### Definições importantes
![[herança3.jpg]]
- *Relação "é-um"*
	- Se eu estou utilizando a herança na subClasse BusinessAccount, isso significa que ela na verdade, é uma Account (com umas coisas amais)
- *Generalização/especialização*
	- Todo tipo de Account, seja ela uma Account ou uma BusinessAccount, ela é uma Account, então uma classe Account é chamada de *generalização*, e a BusinessAccount é uma *especialização*
- *Superclasse (classe base) / subclasse (classe derivada)*
	- No exemplo acima, a superClasse é a classe Account, enquanto a subclasse é a classe BusinessAccount
- *Herança/extensão*
	- No conceito de herança, a subclasse é uma extensão da superclasse
- *Herança é uma associação entre classes (e não entre objetos)*
	- Quando temos composição entre duas classes, na hora de instanciar temos que instanciar dois objetos, já na herança não, quando eu instanciar uma subclasse, vamos ter um objeto só, e esse objeto vai ter todos os membros das duas classes (superclasse e subclasse)