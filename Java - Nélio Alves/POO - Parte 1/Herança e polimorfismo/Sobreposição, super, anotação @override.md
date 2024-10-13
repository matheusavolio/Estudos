## Aula132 - Sobreposição, palavra Super, anotação @Override

### #Sobreposição ou sobreescrita
- *É a implementação de um método de uma superclasse na subclasse*
	- Ex: Eu tenho a superclasse `Account`, essa superclasse ela tem o método withDraw(saque), e podemos implementar esse método na subclasse `SavingsAccount`, isso pode ser útil, para definir um comportamento específico de saque quando a conta for uma poupança.
	- É quando você implementa um método da superclasse na subclasse.
- *É fortemente recomendável usar a anotação @Override em método sobrescrito.*
	- Facilita a leitura e compreensão do código
	- Avisamos ao compilador (boa prática)

![[Sobreposição.jpg]]
### Continuando com o exemplo imposto na Aula130 e 131:
##### class SavingsAccount
```java
// SOBREPOSIÇÃO  
@Override  
public void withDraw(double amount){  
    balance -= amount;  
}
```

##### class Program
```java
Account acc1 = new Account(1003,  
        "Matheus",  
        1000.0);  
acc1.withDraw(200);  
System.out.println(acc1.getBalance());  // Output: 795.0


Account acc2 = new SavingsAccount(1002,  
            "Maria",  
            1000.0,  
            0.20);  
  
acc2.withDraw(200.0);  
System.out.println(acc2.getBalance()); // Output: 800.0
```

### Palavra #Super 
- É possível chamar a implementação da superclasse usando a palavra super.
	- Ex: Suponha que, na subclasse BusinessAccount, a regra para saque seja realizar o saque normalmente da superclasse e descontar mais 2.0
- O super nos #constructor ele aproveita a lógica dos contrutores da superclasse.
Podemos reutilizar o código da superclasse na subclasse utilizando a palavra #super e adicionar mais coisas se necessário 
##### class BusinessAccount
```java
@Override
public void withDraw(double amount){
	super.withDraw(amount)
	balance -= 2.0;
}
```

##### class Program
```java
    Account acc3 = new BusinessAccount(1003,  
            "Vanessa",  
            1000.0,  
            500.0);  
    acc3.withDraw(200.0);  
    System.out.println(acc3.getBalance());  
}
```

