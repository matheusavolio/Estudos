
# Aula67 - Um segundo exercício de exemplo sobre POO
 
 Fazer um programa para ler os dados de um produto em estoque (nome, preço e quantidade no estoque). Em seguida: 
-  Mostrar os dados do produto (nome, preço, quantidade no estoque, valor total no estoque)
-  Realizar uma entrada no estoque e mostrar novamente os dados do produto 
-  Realizar uma saída no estoque e mostrar novamente os dados do produto 

Para resolver este problema, você deve criar uma CLASSE conforme projeto ao lado: (veja exemplo)

![[Diagram 2.svg]]

```java
Enter product data: 
Name: TV 
Price: 900.00 
Quantity in stock: 10 

Product data: TV, $ 900.00, 10 units, Total: $ 9000.00 

Enter the number of products to be added in stock: 5 

Updated data: TV, $ 900.00, 15 units, Total: $ 13500.00 

Enter the number of products to be removed from stock: 3 

Updated data: TV, $ 900.00, 12 units, Total: $ 10800.00
```

---
---

# Aula68 - Object e toString

- #### Toda classe em Java é uma subclasse da classe `Object`
- #### Object possui os seguintes métodos:
	- ##### getClass - retorna o tipo do objeto
	- ##### equals - compara se o objeto é igual ao outro
	- ##### hashCode - retorna  um código hash do objeto
	- ##### toString - converte o objeto para string

##### Qualquer variável que você tiver no seu programa, ela vai ter um tipo, por exemplo:

Tipo tirangle, tipo product, porém, cada um desses tipos, é do tipo #object e ele tem algumas operações padrões que são mostradas acima.


---
---

## Explicação detalhada do código 1

```java
CÓDIGO 1
package entities2;

public class Product {
    public String name;
    public double price;
    public int quantity;

    public double totalValueInStock(){
        return price * quantity;
    }

    public void addProducts(int quantity){
        this.quantity += quantity;
    }

    public void removeProducts(int quantity){
        this.quantity -= quantity;
    }

    public String toString(){
        return name
        + ", U$ "
        + String.format("%.2f", price)
        + ", "
        + quantity
        + " units, Total: U$"
        + String.format("%.2f", totalValueInStock());
    }
}
```


```java
ANÁLISE
Linha 1:

package entities2;
- Explicação: 
Define o pacote ao qual a classe `Product` pertence. Pacotes são usados em Java para organizar o código e evitar conflitos entre classes que podem ter o mesmo nome, mas estão em pacotes diferentes. Nesse caso, o pacote é `entities2`.

---

Linha 3:
public class Product {

- Explicação: 
Declara a classe `Product` como pública, o que significa que ela pode ser acessada de qualquer lugar no programa. Uma classe em Java define o comportamento e o estado de um objeto, e a classe `Product` irá representar um produto no estoque.

---

Linha 4:

public String name;

- Explicação: 
Declara uma variável de instância (atributo) pública chamada `name` do tipo `String`. Isso significa que cada instância da classe `Product` terá uma variável `name`, que armazenará o nome do produto.

---

Linha 5:

public double price;

- Explicação 
Declara outra variável de instância pública, `price`, do tipo `double`. Esta variável armazenará o preço do produto.

---

Linha 6:

public int quantity;

- Explicação: 
Declara a variável de instância `quantity` do tipo `int`, que armazenará a quantidade de produtos disponíveis no estoque.

---

Linha 8:

public double totalValueInStock(){

- Explicação:
Define um método público chamado `totalValueInStock` que retorna um valor do tipo `double`. Esse método não recebe parâmetros e será usado para calcular o valor total em estoque de um produto.

---

Linha 9:

return price * quantity;

- Explicação: 
Este código dentro do método `totalValueInStock()` retorna o valor total em estoque multiplicando o `price` pelo `quantity` (preço pela quantidade em estoque). O resultado será o valor total de todos os produtos daquele tipo em estoque.

---

Linha 11:

public void addProducts(int quantity){

- Explicação: 
Define um método público `addProducts`, que não retorna nenhum valor (`void`). Ele recebe um parâmetro `int quantity`, que será usado para adicionar produtos ao estoque.

---

Linha 12:

this.quantity += quantity;

- Explicação: 
Dentro do método `addProducts`, o código adiciona a quantidade passada como parâmetro à variável de instância `quantity`. A palavra-chave `this` é usada para se referir à variável de instância `quantity` da classe. O operador `+=` faz a adição da nova quantidade à quantidade atual do produto no estoque.

---

Linha 14:

public void removeProducts(int quantity){

- Explicação: 
Define o método público `removeProducts`, que também não retorna valor (`void`). Ele recebe um parâmetro `int quantity`, que será usado para remover produtos do estoque.

---

### Linha 15:

this.quantity -= quantity;

- Explicação: 
Dentro do método `removeProducts`, o código subtrai a quantidade passada como parâmetro da variável de instância `quantity`. A palavra-chave `this` é usada para garantir que estamos nos referindo à variável da classe e não ao parâmetro local.

---

Linha 17:

public String toString(){

- Explicação: 
Este método sobrescreve o método `toString()` da classe `Object` em Java. O método `toString` é chamado automaticamente quando tentamos imprimir um objeto. Ele retorna uma `String` que representa o objeto, neste caso, uma descrição detalhada do produto.

---

Linhas 18 a 23:

return name     
	+ ", U$ "     
	+ String.format("%.2f", price)     
	+ ", "     
	+ quantity     
	+ " units, Total: U$"     
	+ String.format("%.2f", totalValueInStock());`

- Explicação: 
O método `toString` retorna uma `String` que contém:
    - O nome do produto (`name`).
    - A palavra "U$" seguida do preço do produto formatado com duas casas decimais (`String.format("%.2f", price)`).
    - A quantidade de unidades em estoque.
    - O valor total em estoque (preço multiplicado pela quantidade), também formatado com duas casas decimais. Ele usa o método `totalValueInStock()` para obter esse valor.
    
    Exemplo de saída: `"Laptop, U$ 1200.00, 5 units, Total: U$ 6000.00"`

---

Resumo Geral

A classe `Product` tem três atributos: `name`, `price` e `quantity`, que representam o nome, o preço e a quantidade de um produto, respectivamente. Ela possui três métodos principais:

1. `totalValueInStock`: calcula o valor total dos produtos em estoque.
2. `addProducts`: adiciona uma quantidade ao estoque.
3. `removeProducts`: remove uma quantidade do estoque.

O método `toString` sobrescreve o comportamento padrão de como o objeto é convertido para uma `String`, oferecendo uma descrição detalhada do produto.
```

---
---

## Análise detalhada do código 2
```java
ANÁLISE
CÓDIGO 2
package application2;

import java.util.Locale;
import java.util.Scanner;
import entities2.Product;

  

public class Program {
    public static void main(String[] args) {
        Locale.setDefault(Locale.US);
        Scanner sc = new Scanner(System.in);

        Product product = new Product();
        System.out.println("Enter product data: ");
        System.out.print("Name: ");
        product.name = sc.nextLine();

        System.out.print("Price: U$");
        product.price = sc.nextDouble();

        System.out.print("Quantity in stock: ");
        product.quantity = sc.nextInt();

        System.out.println();
        System.out.println("Product data: " + product);

  
        System.out.println();
        System.err.print("Enter the numbers of products to be added in stock: ");
        int quantity = sc.nextInt();
        product.addProducts(quantity);


        System.out.println();
        System.out.println("Updated product data: " + product);
        System.out.println();

  
        System.err.print("Enter the numbers of products to be remove from stock: ");
        quantity = sc.nextInt();
        product.removeProducts(quantity);

        System.out.println("Updated product data: " + product);
        System.out.println();

        sc.close();
    }
}
```

```java
ANÁLISE
Linha 1:

package application2;

- Explicação: 
Define o pacote onde a classe `Program` está localizada. O pacote `application2` está sendo utilizado para organizar as classes relacionadas ao programa de execução.

---
Linha 3:


import java.util.Locale; 
import java.util.Scanner; 
import entities2.Product;

- Explicação:
    - import java.util.Locale; : Importa a classe `Locale` da biblioteca Java. Esta classe é usada para definir configurações regionais, como formato de moeda e decimal.
    - import java.util.Scanner; : Importa a classe `Scanner`, que será utilizada para ler a entrada do usuário (input) no console.
    - import entities2.Product; : Importa a classe `Product` do pacote `entities2`. A classe `Product` foi criada no primeiro bloco de código e será usada no programa principal.

---

Linha 5:

public class Program {

- Explicação: 
Declara a classe `Program`. Esta classe é a principal do programa, onde a execução irá ocorrer.

---

Linha 6:

public static void main(String[] args) {

- Explicação: 
O método `main` é o ponto de entrada do programa. Todo programa Java inicia sua execução a partir do método `main`, e é necessário para rodar a aplicação. O argumento `String[] args` pode ser usado para passar informações pela linha de comando (neste caso, não está sendo usado).

---

Linha 7:

Locale.setDefault(Locale.US);

- Explicação: 
Define o local padrão como sendo o dos Estados Unidos. Isso garante que o programa use o formato de ponto decimal (.) para separar casas decimais, que é o padrão nos EUA, em vez de vírgula, como em outros locais.

---

Linha 8:

Scanner sc = new Scanner(System.in);

- Explicação:
Cria um objeto `Scanner` chamado `sc`, que é usado para ler dados de entrada do usuário pelo console. O `System.in` indica que a fonte da entrada será o teclado.

---

Linha 10:

Product product = new Product();

- Explicação: 
Cria um novo objeto `Product` chamado `product`. Este objeto será usado para armazenar os dados do produto (nome, preço, quantidade) e manipular suas propriedades e métodos.

---

Linha 12:

System.out.println("Enter product data: ");

-Explicação:
Exibe a mensagem "Enter product data: " no console para avisar ao usuário que ele deverá inserir as informações sobre o produto.

---

Linha 13-14:

System.out.print("Name: "); 
product.name = sc.nextLine();

- Explicação:
    - System.out.print("Name: "); : Pede ao usuário para inserir o nome do produto, sem pular uma linha.
    - product.name = sc.nextLine(); : Lê o nome do produto digitado pelo usuário e armazena na variável `name` do objeto `product`. O método `nextLine()` lê uma linha inteira de entrada.

---

Linha 16-17:

System.out.print("Price: U$"); product.price = sc.nextDouble();

- Explicação:
    - System.out.print("Price: U$"); : Pede ao usuário para inserir o preço do produto.
    - product.price = sc.nextDouble(); : Lê o preço do produto digitado pelo usuário e armazena na variável `price` do objeto `product`. O método `nextDouble()` lê um valor de ponto flutuante (decimal).

---

Linha 19-20:

System.out.print("Quantity in stock: "); 
product.quantity = sc.nextInt();

- Explicação:
    - System.out.print("Quantity in stock: ");: Pede ao usuário para inserir a quantidade do produto no estoque.
    - product.quantity = sc.nextInt(); : Lê a quantidade de produtos digitada pelo usuário e armazena na variável `quantity` do objeto `product`. O método `nextInt()` lê um valor inteiro.

---

Linha 22-23:

System.out.println(); 
System.out.println("Product data: " + product);

- Explicação:
    - A primeira linha System.out.println(); : apenas imprime uma linha em branco no console para dar espaçamento.
    - System.out.println("Product data: " + product); : Imprime os dados do produto usando o método `toString()` da classe `Product`, que já formatará a saída com o nome, preço, quantidade e valor total em estoque.

---

Linha 25-26:


System.err.print("Enter the numbers of products to be added in stock: "); 
int quantity = sc.nextInt();

- Explicação:
    - System.err.print("Enter the numbers of products to be added in stock: "); : Pede ao usuário para inserir o número de produtos que serão adicionados ao estoque. O uso de `System.err.print()` ao invés de `System.out.print()` envia a mensagem para o fluxo de erro (geralmente usado para mensagens de erro, mas pode ser usado para qualquer tipo de saída).
    - int quantity = sc.nextInt(); : Lê a quantidade de produtos a serem adicionados e a armazena na variável `quantity`.

---

### Linha 27:

product.addProducts(quantity);

- Explicação: Chama o método `addProducts` do objeto `product` para adicionar a quantidade digitada pelo usuário ao estoque.

---

Linha 28-30:



System.out.println(); 
System.out.println("Updated product data: " + product); 
System.out.println();

- Explicação:
    - A primeira e a terceira linha imprimem linhas em branco no console.
    - System.out.println("Updated product data: " + product); : Imprime os dados atualizados do produto, refletindo a nova quantidade após a adição.

---

Linha 32-33:

System.err.print("Enter the numbers of products to be remove from stock: "); 
quantity = sc.nextInt();

- Explicação:
    - System.err.print("Enter the numbers of products to be remove from stock: "); : Pede ao usuário para inserir o número de produtos a serem removidos do estoque.
    - quantity = sc.nextInt(); : Lê a quantidade de produtos a serem removidos e a armazena na variável `quantity`.

---

Linha 34:

product.removeProducts(quantity);

- Explicação: Chama o método `removeProducts` do objeto `product` para remover a quantidade especificada do estoque.

---

Linha 35-37:

System.out.println("Updated product data: " + product); 
System.out.println();

- Explicação:
    - System.out.println("Updated product data: " + product); : Imprime os dados atualizados do produto após a remoção de produtos do estoque.
    - A última linha imprime uma linha em branco no console.

---

Linha 38:

sc.close();

- Explicação: Fecha o objeto `Scanner` (liberando o recurso de entrada do teclado). É uma boa prática fechar o `Scanner` após o uso para evitar desperdício de recursos.

---

### Resumo Geral

Este programa em Java permite ao usuário inserir as informações de um produto (nome, preço e quantidade em estoque), adicionar produtos ao estoque e remover produtos. Ele usa a classe `Product` para armazenar e manipular as propriedades do produto, e o método `toString()` para imprimir uma descrição formatada do objeto.
```
