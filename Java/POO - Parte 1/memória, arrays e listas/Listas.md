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
