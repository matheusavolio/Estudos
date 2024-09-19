
# Aula96 - Boxing, unboxing e wrapper

####  #Boxing
- É o processo de conversão de um objeto tipo valor para um objeto tipo referência compatível

![[boxing.jpg]]

---
---
#### #Unboxing 
- É o processo de conversão de um objeto tipo referência para um objeto tipo valor compatível

![[unboxing.jpg]]

---
---
#### #Wrapper classes
- São classes equivalentes aos tipos #primitivos
- #Boxing e #Unboxing é natural da linguagem
- **Uso comum: Campos de entidades em sistemas da informação**
	- Pois tipos referências(classes) aceitam valor null e usufruem dos recursos OO
	
	![[Wrapper.jpg]]]

Isso é usada para que seja feito o boxing e unboxig de uma forma natural

As classes Wrapper são essenciais em Java para permitir que tipos primitivos sejam tratados como objetos. Isso é útil em coleções, como List e Map, que operam com objetos e não com tipos primitivos. Aqui estão os principais pontos sobre classes Wrapper:

1. **Tipos Primitivos e seus Wrappers**:
    
    - `int` -> `Integer`
    - `char` -> `Character`
    - `boolean` -> `Boolean`
    - `double` -> `Double`
    - `float` -> `Float`
    - `long` -> `Long`
    - `byte` -> `Byte`
    - `short` -> `Short`
2. **Boxing e Unboxing**:
    
    - **Boxing** é o processo de converter um tipo primitivo em um objeto Wrapper correspondente.
    - **Unboxing** é o processo inverso, onde um objeto Wrapper é convertido de volta para um tipo primitivo.
3. **Uso Comum**:
    
    - Os tipos Wrapper são frequentemente usados em coleções que apenas aceitam objetos.
    - Eles permitem a utilização de métodos de objetos em tipos primitivos.
    - Campos em entidades de sistemas de informação geralmente são declarados como Wrappers para aceitar valores `null` e para utilizar recursos da orientação a objetos.
4. **Exemplo de Boxing e Unboxing**:
    ```java
    Integer myInt = 10; // Boxing 
    int myPrimitive = myInt; // Unboxing`
```    

As classes Wrapper são fundamentais para o uso eficaz de recursos avançados de programação orientada a objetos em Java, especialmente ao trabalhar com estruturas de dados que requerem objetos ao invés de tipos primitivos.

---
---
# Aula97 - "Laço for each"
#forEach

**É uma sintaxe simplificada para percorrer coleções**
sintaxe básica:
```java
for (tipo apelido: colecção){
	<comando1>
	<comando2>
}
```

#### _Exemplo:_
```java
String[] vect = new Srtring[] {"Maria", "Bob", "Alex"};

for (String obj : vect){
	System.out.println("obj")}
```
