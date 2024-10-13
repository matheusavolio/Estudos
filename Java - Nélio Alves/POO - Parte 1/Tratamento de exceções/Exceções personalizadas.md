## Aula 150 - Solução boa
![[model package.jpg]]

![[ExExeção.jpg]]

![[exceçãoEx.jpg]]
![[exceçãoEx2.jpg]]

### Resumo da aula
- *Solução 1(Muito ruim):*
	- Lógica de validação no programa principal, lógica não delegada
- *Solução 2:(ruim)*
	- Método retornando string
	- A semântica da operação é prejudicada
		- Retornar string não tem nada a ver com a atualização de reserva
		- E se a operação tivesse que retornar um string?
	- Ainda não é possível tratar exceções em construtores
	- Ainda não á auxílio do compilador: o programador deve "lembrar" de verificar se houve erro
	- A lógica fica estruturada em condicionais aninhadas
- *Solução 3(Boa):*
	- Tratamento de exceções
- Cláusula #throws: Propaga a exceção ao invés de trata-la
- Cláusula #throw: laça a exceção/"corta" o método
- #Exception:  compilador obriga a tratar ou propagar
- #RuntimeException: Compilador não obriga
- O modelo de tratamento de exceções permite que erros sejam tratados de forma consistente, flexível, usando boas práticas
- Vantagens:
	- Lógica delegada
	- Construtores podem ter tratamento de exceções
	- Possibilidade de auxílio do compilador ( #Exception )
	- Código mais simples. Não há aninhamento de condicionais: a qualquer momento que uma exceção for disparada, a execução é interrompida e cai no bloco #catch correspondente
	- É possível capturar inclusive outras exceções do sistema 


### Solução 3 (boa)

#### Classe Program
```java
package application;  
import model.entities.Reservation;  
import model.exceptions.DomainException;  
import java.time.LocalDate;  
import java.time.format.DateTimeFormatter;  
import java.util.Scanner;  
  
// Solução 3 (boa)  
public class Program {  
    public static void main(String[] args)  {
		Scanner sc = new Scanner(System.in);  
		DateTimeFormatter fmt =
		DateTimeFormatter.ofPattern("dd/MM/yyyy");  
		  
try {  
    System.out.print("Room number: ");  
    int number = sc.nextInt();  
    System.out.print("Check-in date: (dd/mm/yyyy): ");  
    LocalDate checkIn = LocalDate.parse(sc.next(), fmt);  
    System.out.print("Checkk-out date (dd/mm/yyyy): ");  
    LocalDate checkOut = LocalDate.parse(sc.next(), fmt);  
  
    Reservation reservation = new Reservation(number, checkIn, checkOut);  
    System.out.println("Reservation: " + reservation);  
  
    System.out.println();  
    System.out.println("Enter data to " +
			    "updated the reservation: ");  
    System.out.print("Check-in date: (dd/mm/yyyy): ");  
    checkIn = LocalDate.parse(sc.next(), fmt);  
    System.out.print("Check-out date (dd/mm/yyyy): ");  
    checkOut = LocalDate.parse(sc.next(), fmt);  
  
    reservation.updateDates(checkIn, checkOut);  
    System.out.println("Reservation: " + reservation);  
}  
catch (DomainException e){  
    System.out.println("Error in reservation: " + e.getMessage());  
}  
finally {  
    sc.close();  
	}
}
}
```

```java

public class Program {     
	public static void main(String[] args)  {
```
Aqui, temos a classe principal `Program` e o método `main`, ponto de entrada do programa. Ele é o responsável por iniciar a execução, coletar dados e tratar possíveis exceções.

```java
Scanner sc = new Scanner(System.in); 
DateTimeFormatter fmt =DateTimeFormatter.ofPattern("dd/MM/yyyy");`
```
O `Scanner` é usado para capturar a entrada do usuário, e o `DateTimeFormatter` é utilizado para formatar e interpretar as datas no formato "dd/MM/yyyy", que é o padrão esperado para entrada e saída das datas.

```java
System.out.print("Room number: "); 
int number = sc.nextInt();
```
Essas linhas capturam o número do quarto que o usuário insere e armazenam na variável `number`.

```java
System.out.print("Check-in date: (dd/mm/yyyy): "); LocalDate checkIn = LocalDate.parse(sc.next(), fmt); System.out.print("Check-out date (dd/mm/yyyy): "); LocalDate checkOut = LocalDate.parse(sc.next(), fmt);
```
Aqui, as datas de check-in e check-out são capturadas como strings e transformadas em objetos `LocalDate` usando o método `parse` e o formato definido anteriormente (`fmt`). Se a entrada do usuário estiver fora do padrão esperado, pode lançar uma exceção de formatação.

```java
Reservation reservation = new Reservation(number, 
										  checkIn, 
										  checkOut); System.out.println("Reservation: " + reservation);
```
Essa parte cria uma nova instância da classe `Reservation` e exibe os detalhes da reserva ao invocar o método `toString()` da classe `Reservation`.

```java
System.out.println("Enter data to update the reservation: "); 
System.out.print("Check-in date: (dd/mm/yyyy): "); 
checkIn = LocalDate.parse(sc.next(), fmt); System.out.print("Check-out date (dd/mm/yyyy): "); checkOut = LocalDate.parse(sc.next(), fmt);  reservation.updateDates(checkIn, checkOut);
```
O usuário tem a chance de atualizar as datas da reserva. Novas datas são capturadas e o método `updateDates` é chamado para atualizar as informações da reserva. Caso as novas datas sejam inválidas, a exceção `DomainException` será lançada.

```java
catch (DomainException e) {     
	System.out.println("Error in reservation: " + 
							e.getMessage()); 
}
```
Aqui, o programa captura e trata a exceção personalizada `DomainException`, que ocorre quando a regra de negócio sobre datas é violada (como tentar colocar uma data de check-out anterior à de check-in).
```java
finally {     
	sc.close(); }
```
O `finally` é usado para garantir que o objeto `Scanner` seja fechado, liberando recursos independentemente de ocorrerem erros ou não.


#### Classe Reservation
```java
public class Reservation {  
    private Integer roomNumber;  
    private LocalDate checkIn;  
    private LocalDate checkOut;  
  
    public Reservation() {  
    }  
    public Reservation(Integer roomNumber, LocalDate checkIn, LocalDate checkOut) throws DomainException{  
        if (!checkOut.isAfter(checkIn)) {  
            throw new DomainException("Check-out date must be after check-in date.");  
        }  
        this.roomNumber = roomNumber;  
        this.checkIn = checkIn;  
        this.checkOut = checkOut;  
    }  
  
    public Integer getRoomNumber() {  
        return roomNumber;  
    }  
  
    public void setRoomNumber(Integer roomNumber) {  
        this.roomNumber = roomNumber;  
    }  
  
    public LocalDate getCheckIn() {  
        return checkIn;  
    }  
  
    public LocalDate getCheckOut() {  
        return checkOut;  
    }  
  
    public long duration(){  
        Duration diff = Duration.between(checkIn.atStartOfDay(), checkOut.atStartOfDay());  
        return diff.toDays();  
    }  
  
    public void updateDates(LocalDate checkIn, LocalDate checkOut) throws DomainException{  
        LocalDate now = LocalDate.now();  
        if (checkIn.isBefore(now) || checkOut.isBefore(now)) {  
            throw new DomainException("Reservation dates for update must be future dates.");  
        }  
        if (!checkOut.isAfter(checkIn)) {  
            throw new DomainException("Error in reservation: " +  
                    "Check-out date must be after check-in date.");  
        }  
        this.checkIn = checkIn;  
        this.checkOut = checkOut;  
    }  
  
    private static DateTimeFormatter fmt = DateTimeFormatter.ofPattern("dd/MM/yyyy");  
  
    public String toString(){  
        return "Room "  
                + roomNumber  
                + ", check-in: "  
                + fmt.format(checkIn)  
                + ", check-out: "  
                + fmt.format(checkOut)  
                + ", "  
                + duration()  
                + " nights.";  
    }  
}
```


```java
private Integer roomNumber; 
private LocalDate checkIn; 
private LocalDate checkOut;
```
Esses são os atributos que armazenam o número do quarto e as datas de check-in e check-out, essenciais para a reserva.

```java
public Reservation(Integer roomNumber, 
				   LocalDate checkIn, 
				   LocalDate checkOut) 
				   throws DomainException {     
	if (!checkOut.isAfter(checkIn)) {       
		throw new DomainException("Check-out date must be 
		"after check-in date.");     
	}     
	this.roomNumber = roomNumber;     
	this.checkIn = checkIn;     
	this.checkOut = checkOut; 
}
```
O construtor inicializa os valores da reserva, mas antes verifica se a data de check-out é posterior à de check-in. Caso contrário, uma exceção `DomainException` é lançada. Essa validação é importante para garantir a integridade dos dados da reserva.

```java
public long duration() {     
	Duration diff = 
	Duration.between(
	checkIn.atStartOfDay(), 
	checkOut.atStartOfDay());     
	return diff.toDays(); }
```
Esse método calcula a diferença de dias entre o check-in e o check-out usando a classe `Duration`, convertendo a diferença para dias completos. Isso é útil para saber quantas noites o cliente ficará hospedado.

```java
public void updateDates(LocalDate checkIn, 
						LocalDate checkOut) 
						throws DomainException {     
	LocalDate now = LocalDate.now();     
	if (checkIn.isBefore(now) || checkOut.isBefore(now)) {         throw new DomainException("Reservation dates for 
						"update must be future dates.");     }   
		if (!checkOut.isAfter(checkIn)) {         
		throw new DomainException("Check-out date must be 
								"after check-indate.");   
	}   
	this.checkIn = checkIn;     
	this.checkOut = checkOut; 
}
```
O método `updateDates` permite atualizar as datas de uma reserva existente. Primeiro, verifica se as datas inseridas estão no futuro em relação à data atual, e se a data de check-out é válida (deve ser após o check-in). Se qualquer regra for violada, uma `DomainException` é lançada.

```java
private static DateTimeFormatter fmt
DateTimeFormatter.ofPattern("dd/MM/yyyy");  
public String toString() {     
	return "Room " 
	+ roomNumber 
	+ ", check-in: " 
	+ fmt.format(checkIn) 
	+ ", check-out: " 
	+ fmt.format(checkOut) 
	+ ", " + duration() 
	+ " nights."; }`
```
O método `toString()` sobrescreve a versão padrão para fornecer uma representação mais amigável do objeto `Reservation`. O formato de data e a duração (número de noites) são exibidos no resultado.


#### Classe DomainException
```java
package model.exceptions;  
  
public class DomainException extends Exception{  
  
    public DomainException (String msg){  
        super(msg);  
    }  
}
```

```java
`public class DomainException extends Exception {     
	public DomainException(String msg) {         
		super(msg);     
		} 
	}
```
A `DomainException` é uma exceção personalizada que herda de `Exception`. Ela é usada para capturar erros de lógica de negócio, como datas inválidas nas reservas. Isso facilita o tratamento de erros específicos em comparação a exceções genéricas.