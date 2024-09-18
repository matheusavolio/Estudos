
#### Tipos referências vs tipo valor
### Explicação:
1. **Referências em Java**:

    - Quando você declara uma variável de um tipo de classe em Java, essa variável não contém o próprio objeto, mas sim uma **referência** (ou seja, um "endereço") que aponta para onde o objeto está armazenado na **Heap**.
    - Essa referência funciona de maneira semelhante a um **ponteiro**, indicando onde, na memória, o objeto pode ser encontrado, mas sem expor diretamente o endereço de memória, como os ponteiros fazem em C/C++.
    - 
2. **Criação de Objetos**:
    - Quando um objeto é criado em Java com o operador `new`, o objeto real é alocado na **Heap**, e a variável que você declarou armazena uma **referência** para esse objeto.
    - Exemplo:

```java
 Product p1 = new Product("TV", 900.00, 0);
```

Nesse código, a variável `p1` não contém o objeto `Product` diretamente, mas sim uma referência para o local na **Heap** onde o objeto `"TV", 900.00, 0` está armazenado.
3. **Uso de Referências**:
    - Sempre que você acessa um método ou um atributo de um objeto, o Java segue a **referência** da variável até o local da **Heap** onde o objeto está armazenado e executa a ação desejada.
    - Exemplo:
        
```java
System.out.println(p1.getName());
```        

O código acima segue a referência `p1` até o objeto `Product` na **Heap** e acessa o método `getName()` para imprimir o nome `"TV"`.
4. **Sem ponteiros explícitos**:
    
    - Diferente de linguagens como C, você não tem controle explícito sobre o endereço de memória em Java. O gerenciamento de memória é feito automaticamente pelo **Garbage Collector**, que desaloca objetos da memória **Heap** quando não há mais referências apontando para eles, como vimos anteriormente.
![[Classes_referencias 1.jpg]]

---
---
#### #null 
#### Valor `null` em Java

Em Java, os tipos de referência são aqueles que referenciam objetos. Diferentemente dos tipos primitivos, como `int` e `char`, que armazenam valores diretamente, os tipos de referência armazenam referências a objetos na memória. Isso significa que uma variável de tipo referência pode apontar para um objeto ou, em alguns casos, para nenhum objeto.

O valor especial `null` é utilizado para indicar que uma variável de tipo referência não está atualmente apontando para nenhum objeto. Em outras palavras, quando uma variável é atribuída ao valor `null`, ela não está associada a nenhum objeto válido na memória.

1. **Declaração e Inicialização**:
    - Quando você declara uma variável de tipo referência sem inicializá-la, ela não tem um valor definido.
    - Por padrão, variáveis de tipo referência declaradas em uma classe são inicializadas com `null`.
    
    ```java
	String nome; // Declaração de uma variável de tipo referência 
	System.out.println(nome); // Isso imprimirá "null"`
    ```
2. **Atribuição de `null`**:
    
    - Você pode explicitamente atribuir o valor `null` a uma variável de tipo referência.

    ```java
    String nome = null; // A variável 'nome' não aponta para nenhum objeto`
    ```
3. **Checagem de `null`**:
    
    - Antes de utilizar uma variável de tipo referência, é uma boa prática verificar se ela é `null` para evitar erros em tempo de execução, como o `NullPointerException`.
    

    ```java
    `if (nome != null) {     
	    System.out.println(nome.length()); // Seguro para usar 'nome' aqui 
	} 
	else {     
		System.out.println("A variável 'nome' é null."); 
		    }`
    ```
4. **Uso Comuns**:
    
    - `null` é frequentemente usado para indicar a ausência de valor ou para inicializar variáveis de tipo referência quando o valor real não é conhecido ainda.
    
    ```java
    List<String> listaDeNomes = null; // A lista ainda não foi criada`
    ```
5. **Cuidado com `NullPointerException`**:
    
    - Tentativas de acessar métodos ou propriedades de uma variável que é `null` levarão a uma exceção `NullPointerException`. Sempre verifique se a variável é `null` antes de usá-la.
    
```java
    `String texto = null; 
    System.out.println(texto.length()); // Isso causará NullPointerException`
    ```

**Resumo**: Em Java, `null` é um valor especial atribuído a variáveis de tipo referência para indicar que elas não apontam para nenhum objeto na memória. É crucial verificar se uma variável é `null` antes de utilizá-la para evitar exceções indesejadas.

---
---
### Tipos Primitivos e Tipos Valor em Java

Em Java, os tipos primitivos são considerados tipos valor. Aqui está uma explicação mais detalhada sobre o conceito:

#### Tipos Primitivos

Os tipos primitivos em Java são os tipos de dados mais básicos fornecidos pela linguagem. Eles incluem:

- `byte`: 8 bits
- `short`: 16 bits
- `int`: 32 bits
- `long`: 64 bits
- `float`: 32 bits
- `double`: 64 bits
- `char`: 16 bits (representa um caractere Unicode)
- `boolean`: Representa `true` ou `false`

#### Tipos Valor

Os tipos valor são caracterizados por armazenarem diretamente o valor em vez de uma referência a um local de memória. Em outras palavras:

- **Armazenamento Direto**: Variáveis de tipo valor armazenam o dado diretamente na memória onde a variável é alocada. Não há uma referência ou ponteiro envolvido.
    
- **Cópia por Valor**: Quando uma variável de tipo valor é atribuída a outra, uma cópia do valor é criada. Alterações na nova variável não afetam a variável original.
    
    ```java
    int a = 10; 
    int b = a; // 'b' recebe uma cópia do valor de 'a' 
    b = 20;    // Alterando 'b' não afeta 'a' 
    System.out.println(a); // Imprime 10 
    System.out.println(b); // Imprime 20`
    ```
- **Eficiência**: Tipos valor são geralmente mais eficientes em termos de memória e processamento, pois não há sobrecarga associada à manipulação de referências.
    
#### Comparação com Tipos Referência

Em contraste com os tipos primitivos (tipos valor), os tipos referência:

- **Armazenamento de Referências**: Armazenam uma referência (ou ponteiro) para o objeto na memória, e não o próprio objeto.
    
- **Cópia de Referência**: Quando uma variável de tipo referência é atribuída a outra, ambas as variáveis referenciam o mesmo objeto. Alterações feitas em um são refletidas no outro.
    
```java
    `String str1 = "Hello"; 
    String str2 = str1; // 'str2' refere-se ao mesmo objeto que 'str1' 
    str2 = "World";    // Alterando 'str2' não muda 'str1' 
    System.out.println(str1); // Imprime "Hello" 
    System.out.println(str2); // Imprime "World"`
    ```
- **Instanciação e Gerenciamento**: Requerem o uso do operador `new` para criação e são gerenciados pela memória heap, com coleta automática de lixo (Garbage Collector).
#### Resumo

- **Tipos Primitivos (Tipos Valor)**: Armazenam valores diretamente e não têm sobrecarga de referências. São mais eficientes para operações simples e comparações rápidas.
- **Tipos Referência**: Armazenam referências a objetos e permitem o uso de recursos da programação orientada a objetos, mas com um custo adicional de gerenciamento e sobrecarga de memória.
![[primitvos_caixas.jpg]]


Quando você aloca (usando `new`) qualquer tipo estruturado, como classes ou arrays, o Java atribui valores padrão aos seus elementos. Isso ajuda a evitar que você tenha que inicializar manualmente cada elemento.

**Valores padrão:**

- **Números (`int`, `float`, `double`, etc.)**: 0
- **Booleanos (`boolean`)**: `false`
- **Caracteres (`char`)**: caractere com código 0 (representado como `'\u0000'`)
- **Objetos (`String`, arrays, etc.)**: `null`


![[memória.jpg]]

### Comparação Entre Tipos Referência (Classe) e Tipos Primitivos

|**Classe (Tipo Referência)**|**Tipo Primitivo**|
|---|---|
|**Vantagem**: Usufrui de todos os recursos da programação orientada a objetos (OO), como herança, polimorfismo e encapsulamento.|**Vantagem**: Simples e mais eficiente em termos de performance, pois não requer a sobrecarga associada à manipulação de objetos.|
|**Variáveis**: Armazenam referências (ou ponteiros) para os objetos na memória.|**Variáveis**: Armazenam valores diretamente (como números ou caracteres).|
|**Instanciação**: Objetos precisam ser criados usando o operador `new`, ou referenciar um objeto já existente.|**Instanciação**: Não é necessário instanciar. Uma vez declarado, o valor está pronto para uso.|
|**Valor `null`**: Aceita o valor `null`, indicando que a variável não está apontando para nenhum objeto.|**Valor `null`**: Não aceita o valor `null`, pois os tipos primitivos sempre contêm um valor válido.|
|**Atribuição**: Quando você faz `Y = X`, `Y` passa a referenciar o mesmo objeto que `X` (ambas as variáveis apontam para o mesmo local na memória).|**Atribuição**: Quando você faz `Y = X`, `Y` recebe uma cópia do valor armazenado em `X`.|
|**Localização na Memória**: Objetos são instanciados na área da memória chamada "heap".|**Localização na Memória**: Tipos primitivos são armazenados na área da memória chamada "stack".|
|**Gerenciamento de Memória**: Objetos não utilizados são automaticamente desalocados pelo Garbage Collector em um momento próximo.|**Gerenciamento de Memória**: Variáveis de tipos primitivos são desalocadas automaticamente quando seu escopo de execução termina.|

### Explicações Adicionais

1. **Vantagem**:
    
    - **Classe**: Permite o uso de conceitos da orientação a objetos, o que pode levar a um código mais modular e reutilizável.
    - **Tipo Primitivo**: Simples e eficiente, ideal para operações matemáticas e comparações rápidas.
2. **Variáveis**:
    
    - **Classe**: Armazena referências que podem ser direcionadas para diferentes objetos durante a execução.
    - **Tipo Primitivo**: Armazena o valor real, como um número ou caractere, diretamente na variável.
3. **Instanciação**:
    
    - **Classe**: Usar `new` para criar um novo objeto é uma operação mais pesada em termos de recursos.
    - **Tipo Primitivo**: Não requer alocação dinâmica, já que os valores são alocados diretamente na pilha (stack).
4. **Valor `null`**:
    
    - **Classe**: Usado para indicar que a variável não está associada a nenhum objeto específico.
    - **Tipo Primitivo**: Não pode ser `null`; sempre terá um valor padrão ou especificado.
5. **Atribuição**:
    
    - **Classe**: `Y` e `X` referenciam o mesmo objeto, alterações em `X` refletirão em `Y`.
    - **Tipo Primitivo**: `Y` é uma cópia independente de `X`, mudanças em `X` não afetam `Y`.
6. **Localização na Memória**:
    
    - **Classe**: "Heap" é onde objetos são alocados e gerenciados pelo Garbage Collector.
    - **Tipo Primitivo**: "Stack" é onde variáveis de tipos primitivos são rapidamente alocadas e desalocadas.
7. **Gerenciamento de Memória**:
    
    - **Classe**: O Garbage Collector cuida da desalocação de objetos não referenciados.
    - **Tipo Primitivo**: Desalocado automaticamente quando a execução sai do escopo.

