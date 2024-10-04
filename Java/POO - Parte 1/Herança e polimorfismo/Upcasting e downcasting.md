
### Aula131 -  #Upcasting e #downcasting

- Upcasting:
	- *Casting da subclasse para super classe*
		- é como se tivéssemos um objeto do tipo BusinessAccount e eu quisesse atribuir esse objeto ao uma variável do tipo Account
	- *Uso comum: polimorfismo*
- *Downcasting*
	- *Casting da superclasse para subclasse*
		- É como se tivesse um objeto do tipo Account, e eu quisesse atribuir esse objeto a uma variável do tipo BusinessAccount
	- *Palavra `instanceOf`*
	- *Uso comum: métodos que recebem parâmetros genéricos (Ex: Equals)*


![[upcasting e downcasting.jpg]]
### *Utilizando o mesmo exemplo da Aula130:*

##### class SavingAccount
```java
package entities;  
  
public class SavingsAccount extends Account{  
    private Double interestRest;  
  
    public SavingsAccount(){  
        super();  
    }  
  
    public SavingsAccount(Integer number, String holder, double balance, Double interestRest) {  
        super(number, holder, balance);  
        this.interestRest = interestRest;  
    }  
  
    public Double getInterestRest() {  
        return interestRest;  
    }  
  
    public void setInterestRest(Double interestRest) {  
        this.interestRest = interestRest;  
    }  
  
    public void updateBalance(){  
        balance += balance * interestRest;  
    }  
}
```

##### class Program
```java
package application;  
import entities.Account;  
import entities.BusinessAccount;  
import entities.SavingsAccount;  
  
public class Program {  
    public static void main(String[] args) {  
        Account ac = new Account(1001, "Matheus", 0.0);  
  
        BusinessAccount bAcc = new BusinessAccount(1002,  
                "Lucas",  
                0.0,  
                500.0);  
  
        // UPCASTING  
        // É normal pegarmos um objeto da subclasse e 
        // atribuirmos a um da        
        // superlasse        
        Account acc1 = bAcc;  
        acc1.getHolder();  
        Account acc2 = new BusinessAccount(1003,  
                "Bob",  
                0.0,  
                200.0);  
        Account acc3 = new SavingsAccount(1004,  
                "Anna",  
                0.0,  
                0.01);  
  
        // DOWNCASTING  
        // Para atribuirmos uma uma superclasse a uma 
        // variável da subclasse, precisamos fazer o 
        // casting.        
        BusinessAccount bAcc1 = (BusinessAccount) acc2 ;  
        bAcc1.loan(100.0);  
  
        // A SavingAccount é uma Account, porém não é uma 
        // BusinessAccount  por isso o compilador não irá 
        // apontar erro, porém, quando executar        
        // o programa, esse erro será mostrado        
// -> BusinessAccount bAcc2 = (BusinessAccount) acc3; <-        // Para evitar esse tipo de erro, precisamos fazer o 
	// teste para ver se o objeto do acc3 é do tipo 
	// BusinessAccount, se ele for, ai sim podemos fazer o 
	// downcasting. E para fazer esse teste, utilizamos a 
	// palavrinha intanceOf:        
	if(acc3 instanceof BusinessAccount){  
            BusinessAccount bAcc2 = (BusinessAccount) acc3;  
            bAcc2.loan(200.0);  
            System.out.println("Loan!");  
        }  
        if (acc3 instanceof SavingsAccount){  
            SavingsAccount sAcc = (SavingsAccount) acc3;  
            sAcc.updateBalance();  
            System.out.println("Update!");  
        }  
    }  
}
```


