# Aula64 - Resolvendo um problema sem POO

Problema exemplo:
Fazer um programa para ler as medidas dos lados de dois triângulos X e Y (suponha medidas válidas). Em seguida, mostrar o valor das áreas dos dois triângulos e dizer qual dos dois triângulos possui a maior área. A fórmula para calcular a área de um triângulo a partir das medidas de seus lados a, b e c é a seguinte (fórmula de Heron)

```java
package application;
import java.util.Scanner;
import java.util.Locale;
public class Program {
    public static void main(String[] args) {
        
        Locale.setDefault(Locale.US);
        Scanner sc = new Scanner(System.in);
        
        double xA, xB, xC, yA, yB, yC, p, areaX, areaY;
        
        System.out.println("Enter the measures of triangule X: ");
        xA = sc.nextDouble();
        xB = sc.nextDouble();
        xC = sc.nextDouble();

  
        System.out.println("Enter the measures of triangule Y: ");
        yA = sc.nextDouble();
        yB = sc.nextDouble();
        yC = sc.nextDouble();

        p = (xA + xB + xC) / 2.0;
        areaX = Math.sqrt(p * (p-xA) * (p-xB) * (p-xC));
        
        p = (yA + yB + yC) / 2.0;
        areaY = Math.sqrt(p * (p-yA) * (p - yB) * (p - yC));

        System.out.printf("Triangle X area: %.4f\n", areaX);
        System.out.printf("Triangle Y area: %.4f\n", areaY);
        
        if (areaX > areaY){
            System.out.printf("Larger area: X");
        }
        else{
            System.out.printf("Larger area: Y");
        }
        sc.close();
    }
}
```
---
---
# Aula65 - Criando uma classe com três atributos para representar melhor o triângulo


#### Discussão
O triângulo é uma entidade com três atributos: a, b, c

Usamos três variáveis distintas para representar cada triângulo

```java
double aX, bX cX, aY, bY, cY;
```
Para melhorar isso, podemos utilizar uma classe para representar o triângulo

---
---
# #Classe

- É um tipo estruturado que pode conter (membros)
	- `Atributos` (dados/campos)
	- `Métodos` (funções/operações)
- A classe também pode prover muitos outros recursos, tais como:
	- `Construtores`
	- `Sobrecarga`
	- `Encapsulamento`
	- `Herança`
	- `Polimorfismo`
- Exemplos:
	- Entidades: Produto, Cliente, Triangulo
	- Serviços: ProdutoService, ClienteService, EmailService, StorageService
	- Controladores: ProdutoController, ClienteController
	- Utilitários: Calculadora, Compactador
	- Outros (views, repositórios, gerenciadores, etc.)


Exemplo de #membro e #atributo:
- Vamos ter o `membro triangulo`,  que vai ter os `atributos A, B e C`
- Vamos ter o `membro Cliente`, que vai ter os `atributos nome, CPF, telefone, email`, etc

---
---

#### Discussão
O triângulo é uma entidade com três atributos: a, b, c
Usamos três variáveis distintas para representar cada triângulo
```java
double aX, bX cX, aY, bY, cY;
```
Para melhorar isso, podemos utilizar uma classe para representar o triângulo

No exemplo, sem a utilização do POO, a memória fica assim:

![[meoria.poo.ex.jpg]]




Agora, utilizando POO, ela fica assim:
Quando a variável é do tipo classe, temos que instanciar ela.
Esses quadradinhos de memória abaixo, não é criado automaticamente, por isso utilizamos `new` para isso.
![[memorio.poo.ex2.jpg]]
Exemplo: 
```java
Triangle x, y;
x = new Triangle(); 
y = new Triangle()
```
Após instanciar ela, ai sim os quadrados de memória estarão alocados

---
---
No código abaixo, eu substitui todas as variáveis, por apenas x e y do tipo Triangule, como mostrado acima.
```java
Triangule.java

package entities;
public class Triangle {
        public double a;
        public double b;
        public double c;

    }
```

E agora, o programa que não tinha POO, fica assim:
```java
Program.java
package application;
import java.util.Scanner;
import entities.Triangle;
import java.util.Locale;

public class Program {
    public static void main(String[] args) {

        Locale.setDefault(Locale.US);
        Scanner sc = new Scanner(System.in);

        Triangle x, y;
        x = new Triangle();
        y = new Triangle();

  
        System.out.println("Enter the measures of triangule X: ");
        x.a = sc.nextDouble();
        x.b = sc.nextDouble();
        x.c = sc.nextDouble();

  

        System.out.println("Enter the measures of triangule Y: ");
        y.a = sc.nextDouble();
        y.b = sc.nextDouble();
        y.c = sc.nextDouble();

        double p = (x.a + x.b + x.c) / 2.0;
        double areaX = Math.sqrt(p * (p-x.a) * (p-x.b) * (p-x.c));

        p = (y.a + y.b + y.c) / 2.0;
        double areaY = Math.sqrt(p * (p-y.a) * (p - y.b) * (p - y.c));

        System.out.printf("Triangle X area: %.4f\n", areaX);
        System.out.printf("Triangle Y area: %.4f\n", areaY);

        if (areaX > areaY){
            System.out.printf("Larger area: X");
        }
        else{
            System.out.printf("Larger area: Y");
        }
        sc.close();
    }
}
```

#### #Instanciação
`alocação de memória`

As variáveis declaradas, são criadas numa área da memória chamada de `Stack`, que é a área aonde são criadas as variáveis estáticas 

Durante a execução do programa, podemos fazer uma alocação dinâmica de memoria, utilizando o `new`, e no momento que utilizamos o `new`, vai ser criado/instanciado um objeto do tipo da Classe em uma outra área da memória, o `Heap`, essa área é uma área aonde são criados os objetos dinâmicos  durante a execução.

Por exemplo, quando instanciamos o objeto Triangulo, na parte da memória `Heap` vai ser criado um espaço pra ele, e a variável `x` criada para ser o argumento da classe, também vai existir na área `Stack`, porém, dentro dele vai estar um endereço de memória , que é o enderço do objeto que foi criado no `heap`.
Então, a variável `x` é uma referência ao objeto que está no `heap` 

![[Instanciação.jpg]]

---
---
#### Resumo da aula:

#Classes #Objetos #Atributos
- Classe: É a definição do tipo
- Objetos - são instâncias da classe
