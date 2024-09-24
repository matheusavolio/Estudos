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
