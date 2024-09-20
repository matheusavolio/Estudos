# Aula98 - Listas parte 1/2
#List

- _Lista é uma estrutura de dados:_
	- Homogênea(`dados do mesmo tipo`)
	- Ordenada(`elementos acessados por meio dos índices`)
	- Inicia vazia, e seus elementos são alocados sob demanda
	- cada elemento ocupa um "nó" (ou nodo) da lista
- Tipo ( #interface): #List
- _Classes que implementam_: ArrayList, LinkedLista, etc.
- _Vantagens_:
	- Tamanho variável 
	- Facilidade para se realizar inserções e deleções
- _Desvantagens:_
	- Acesso sequencial aos elementos *

Uma #interface é um tipo que determina apenas as especificações das operações, para se trabalhar com um objeto do tipo #List vamos ter que instanciar esse tipo, porém a interface não pode ser instanciada, vamos precisar de uma classe que implementa essa interface.
Se um tipo é interface, nós não podemos instanciar esse tipo     

 ![[MyList.jpg]] 

# Aula99 - Listas parte 2/2
#List 

- Tamanho da #lista: `size()`
- Inserir elemento na lista: `add(obj), add(int, obj)`
- Remover elementos da lista: `remove(obj), remove(int), removeIf(Predicate)`
- Encontrar posição de elemento: `indexOf(obj), lastIndexOf(obj)`
- Filtrar lista com base em predicado: 
```java
List<Integer> result=list.stream().filter(x->x>4).findFirst().orElse(null)
```


Para instanciar uma interface, que no caso é a lista, vamos precisar instanciar uma classe que implementa essa interface, que nesse caso é #ArrayList
#### *Sintaxe básica de lista:*
```java
List <wrapperClass> nameList = new ArrayList<wrapperClass>();
```

Para instanciar uma interface, que no caso é a lista, vamos precisar instanciar uma classe que implementa essa interface, que nesse caso é #ArrayList

## *Exemplo*:
```java
List<String> myList = new ArrayList<>();  
  
myList.add("Maria"); 
myList.add("Alex");  
myList.add("Bob");  
myList.add("Ana");  
myList.add(2, "Matheus");   
System.out.println(myList.size());  
System.out.println("----------------------------------");  
for (String obj : myList) {  
    System.out.println(obj); 
}  
myList.remove(1);   
myList.remove("Bob"); 
myList.add("Mauricio"); 
myList.add("Margarida"); 
myList.add("Lucas");  
System.out.println("------------Impressão após remoção-----------------");  
for (String obj : myList) {  
    System.out.println(obj); 
}  
System.out.println("------------Impressão após predicado-----------------");  
myList.removeIf(x -> x.charAt(0) == 'M'); 
for (String obj : myList) {  
    System.out.println(obj);  
}  
System.out.println("Index of Bob: " + myList.indexOf("Bob"));   
System.out.println("------------Apenas quem começa com M---------------");  
myList.add("Mauricio");  
myList.add("Margarida");    
List<String> result = myList.stream().filter(x -> x.charAt(0) == 'M').collect(Collectors.toList());
for (String x : result) {  
    System.out.println(x);  
}  
System.out.println("---------------------------");  
String name = myList.stream().filter(x -> x.charAt(0) == 'M').findFirst().orElse(null);  
System.out.println(name);
```

## *Análise:*

### Declaração da Lista

```java
List<String> myList = new ArrayList<>();`
```
- Criamos uma lista do tipo `String` chamada `myList`, utilizando a implementação `ArrayList` da interface `List`. `ArrayList` é uma lista baseada em arrays que permite acessar os elementos de maneira rápida por meio de índices.

---

### Adicionando Elementos

```java
myList.add("Maria"); 
myList.add("Alex"); 
myList.add("Bob"); 
myList.add("Ana");`
```
- Utilizamos o método `add()` para adicionar elementos ao final da lista, de forma similar ao método `append()` em Python. A lista agora contém: 
`["Maria", "Alex", "Bob", "Ana"]`.


```java
myList.add(2, "Matheus");`
```
- Aqui, o elemento `"Matheus"` é adicionado no índice `2`, empurrando os elementos subsequentes uma posição à frente. A lista agora fica: 
`["Maria", "Alex", "Matheus", "Bob", "Ana"]`.

---

### Exibindo o Tamanho da Lista

```java
System.out.println(myList.size());`
```
- O método `size()` retorna o número de elementos na lista. Após as inserções, o tamanho da lista é `5`.

---

### Imprimindo Todos os Elementos

```java
for (String obj : myList) {     
	System.out.println(obj); }`
```
- Esse `for-each` percorre todos os elementos da lista e os imprime. O resultado será:
    
    `Maria 
    `Alex 
    `Matheus 
    `Bob
	`Ana`
    

---

### Removendo Elementos

```java
myList.remove(1); 
myList.remove("Bob");`
```
- **Remover por índice**: Remove o elemento no índice `1`, que é `"Alex"`. A lista agora será: `["Maria", "Matheus", "Bob", "Ana"]`.
- **Remover por valor**: Remove o elemento `"Bob"` da lista, se ele existir. A lista agora será: `["Maria", "Matheus", "Ana"]`.

---

### Adicionando Novos Elementos


```java
myList.add("Mauricio"); 
myList.add("Margarida"); 
myList.add("Lucas");`
```
- Os elementos `"Mauricio"`, `"Margarida"`, e `"Lucas"` são adicionados ao final da lista, que fica assim:
`["Maria", "Matheus", "Ana", "Mauricio", "Margarida", "Lucas"]`.

---

### Removendo Elementos Usando Predicado (Lambda)

```java
myList.removeIf(x -> x.charAt(0) == 'M');`
```
- O método `removeIf()` utiliza uma expressão lambda que remove todos os elementos que começam com a letra `'M'`. A condição `x.charAt(0) == 'M'` verifica se o primeiro caractere (`charAt(0)`) de cada elemento é `'M'`. Após essa operação, os elementos removidos serão `"Maria"`, `"Matheus"`, `"Mauricio"`, e `"Margarida"`, deixando a lista assim: `["Ana", "Lucas"]`.

---

### Encontrando o Índice de um Elemento


```java
System.out.println("Index of Bob: " + myList.indexOf("Bob"));`
```
- O método `indexOf()` retorna o índice do elemento `"Bob"`, mas como `"Bob"` já foi removido anteriormente, o método retornará `-1`, indicando que o elemento não foi encontrado.

---

### Filtrando Elementos com `stream()` e `filter()`

```java
List<String> result = myList.stream().filter(x -> x.charAt(0) == 'M').collect(Collectors.toList());`
```
- Convertemos a lista `myList` para um `stream`, aplicamos o filtro para selecionar apenas os elementos que começam com a letra `'M'`, e utilizamos o `collect()` para transformar o resultado de volta em uma lista. No final, a lista `result` conterá `"Mauricio"` e `"Margarida"`.

---

### Encontrando o Primeiro Elemento que Atende à Condição

```java
String name = myList.stream().filter(x -> x.charAt(0) == 'M').findFirst().orElse(null);`
```
- Aqui, utilizamos o `stream()` e o `filter()` para buscar o primeiro elemento da lista que começa com a letra `'M'`. O método `findFirst()` retorna o primeiro elemento que atende à condição. Caso nenhum elemento seja encontrado, `orElse(null)` retorna `null`. Se a lista contém algum nome com `'M'`, ele será impresso, caso contrário, o resultado será `null`.

---

### Resumo do Fluxo

1. A lista começa com quatro nomes: `"Maria"`, `"Alex"`, `"Bob"`, e `"Ana"`.
2. Após adicionar `"Matheus"` no índice 2, a lista fica com cinco elementos.
3. Removemos `"Alex"` e `"Bob"`.
4. Adicionamos `"Mauricio"`, `"Margarida"`, e `"Lucas"`.
5. Removemos os elementos que começam com `'M'`, deixando apenas `"Ana"` e `"Lucas"`.
6. Filtramos e exibimos os elementos que começam com `'M'`, além de buscar o primeiro elemento com essa característica.

---
---
### *Código do exercício:*
```java
public class Program {  
    public static void main(String[] args) {  
        Locale.setDefault(Locale.US);  
        Scanner sc = new Scanner(System.in);  
        List<Employee> list = new ArrayList<>();  
  
  
        System.out.print("How many employees will be registered? ");  
        int n = sc.nextInt();  
  
        for (int i = 1; i <= n; i++) {  
            System.out.printf("Employee #%d:\n", i);  
  
            System.out.print("ID: ");  
            Integer ID = sc.nextInt();  
            while (hasId(list, ID)) {  
                System.out.println("Id already taken. Try again: ");  
            }  
            System.out.print("Name: ");  
            sc.nextLine();  
            String name = sc.nextLine();  
            System.out.print("Salary: U$");  
            Double salary = sc.nextDouble();  
            list.add(new Employee(ID, name, salary));  
            System.out.println();  
        }  
  
  
		System.out.print("Enter the employee id that will have salary increase: ");  
        int getIdd = sc.nextInt();  
        Employee result = list.stream()  
                .filter(x -> x.getId() == getIdd)  
                .findFirst().orElse(null);  
        if (result == null) {  
            System.out.println("This id does not exist!");  
        } else {  
            System.out.print("Enter the percentage: ");  
            double percentage = sc.nextDouble();  
            result.increaseSalary(percentage);  
        }  
  
        System.out.println();  
        System.out.println("List of employees: ");  
        for (Employee obj : list) {  
            System.out.println(obj);  
        }  
        sc.close();  
    }  
  
    public static boolean hasId(List<Employee> list, int id) {  
	        Employee emp = list.stream().filter(x -> x.getId() == 
	        id).findFirst().orElse(null);  
        return emp != null;  
    }  
}
```

### *Análise do exercício:*
### Classe `Program`

```java
public class Program {`
```
- Define uma classe pública chamada `Program`, que será o ponto de entrada do programa.

### Método `main`
```java
public static void main(String[] args) {`
```
- Este é o método principal que será executado quando o programa começar. A palavra-chave `static` significa que ele pode ser chamado sem instanciar a classe. `String[] args` permite a passagem de argumentos via linha de comando.

### Configuração do Locale

```java
Locale.setDefault(Locale.US);`
```
- Define o padrão de localidade para os Estados Unidos (US), o que afeta a formatação de números e moedas (usando ponto para separar decimais, por exemplo).

### Criação de `Scanner` e `List`

```java
Scanner sc = new Scanner(System.in); 
List<Employee> list = new ArrayList<>();`
```
- `Scanner` é usado para capturar entradas do usuário via console. A variável `list` é uma `ArrayList` que irá armazenar objetos da classe `Employee`, que presumivelmente é uma classe personalizada (não mostrada no código).

### Pergunta inicial

```java
System.out.print("How many employees will be registered? "); 
int n = sc.nextInt();`
```
- O programa pergunta quantos funcionários serão registrados. O valor é lido com `sc.nextInt()`, que captura um número inteiro digitado pelo usuário e armazena na variável `n`.

### Loop de registro de funcionários

```java
for (int i = 1; i <= n; i++) {     
	System.out.printf("Employee #%d:\n", i);
```
- Um loop `for` é iniciado para registrar `n` funcionários. A variável `i` vai de 1 até `n`, e `System.out.printf()` formata a string, exibindo o número do funcionário a ser registrado.

### Leitura do ID

```java
System.out.print("ID: "); 
Integer ID = sc.nextInt();`
```
- O programa solicita o ID do funcionário e o armazena na variável `ID`.

### Validação do ID (evitar duplicados)

```java
while (hasId(list, ID)) {     
	System.out.println("Id already taken. Try again: "); 
}
```
- O método `hasId()` verifica se o ID já foi registrado na lista de funcionários. Se o ID já existir, ele solicita ao usuário que insira um novo ID.

### Leitura do Nome e Salário

```java
System.out.print("Name: "); 
sc.nextLine(); // Limpa o buffer String 
name = sc.nextLine(); 
System.out.print("Salary: U$"); 
Double salary = sc.nextDouble();
```
- O programa solicita o nome do funcionário e, em seguida, o salário. O comando `sc.nextLine()` vazio é necessário para limpar o buffer de entrada do `Scanner` após o uso de `sc.nextInt()`, garantindo que o nome seja lido corretamente.

### Adicionando o funcionário à lista

java

Copiar código

`list.add(new Employee(ID, name, salary)); System.out.println();`

- Um novo objeto `Employee` é criado e adicionado à lista `list`. O objeto armazena as informações do funcionário.

### Aumento de salário por ID
```java
System.out.print("Enter the employee id that will have salary increase: "); 
int getIdd = sc.nextInt();`
```
- O programa solicita o ID do funcionário que terá aumento salarial. Este valor é armazenado em `getIdd`.

### Localizando o funcionário para aumento de salário
```java
Employee result = list.stream()     
	.filter(x -> x.getId() == getIdd)     
	.findFirst().orElse(null);`
```
- Aqui, um `stream()` da lista de funcionários é criado para filtrar o funcionário cujo ID seja igual a `getIdd`. O método `findFirst()` retorna o primeiro funcionário encontrado ou `null` se nenhum funcionário for encontrado com o ID informado.

### Verificação se o ID existe

```java
if (result == null) {     
	System.out.println("This id does not exist!"); 
}
```
- Se o funcionário com o ID fornecido não for encontrado, o programa exibe uma mensagem informando que o ID não existe.

### Aplicando o aumento salarial


```java
else {     
	System.out.print("Enter the percentage: ");     
	double percentage = sc.nextDouble();     
	result.increaseSalary(percentage); 
	}`
```
- Se o funcionário for encontrado, o programa solicita a porcentagem do aumento salarial e chama o método `increaseSalary()` para aplicar o aumento.

### Exibição da lista de funcionários

```java
System.out.println(); 
System.out.println("List of employees: "); 
for (Employee obj : list) {     
	System.out.println(obj); }
```
- Depois de tratar os aumentos de salário, o programa imprime a lista de funcionários usando um loop `for-each` para iterar sobre cada `Employee` na lista e exibir seus detalhes.

### Fechamento do `Scanner`

```java
sc.close();
```
- O `Scanner` é fechado, liberando os recursos associados à leitura de entrada.

### Método auxiliar `hasId()`
```java
public static boolean hasId(List<Employee> list, int id) {     
	Employee emp = list.stream()
	.filter(x -> x.getId() == id)
	.findFirst().orElse(null);     
	return emp != null; }
```
- O método `hasId()` verifica se um determinado ID já existe na lista de funcionários. Ele faz isso filtrando a lista com base no ID e retorna `true` se encontrar um funcionário com aquele ID, ou `false` caso contrário.

