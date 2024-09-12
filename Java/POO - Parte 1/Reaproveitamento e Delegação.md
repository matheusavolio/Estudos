# Aula66 - Criando um método para obtermos os benefícios de reaproveitamento e delegação

#ClassesObjetosAtributos 

Com o uso de CLASSE, agora nós temos uma variável composta do tipo "Triangle" para representar cada triângulo: 
```java
Triangle x, y; 
x = new Triangle(); 
y = new Triangle();
```
Agora vamos melhorar nossa CLASSE, acrescentando nela um MÉTODO para calcular a área.

---
---

#### public, static e void na criação de métodos

#Métodos-Funções 

|                        public                        |                                 static                                 |                           void                           |
| :--------------------------------------------------: | :--------------------------------------------------------------------: | :------------------------------------------------------: |
| para que a função fique dísponível em outras classes | Para que a função possa ser chamada independente de se criar um objeto | Serve para fazer uma ação sem precisar retornar um valor |

Agora, criamos um método para calcular a área, e o nosso código agora ficou assim:

```java
package entities;

public class Triangle {
        public double a;
        public double b;
        public double c;

        public double area(){
            double p = (a + b + c) / 2.0;
            return Math.sqrt(p * (p-a) * (p-b) * (p-c));
        }
    }
```
E adicionando a chamada do método, o código principal fica assim:
```java
package application;
import java.util.Scanner;
import entities.Triangle;
import java.util.Locale;

public class Program {
    public static void main(String[] args) {
    
        Locale.setDefault(Locale.US);
        Scanner sc = new Scanner(System.in);

        Triangle x, y;
        x = new Triangle(); // instanciando as variáveis `x` e `y`
        y = new Triangle();

        System.out.println("Enter the measures of triangule X: ");
        x.a = sc.nextDouble();
        x.b = sc.nextDouble();
        x.c = sc.nextDouble();
        
        System.out.println("Enter the measures of triangule Y: ");
        y.a = sc.nextDouble();
        y.b = sc.nextDouble();
        y.c = sc.nextDouble();

        double areaX = x.area(); // chamando o método e o atribuindo a areaX
        double areaY = y.area(); // chamando o método e o atribuindo a areaY

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
![[Capturar.jpg]]

#### Projeto da classe (UML)

![[Diagram.svg]]
#UML São dividos em três partes, Nome da classe, nome dos atributos e seus tipos, nome do método e seu tipo.


Os dois benefícios de se calcular a área de um triângulo por meio de um #Métodos-Funções dentro da #Classe Triangle:
- **Reaproveitamento de código**: Foi eliminado o código repetido (calculo das áreas dos triângulos x e y) no programa principal
- **Delegação de responsabilidade**: Quem deve ser responsável por saber como calcular a área de um triângulo, é o próprio triângulo. A lógica do cálculo da área não deve estar em outro lugar. Cada classe é responsável por si mesmo, isso é um princípio chamado de Coesão.

