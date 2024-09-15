#### #Construtores
- É uma operação especial da classe, que executa no momento da instanciação do objeto
- Usos comuns: 
	- Iniciar valores dos atributos
	- Permitir ou obrigar que o objeto receba dados/ dependências  no momento de sua instanciação (injeção de dependência)
- Se um construtor customizado não for especificado, a classe disponibiliza o construtor padrão:
	- `Product p = new Product()`
- É possível especificar mais de um construtor na mesma classe ( #sobrecarga)

Quando executamos o comando `Product p = new Product()`, instanciamos um produto `product` com seus atributos "vazios".
Entretanto, faz sentido um produto que não tem nome? Faz sentido um produto que não tem preço?
Com o intuito de evitar a existência de produtos que não sem nome e sem preço, é possível fazer com que seja "obrigatória" a iniciação desses valores? 
É possível sim, pra isso podemos criar um construtor.
![[Capturar2.jpg]]

Os construtores, geralmente são colocados depois dos atributos da classe e antes dos métodos.
```java
public class Product {
    public String name;
    public double price;  // atributos da classe
    public int quantity;

    public Product(String name, double price, int quantity){
        this.name = name;   // sintaxe de construtor, palavra this indica os atributos 
	    this.price = price; // do objeto                
	    this.quantity = quantity                

    }
```
Sempre instanciamos o construtor, após pedirmos os dados ao usuário, por exemplo: 
```java
System.out.println("Enter product data: ");

        System.out.print("Name: ");
        String name = sc.nextLine();

        System.out.print("Price: U$");
        double price = sc.nextDouble();

        System.out.print("Quantity in stock: ");
        int quantity = sc.nextInt();

        Product product = new Product(name, price, quantity);
```

O construtor serve para "proteger" que o desenvolvedor crie um produto que não tenha nome, preço e quantidade.

---
---
#### #This
- É uma referência para o próprio objeto/atributos do objeto
- Usos comuns:
	- Diferenciar atributos de variáveis locais
	- Passar o próprio objeto como argumento na chamada de um método ou construtor
![[Ths.jpg]]

---
---

#### #Sobrecarga 
- É um recurso que uma classe possui de oferecer mais de uma operação com o mesmo nome, porém, com diferentes listas de parâmetros.

##### Proposta:
- Vamos criar um construtor opcional, o qual recebe apenas o nome e preço do produto. A quantidade em estoque deste novo produto, por padrão, deverá então ser iniciada com o valor zero
- Nota: É possível também incluir um construtor padrão

Sobrecarga é você disponibilizar mais de uma versão da operação, por exemplo: 
```java
System.out.println("Enter product data: ");

        System.out.print("Name: ");
        String name = sc.nextLine();

        System.out.print("Price: U$");
        double price = sc.nextDouble();

        System.out.print("Quantity in stock: ");
        int quantity = sc.nextInt();

        Product product = new Product(name, price, quantity);
```
No exemplo acima, temos um construtor que tem três parâmetros.


```java
    public Product(String name, double price, int quantity){
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    }

    public Product(String name, double price){
        this.name = name;
        this.price = price;
    }
```
Já nesse exemplo, acontece uma sobrecarga, por conta de que agora tem dois construtores em uma mesma classe. E esse novo construtor recebe apenas dois parâmetros, dando a possibilidade de você puder ter dois tipos de operações. 


Também é possível continuar usando o construtor padrão, e para isso criamos uma sobrecarga e o construtor padrão vai ficar disponível, por exemplo: 
```java
   public Product(){ // construtor padrão
    }
    
   public Product(String name, double price, int quantity){
        this.name = name;
        this.price = price; // construtor com três parâmetros
        this.quantity = quantity;
    }

    public Product(String name, double price){
        this.name = name; // construtor com dois parâmetros
        this.price = price;
    }
```
---
---
