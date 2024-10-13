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

![[Diagram 2.svg]]
#UML São dividos em três partes, Nome da classe, nome dos atributos e seus tipos, nome do método e seu tipo.


Os dois benefícios de se calcular a área de um triângulo por meio de um #Métodos-Funções dentro da #Classe Triangle:
- **Reaproveitamento de código**: Foi eliminado o código repetido (calculo das áreas dos triângulos x e y) no programa principal
- **Delegação de responsabilidade**: Quem deve ser responsável por saber como calcular a área de um triângulo, é o próprio triângulo. A lógica do cálculo da área não deve estar em outro lugar. Cada classe é responsável por si mesmo, isso é um princípio chamado de Coesão.


#this
`this` significa uma auto-referência ao objeto, é como se fosse uma referência para acessar o atributo da classe, por exemplo, temos a `classe product` que um de seus atributos é um i`nt quantity`, porém criamos um método que tem um `quantity` também no seu argumento, utilizamos o `this.quantity para nos referirmos ao atributo quantity da classe, e não ao parâmetro quantity`.

---
---

# Aula71 - #MembrosEstáticos

Uma classe possui membros -> **Atributos e métodos**

#### Membros Estáticos
- Também chamados membros de classe 
	- Em oposição a membros e instância
- São membros que fazem sentido independente de objetos. Não precisam de objeto para serem chamados. São chamados a partir do próprio nome da classe.
- Aplicações comuns:
	- Classes utilitárias
	- Declaração de constantes
- Uma classe possui somente membros estáticos, pode ser uma classe estática também. Esta classe não poderá ser instanciada.



![[EstaticMembers.jpg]]

#### Já no caso da Calculator, os valores dos cálculos não mudam para calculadoras diferentes, ou seja, são cálculos estáticos. O valor de PI também é estático.
---
---

#### Problema exemplo: 
Fazer um programa para ler um valor numérico qualquer, e daí mostrar quanto seria o valor de uma circunferência e do volume de uma esfera para um raio daquele valor. Informar também o valor de PI com duas casas decimais.

```java
EXEMPLO:
Enter radius: 3.0 
Circumference: 18.85 
Volume: 113.10 
PI value: 3.14
```

Checklist 
-  Versão 1: métodos na própria classe do programa 
	- Nota: dentro de um método estático você não pode chamar membros de instância da mesma classe. 
- Versão 2: classe Calculator com membros de instância 
- Versão 3: classe Calculator com método estático


#### Final
Utilizamos a palavra #final para declaramos um membro estático como constante, isso significa que os valores que estiverem dentro dessa classe, não poderão ser alterados depois.

Para declararmos #constantes, sempre utilize upper case, por exemplo:
```java
PI
NET_SALARY
MEDIA_STUDENT
```
Dentro de uma classe estática, você não pode chamar outros métodos que não sejam estáticos 
