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