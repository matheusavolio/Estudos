A **composição** é um tipo de associação entre classes onde um objeto é composto por outros objetos, formando uma relação "todo-parte". Na programação orientada a objetos, essa composição é fundamental para criar sistemas coesos, flexíveis e fáceis de manter, e a UML (Unified Modeling Language) nos fornece uma forma de representá-la graficamente.

### Relação "tem-um" ou "tem-vários"

Na composição, dizemos que uma classe "tem-um" ou "tem-vários" outros objetos. Por exemplo, um pedido de compra (**Order**) pode ter múltiplos itens (**OrderItem**). O pedido só faz sentido se tiver itens, e um item sempre faz parte de um pedido.

### Exemplos com base nas imagens enviadas

1. **Imagem de Entidades**:
    
    - **Order** (Pedido) tem uma relação de composição com **OrderItem** (Itens do Pedido). A classe **Order** contém uma lista de itens do pedido. Essa é uma relação "tem-vários", pois um pedido pode ter vários itens.
        - Notamos isso pela multiplicidade indicada ao lado do relacionamento entre `Order` e `OrderItem`.
    - Da mesma forma, o **OrderItem** tem uma relação com o **Product** (Produto), onde cada item de pedido está relacionado a um produto específico. Esse relacionamento mostra que cada **OrderItem** "tem-um" **Product**.
    - Além disso, a classe **Order** tem uma relação com a classe **Client** (Cliente), onde cada pedido está associado a um cliente específico. Isso indica uma relação "tem-um" entre **Order** e **Client**.
    - O conceito de composição é visualizado aqui como uma forma de garantir que a classe **Order** não exista sem **OrderItem** e **Client**.
2. **Imagem de Serviços**:
    
    - O **OrderRepository** e o **OrderService** trabalham em conjunto para manipular pedidos. O **OrderService** tem uma relação de "tem-um" com o **EmailService**, pois ele utiliza este serviço para enviar e-mails relacionados aos pedidos. Essa relação facilita a divisão de responsabilidades, onde o envio de e-mails é delegado ao **EmailService**, enquanto o processamento do pedido é responsabilidade do **OrderService**.
    - O **AuthService** (Serviço de Autenticação) também demonstra essa relação, utilizando o **EmailService** para enviar novas senhas, quando necessário. Isso exemplifica como a composição permite a criação de sistemas modulares e flexíveis.

### Vantagens da Composição

1. **Organização e Divisão de Responsabilidade**:
    
    - Ao usar composição, as responsabilidades são divididas entre as classes. Por exemplo, em vez de o **Order** gerenciar produtos diretamente, essa responsabilidade é delegada ao **OrderItem**.
2. **Coesão**:
    
    - A coesão é promovida, pois cada classe tem uma única responsabilidade bem definida. O **EmailService**, por exemplo, só cuida do envio de e-mails, enquanto o **OrderService** lida com a lógica de negócios dos pedidos.
3. **Flexibilidade**:
    
    - A composição permite flexibilidade no design, onde podemos modificar partes de um sistema sem afetar a estrutura global. Podemos alterar a implementação do **EmailService** sem alterar o funcionamento do **OrderService**.
4. **Reuso**:
    
    - A composição facilita o reuso de componentes. O **EmailService**, por exemplo, pode ser utilizado tanto pelo **OrderService** quanto pelo **AuthService**.

### Nota sobre Composição na UML

Na notação UML, a composição tradicionalmente é representada por um diamante preto próximo à classe "todo" (a que contém as partes). No entanto, neste contexto, estamos utilizando o termo "composição" de maneira mais genérica, aplicando-o a qualquer relação "tem-um" ou "tem-vários", como as observadas entre **Order** e **OrderItem** ou **Order** e **Client**.

Esses exemplos ilustram como a composição é uma ferramenta poderosa no design de sistemas orientados a objetos, promovendo coesão, modularidade e reuso.


![[entities.jpg]]![[services.jpg]]
### Diagrama de Entidades

1. **Order (Pedido)**
    
    - **Atributos:**
        - `moment: Date`: A data e hora em que o pedido foi realizado.
        - `status: OrderStatus`: Um enum que indica o status atual do pedido (como pagamento pendente, em processamento, enviado, etc.).
    - **Métodos:**
        - `addItem(item: OrderItem): void`: Método para adicionar um item ao pedido.
        - `removeItem(item: OrderItem): void`: Método para remover um item do pedido.
        - `total(): Double`: Calcula o valor total do pedido, somando o valor de todos os itens.
    - **Composições:**
        - O pedido tem uma composição do tipo "tem-vários" com `OrderItem` (Itens do pedido), representada pela lista de itens. Essa relação precisa ser implementada utilizando um `List<OrderItem>` na classe `Order`. O pedido também tem uma composição do tipo "tem-um" com o cliente (`Client`), já que cada pedido é associado a um cliente.
2. **Client (Cliente)**
    
    - **Atributos:**
        - `name: String`: Nome do cliente.
        - `email: String`: Endereço de e-mail do cliente.
        - `birthDate: Date`: Data de nascimento do cliente.
    - Cada cliente pode ter vários pedidos (mas no diagrama, focamos na associação inversa, onde o pedido tem um cliente).
3. **OrderItem (Item do Pedido)**
    
    - **Atributos:**
        - `quantity: Integer`: Quantidade do produto no pedido.
        - `price: Double`: Preço unitário do produto.
    - **Método:**
        - `subTotal(): Double`: Calcula o subtotal (quantidade * preço) de um item específico.
    - **Composições:**
        - Um `OrderItem` está associado a um produto, o que cria uma relação do tipo "tem-um" com a entidade `Product` (Produto).
4. **Product (Produto)**
    
    - **Atributos:**
        - `name: String`: Nome do produto.
        - `price: Double`: Preço do produto.
5. **OrderStatus (Enum)**
    
    - Este enum define diferentes estados para o pedido:
        - `PENDING_PAYMENT`: Pagamento pendente.
        - `PROCESSING`: Pedido em processamento.
        - `SHIPPED`: Pedido enviado.
        - `DELIVERED`: Pedido entregue.

### Relação de Composição "tem-um" e "tem-vários" nas Entidades

- A classe `Order` contém vários itens (`OrderItem`), o que é uma composição do tipo "tem-vários".
- A relação do pedido com o cliente (`Client`) é do tipo "tem-um", onde um pedido pertence a apenas um cliente.
- Um `OrderItem` contém um `Product`, o que também representa uma composição do tipo "tem-um".

### Diagrama de Serviços

1. **CrudRepository Interface**
    
    - Esta interface genérica define operações CRUD básicas que podem ser aplicadas a qualquer entidade:
        - `save(obj: T): T`: Salva um objeto do tipo `T`.
        - `delete(obj: T): void`: Deleta um objeto do tipo `T`.
        - `findById(id: ID): T`: Busca um objeto pelo seu identificador.
        - `findAll(): List<T>`: Retorna uma lista de todos os objetos do tipo `T`.
2. **OrderRepository**
    
    - Extende a interface `CrudRepository` e adiciona um método específico:
        - `findByDate(minDate: Date, maxDate: Date): List<Order>`: Busca pedidos em um intervalo de datas.
3. **OrderService**
    
    - **Métodos:**
        - `save(order: Order): void`: Salva um pedido no repositório.
        - `search(minDate: Date, maxDate: Date): List<Order>`: Busca pedidos no intervalo de datas fornecido.
4. **AuthService**
    
    - Serviço responsável pela autenticação de usuários. Métodos principais incluem:
        - `getToken(username: String, password: String): String`: Gera um token de autenticação para o usuário.
        - `refreshToken(token: String): String`: Atualiza o token de autenticação.
        - `sendNewPassword(email: String): void`: Envia um novo email com a senha.
5. **EmailService**
    
    - Serviço utilizado para enviar e-mails:
        - `sendEmail(sender: String, recipient: String, subject: String, message: String): void`: Envia um e-mail com os detalhes fornecidos.

### Relação de Composição "tem-um" e "tem-vários" nos Serviços

- O serviço `OrderService` tem uma composição do tipo "tem-um" com o `OrderRepository`, pois ele depende desse repositório para persistir ou recuperar os pedidos.
- Da mesma forma, o `AuthService` tem uma dependência ("tem-um") com o `EmailService` para enviar e-mails de recuperação de senha.

### Exemplo de Declaração em Java

Como mencionado, quando temos uma composição do tipo "tem-vários", a lista de itens (`OrderItem`, por exemplo) precisa ser declarada e instanciada. Isso pode ser feito da seguinte maneira:

java

Copiar código
```java

public class Order {     
	private List<OrderItem> 
	items = new ArrayList<>();      
	public void addItem(OrderItem item) {        
		items.add(item);     }      
	public void removeItem(OrderItem item) {         
		items.remove(item);     }      
	public double total() {        
	 return
	 items.stream().mapToDouble(OrderItem::subTotal).sum();    } 
}
```
Nesse exemplo:

- A composição "tem-vários" é representada pela lista `items` que contém os `OrderItem`.
- O método `addItem` adiciona itens à lista, e `removeItem` os remove.
- O método `total` calcula o total de todos os itens, somando os subtotais.