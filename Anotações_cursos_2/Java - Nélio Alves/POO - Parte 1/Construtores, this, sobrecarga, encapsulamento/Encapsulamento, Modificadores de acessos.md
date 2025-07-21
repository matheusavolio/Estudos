# Aula79 - Encapsulamento 
#### #Encapsulamento

- É um princípio que consiste em esconder detalhes de implementação de uma classe, expondo apenas operações seguras que mantenham os objetos em um estado consistente.

- Regra de ouro: O objetivo deve sempre estar em um estado consistente, e a própria classe deve garantir isso.

#### Analogia de encapsulamento:
Por exemplo, um aparelho de som. O aparelho de som internamente tem vários circuitos, conexões e operações acontecendo dentro dele, porém, o usuário do aparelho, ele não pode acessar diretamente os circuitos, vai que ele liga um componente no outro de forma errada e gera um estado inválido no aparelho ou até queimando.  E o que o aparelho de som faz? ele vai esconder todos esses detalhes de circuitos e vai disponibilizar para o usuário somente operações que não vão corromper o aparelho, por exemplo: Colocar um disco no aparelho, pausar e despausar a música, aumentar e diminuir o som do aparelho, etc. Essas são as operações que são expostas para o usuário, o que vai acontecer internamente ali, não tem acesso para o usuário e esse é o #PrincipioDoEncapsulamento, você vai esconder detalhes de implementação da sua classe, e expor apenas operações seguras que mantenham os objetos em estado consistente.

#### Regra geral básica
- Um objeto **Não** deve expor nenhum atributo (modificador de acesso **private**)
- Os atributos devem ser acessados por meio de #get e #set 
	- Padrão JavaBeans: https://en.wikipedia.org/wiki/JavaBeans

#JavaBeans é um padrão de desenvolvimento que oferece algumas regras básicas para você construir os objetos, uma delas é que os atributos devem ser privados e devem ser acessados por meio de #get e #set 

#### Padrão para implementação de #getters e #setters

```java

private String name; 
private double price; 

public String getName() { // Método para acessar o atributo
	return name; 
} 
public void setName(String name) { // Método para alterar valor do atributo
	this.name = name; 
} 
public double getPrice() { // Acessa o atributo
	return price; 
} 

public void setPrice(double price) { // Altera o atributo
	this.price = price; 
}
```

Métodos #get e #set, são feitos após os construtores.

### Exemplo na classe Product
```java
public class Product { // classe principal
    private String name;
    private double price;
    private int quantity;

    public Product(){ // construtor padrão
    }
    
    public Product(String name, double price, int quantity){
        this.name = name;
        this.price = price;
        this.quantity = quantity;} // contrutor 2
        
    public Product(String name, double price){
        this.name = name;
        this.price = price;} // construtor 3
  
  
        public void setName(String name){ // Alterando valor do atributo encapsulado
            this.name = name;} 
       
        public String getName(){ // Acessando atributo encapsulado
            return name;}


        public void setPrice(double price){ // Alterando valor do atributo encapsulado
            this.price = price;}

        public double getPrice(){ // Acessando atributo encapsulado
            return price;}

        public int getQuantity(){ 
            return quantity;}
                             // como a quantidade só pode ser alterada 
                             // quando o produto tiver
                             // uma entrada ou saída, só vai ser permitida 
	                         // acessar esse valor
	                         // e não modificalo
	                         // Nãi vai ser criado o método setQuantity 
	                         // para proteger alterações inconsistentes 
	                         // no produto   
	                         // então ela só pode mudar por meio das  
	                         // entradas e saídas do estoque  
```

#### Acessando os atributos pela classe Program 

```java
		Product product = new Product(name, price); 
		// instanciando e utilizando contrutor 2

        product.setName("Computer"); // modificando atributo encapsulado
        System.out.println("Updated name: " + product.getName()); 
        // acessando atributo encapsulado

        product.setPrice(1200.00); // modificando atributo encapsulado
        System.out.println("Updated price: " + product.getPrice()); 
        // acessando atributo encapsulado
```

---
---

# Aula80 - Gerando automaticamente construtores, getters e setters.
#### #GerarGetSetConstructorAutomaticamente

Para gerar #getters, #setter e #constructor, no Intellij utilizamos alt + insert para abrir a paleta de geração, e podemos selecionar o que gerar automaticamente por lá 

---
---


# Aula81 - Modificadores de acessos

- #private: O membro só pode ser acessado na `própria classe`
- (nada): O membro só pode ser acessado nas classes do `mesmo pacote`
- #protectec: O membro só pode ser acessado no` mesmo pacote`, bem como em `subclasses de pacotes diferentes`
- #public: O membro é acessado por todas as classes (ao menos que ele resida em módulo diferente que não exporte o pacote onde ele está )

![[Pasted image 20240917111513.png]]
