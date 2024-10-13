## Aula137 - Classes #abstratas 

- São classes que não podem ser instanciadas
- É uma forma de garantir herança total: somente subclasses não abstratas podem ser instanciadas, mas nunca a superclasse abstratas.

![[classes abstratas.jpg]]
```java
public class Program {  
    public static void main(String[] args) {  
		// Não pode ser instanciada, vai dar erro, pois 
	    // Account é uma classe abstract
        Account acc1 = new Account(1001, "Alex", 1000.0); 


        Account acc2 = new SavingsAccount(1002, "Maria", 
									     1000.0, 0.01);  
        Account acc3 = new BusinessAccount(1003, "Bob", 
									      1000.0, 500.0);  
  }

public abstract class Account {  
    private Integer number;  
    private String holder;  
    protected Double balance;

```
### Questionamento
- Se a classe `Account` não pode ser instanciada, por que simplesmente não criar somente SavingsAccount e BusinessAccount?
- *Resposta:*
	- *REUSO*
	- *Polimorfismo*
		- A superclasse genérica nos permite tratar de forma fácil e uniforme todos os tipos de conta, inclusive com polimorfismo se for o caso (como fizemos nos últimos exercícios). Por exemplo, você pode colocar todos os tipos de contas em uma mesma coleção
- Demo: suponha que você queira:
	- Totalizar o saldo de todas as contas.
	- Depositar 10.00 em todas as contas.

```java
List<Account> list = new ArrayList<>();  
list.add(new SavingsAccount(1001, "Alex", 500.00, 0.01));  
list.add(new BusinessAccount(1002, "Maria", 1000.0, 400.0));  
list.add(new SavingsAccount(1004 ,"Bob", 300.0, 0.01));  
list.add(new BusinessAccount(1005, "Anna", 500.0, 500.0));  

// faz a soma do saldo de todas as contas
double sum = 0;  
for (Account acc : list){  
    sum += acc.getBalance();  
}  
System.out.printf("Total balance: U$%.2f\n", sum);  

// adiciona 10.0 a todas as contas
for (Account acc : list){  
    acc.deposit(10.0);  
}  

for (Account acc:list){  
    System.out.printf("Updated balance for account %d: U$%.2f\n", acc.getNumber(), acc.getBalance());  
}
```

## Aula138 - Métodos abstratos

- São métodos que não possuem implementação
- Métodos precisam ser abstratos quando a classe é genérica demais para conter sua implementação
- Se uma classe possuir pelo menos um método abstrato, então esta classe também é abstrata
- Notação UML: Itálico
- Sintaxe básica:
	- `public abstract tipo nameMéthod();`
- Exercício resolvido
![[MétodAbstract.jpg]]

![[exAbstract.jpg]]

## Aula139 -Exercício de fixação
![[fixaçãoAbstract.jpg]]

![[fixaçãoAbstract2.jpg]]