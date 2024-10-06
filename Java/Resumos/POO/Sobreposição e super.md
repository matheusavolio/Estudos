### obreposição (ou Sobrescrita de Método)

A **sobreposição**, também chamada de sobrescrita (override), ocorre quando um método que foi definido na **superclasse** é redefinido em uma **subclasse** para alterar ou estender o comportamento padrão.

#### Exemplo:

Imagine que temos uma classe `Account` com o método `withdraw`. Se criarmos uma subclasse `SavingsAccount`, podemos sobrescrever o método `withdraw` para que ele tenha um comportamento específico quando se tratar de uma conta poupança.

```java
public class Account {     
	private Double balance;      
	
	public Account(Double balance) {         
		this.balance = balance;     
	}      
	public void withdraw(Double amount) {         
	balance -= amount;     
	} 
}
```
Agora, vamos sobrescrever esse método na subclasse `SavingsAccount`:

```java
public class SavingsAccount extends Account {     
	private Double interestRate;      
	
	public SavingsAccount(Double balance, 
	Double interestRate) {         
	super(balance);         
	this.interestRate = interestRate;     
	}      
	@Override     
	public void withdraw(Double amount) {         
		// Regra específica para saque em conta poupança
	    balance -= amount + 2.0;     
	} 
}
```
Neste exemplo, `SavingsAccount` está sobrescrevendo o método `withdraw` da classe `Account` para adicionar uma taxa extra ao saque (R$ 2.0). A sobrescrita permite personalizar o comportamento do método herdado.

### Uso da Anotação `@Override`

É **altamente recomendável** utilizar a anotação `@Override` ao sobrescrever métodos. Ela traz as seguintes vantagens:

1. **Claridade:** O código fica mais fácil de entender, pois outros desenvolvedores sabem que o método está sendo sobrescrito de uma superclasse.
2. **Verificação pelo Compilador:** O compilador vai verificar se o método realmente está sobrescrevendo um método da superclasse. Se houver algum erro (por exemplo, digitar o nome do método errado), o compilador vai alertar.

#### Exemplo com `@Override`:

```java
@Override 
public void withdraw(Double amount) {     
	balance -= amount + 2.0;  
	// Sobrescrevendo o método withdraw 
}
```
### A Palavra-Chave `super`

A palavra-chave `super` é usada para se referir à **superclasse** diretamente. Ela é útil quando você quer:

1. **Chamar o método da superclasse dentro de um método sobrescrito.**
2. **Invocar o construtor da superclasse** para reaproveitar a lógica de inicialização.

#### Exemplo de Uso de `super` em Métodos:

Imagine agora que temos uma outra subclasse `BusinessAccount`, que tem a mesma lógica de saque da `Account`, mas com uma taxa extra.

```java
public class BusinessAccount extends Account { 

	public BusinessAccount(Double balance) {         
	super(balance);  
	// Chamando o construtor da superclasse Account     
	}      
	@Override     
	public void withdraw(Double amount) {         
	super.withdraw(amount);  
	// Chamando o método withdraw da superclasse         
	balance -= 2.0;  
	// Regra adicional de saque: cobra uma taxa extra     
	} 
}
```
Nesse exemplo, ao sobrescrever o método `withdraw` na `BusinessAccount`, chamamos o método `withdraw` da `Account` usando `super.withdraw(amount)`, que faz o saque normal. Depois, aplicamos uma regra extra específica de `BusinessAccount`, retirando mais R$ 2.0.

#### Uso de `super` no Construtor:

Quando uma subclasse é criada, é possível reaproveitar a lógica do **construtor da superclasse**. Isso economiza código e garante que os atributos herdados sejam inicializados corretamente.

```java
public class BusinessAccount extends Account {     
	private Double loanLimit;      
	
	 public BusinessAccount(Double balance, DoubleloanLimit) {         
	super(balance);  
// Chama o construtor de Account para inicializar balance    
	this.loanLimit = loanLimit;  // Inicializa loanLimit     
	} 
}
```
Aqui, o construtor de `BusinessAccount` chama o construtor de `Account` com `super(balance)`. Isso garante que o saldo (`balance`) seja inicializado corretamente, sem precisar duplicar o código.

### Resumo:

- **Sobreposição** permite que uma subclasse substitua um método da superclasse para definir um comportamento mais específico.
- A anotação `@Override` é uma **boa prática**, pois melhora a legibilidade e ajuda o compilador a detectar possíveis erros.
- A palavra-chave `super` permite acessar métodos e construtores da superclasse, possibilitando reutilização de código e extensão das funcionalidades herdadas.