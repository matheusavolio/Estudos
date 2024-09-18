## Aula 76 - #Construtores em Java

### O que é um Construtor?

Um **construtor** é uma operação especial de uma classe que é executada **no momento da criação do objeto** (instanciação). Ele tem o papel de **inicializar os atributos** do objeto e garantir que ele comece com um estado válido.

### Usos Comuns de um Construtor:

- **Inicializar atributos**: O construtor pode atribuir valores iniciais aos atributos do objeto.
- **Injeção de dependências**: Permite ou obriga que o objeto receba certos dados ou dependências durante sua criação, assegurando que ele tenha tudo o que precisa para funcionar corretamente.

### Construtor Padrão vs Construtor Customizado

Se você **não definir** um construtor customizado, o Java fornece um **construtor padrão**, que permite criar o objeto sem inicializar seus atributos. Exemplo de uso do construtor padrão:
```java
Product p = new Product(); // Atributos iniciam "vazios"`
```

No entanto, faz sentido criar um produto sem nome ou preço? Para evitar isso, podemos definir um **construtor customizado** que obriga a inicialização dos atributos essenciais ao criar o objeto.

### Sobrecarga de Construtores

É possível ter mais de um construtor na mesma classe. Isso se chama **sobrecarga**, onde diferentes construtores podem aceitar diferentes conjuntos de parâmetros. Assim, você pode criar objetos de maneiras variadas, conforme as necessidades.

### Exemplo de Construtor Customizado

No exemplo abaixo, criamos um construtor que **exige** que o nome, o preço e a quantidade sejam fornecidos ao instanciar um produto. Isso garante que nenhum produto seja criado com atributos inválidos ou não definidos.


```java

`public class Product {     
	public String name;     
	public double price;       
	public int quantity;      
	// Construtor customizado     
	public Product(String name, double price, int quantity) {         
		this.name = name;   // 'this' refere-se ao atributo da classe
		this.price = price;          
		this.quantity = quantity;                     
		} 
	}
```
### Como Usar o Construtor

Aqui está um exemplo de como coletar dados do usuário e passar esses valores para o construtor ao criar um novo produto:

```java

System.out.println("Enter product data: ");  

System.out.print("Name: "); 
String name = sc.nextLine();  

System.out.print("Price: U$"); 
double price = sc.nextDouble();  

System.out.print("Quantity in stock: "); 
int quantity = sc.nextInt();  

// Instanciação do produto com o construtor customizado 
Product product = new Product(name, price, quantity);`
```
### Conclusão

O **construtor** é uma forma de garantir que objetos sejam criados de forma consistente e válida. Ele "protege" o código, obrigando o desenvolvedor a fornecer os dados essenciais no momento da criação do objeto, evitando que produtos, por exemplo, sejam criados sem nome, preço ou quantidade.


---
---

## #Encapsulamento em Java

### O que é Encapsulamento?

**Encapsulamento** é um princípio fundamental da Programação Orientada a Objetos (POO), que visa **esconder os detalhes internos de implementação de uma classe**, expondo apenas as **operações seguras** que mantêm os objetos em um estado consistente. Isso garante que os atributos de uma classe não sejam acessados ou modificados diretamente de maneira que possa corromper seu estado.

### Regra de Ouro:

O objetivo do encapsulamento é garantir que um objeto **esteja sempre em um estado válido**, e a própria classe deve ser responsável por assegurar isso.

### Analogia para Entender Encapsulamento:

Imagine um **aparelho de som**. Internamente, ele possui diversos circuitos e conexões que o fazem funcionar, mas o usuário não tem acesso direto a esses componentes, pois uma ligação errada poderia danificar o aparelho. Para evitar isso, o fabricante esconde esses detalhes e expõe apenas **funções seguras**, como "ligar", "aumentar o volume" e "trocar de faixa", que permitem ao usuário operar o aparelho sem o risco de prejudicá-lo.

Essa é a essência do encapsulamento: **esconder a complexidade interna** e oferecer **operações controladas** para manter o objeto funcional e seguro.

### Regra Geral de Encapsulamento:

1. **Não exponha diretamente os atributos** de um objeto. Em vez disso, utilize o modificador de acesso **`private`** para garantir que eles só possam ser acessados por meio de métodos controlados.
    
2. **Utilize métodos `get` e `set`** (acessores e mutadores) para permitir o acesso controlado aos atributos, seguindo o padrão **JavaBeans**.
    

---

### Padrão JavaBeans

O padrão **JavaBeans** é um conjunto de convenções que define como os atributos de uma classe devem ser acessados e modificados. A regra principal é que os **atributos devem ser privados**, e o acesso a eles deve ser feito por meio de métodos **`get`** e **`set`**.

#### Exemplo de Implementação de `get` e `set`:


```java
private String name;  
private double price;   

// Método getter para acessar o nome 
public String getName() {     
	return name;  }   
	

// Método setter para modificar o nome 
public void setName(String name) {     
	this.name = name;  }   

// Getter para acessar o preço 
public double getPrice() {     
	return price;  }   

// Setter para modificar o preço 
public void setPrice(double price) {     
	this.price = price;  }`
```
Os métodos `get` e `set` são normalmente implementados **após os construtores** da classe.

---

### Exemplo Completo na Classe `Product`:


```java
`public class Product {     
	private String name;     
	private double price;     
	private int quantity;      
	
	// Construtor padrão     
	public Product() {
	}      
	
	// Construtor com todos os atributos     
	public Product(String name, double price, int quantity) {         
		this.name = name;         
		this.price = price;         
		this.quantity = quantity;     }      
		
	// Construtor com nome e preço     
	public Product(String name, double price) {         
		this.name = name;         
		this.price = price;     }      
		
	// Getter e setter para o nome     
	public void setName(String name) {         
		this.name = name;     }      
	
	public String getName() {         
		return name;     }      
		
	// Getter e setter para o preço     
	public void setPrice(double price) {         
		this.price = price;     }      
	
	public double getPrice() {         
		return price;     }      
		
	// Getter para quantidade (sem setter)     
	public int getQuantity() {         
		return quantity;     }      
		
	// Não há setter para 'quantity', pois ela só pode ser modificada     
	// através de operações específicas, como entrada e saída de estoque. }`
```
No exemplo acima:

- A quantidade (`quantity`) **não pode ser modificada diretamente** por meio de um método `set`. Ela só pode ser alterada por operações como entradas e saídas de estoque, evitando mudanças inconsistentes no valor.

---

### Acessando os Atributos pela Classe `Program`:

```java
`Product product = new Product("Laptop", 1500.00);  
// Instanciando um produto com o construtor  

product.setName("Computer"); // Modificando o atributo 'name'
System.out.println("Updated name: " + product.getName());  

// Acessando o atributo 'name'  
product.setPrice(1200.00); // Modificando o atributo 'price' 

System.out.println("Updated price: " + product.getPrice());  
// Acessando o atributo 'price'`
```
---

### Conclusão:

O encapsulamento garante que os atributos de uma classe **não sejam expostos diretamente**, protegendo-os de modificações não controladas. Ao utilizar **métodos `get` e `set`**, você controla como os atributos podem ser acessados e modificados, mantendo o estado do objeto sempre consistente.