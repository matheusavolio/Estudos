### Aula 98 - Introdução às Listas (Parte 1)

- **Lista como Estrutura de Dados**:
    
    - **Homogênea**: Todos os elementos em uma lista são do mesmo tipo. Por exemplo, uma lista de inteiros (`List<Integer>`) só pode conter inteiros.
    - **Ordenada**: Os elementos são organizados de acordo com sua posição (índices), permitindo acesso sequencial a eles.
    - **Inicia vazia**: Diferente de arrays, que têm tamanho fixo, listas começam vazias e seu tamanho cresce conforme os elementos são adicionados.
    - **Elementos em "nós" (ou nodos)**: Cada elemento ocupa um espaço na lista, seja um índice ou uma referência de ligação, dependendo da implementação da lista.
- **Tipo `List` (Interface)**:
    
    - `List` é uma **interface** em Java, o que significa que ela define métodos (como `add`, `remove`, `size`), mas não pode ser instanciada diretamente. Para usar listas, você precisa de uma classe que implemente `List`, como `ArrayList` ou `LinkedList`.
- **Classes que Implementam `List`**:
    
    - **`ArrayList`**: Baseada em arrays, com acesso rápido por índices.
    - **`LinkedList`**: Baseada em nós encadeados, com inserções e remoções eficientes.
- **Vantagens**:
    
    - **Tamanho Variável**: As listas podem crescer e diminuir dinamicamente conforme os elementos são adicionados ou removidos.
    - **Facilidade em Inserir/Remover Elementos**: Diferente de arrays, é fácil modificar o conteúdo de uma lista.
- **Desvantagem**:
    
    - **Acesso Sequencial**: No caso de `LinkedList`, acessar um elemento específico pode ser mais lento, pois é necessário percorrer os nós até encontrar o índice.

---

### Aula 99 - Operações com Listas (Parte 2)

- **Operações Comuns**:
    
    - **Tamanho da Lista**: O método `size()` retorna o número de elementos na lista.
    - **Inserir Elemento**:
        - `add(obj)`: Adiciona um elemento no final da lista.
        - `add(int, obj)`: Adiciona um elemento em um índice específico.
    - **Remover Elemento**:
        - `remove(obj)`: Remove a primeira ocorrência do objeto especificado.
        - `remove(int)`: Remove o elemento no índice especificado.
        - `removeIf(Predicate)`: Remove todos os elementos que atendem a uma condição (usando um predicado ou expressão lambda).
    - **Encontrar Posição de um Elemento**:
        - `indexOf(obj)`: Retorna o índice da primeira ocorrência do elemento especificado.
        - `lastIndexOf(obj)`: Retorna o índice da última ocorrência do elemento especificado.
- **Filtrar Lista com Base em um Predicado**:
    
    - Você pode usar **streams** para filtrar elementos de uma lista. Por exemplo, o código abaixo filtra os elementos da lista `list` que são maiores que 4 e retorna o primeiro elemento que atende à condição:
    
    ```java
List<Integer> result = list.stream().filter(x>x>4).findFirst().orElse(null);`
```    
    - O uso de `filter()` permite criar filtros dinâmicos, e `findFirst()` retorna o primeiro valor encontrado. Caso nenhum valor satisfaça a condição, `orElse(null)` retorna `null`.

---

### Instanciando uma Lista em Java

Como a interface `List` não pode ser instanciada diretamente (porque é uma interface), é necessário utilizar uma das suas implementações, como `ArrayList`:

#### Sintaxe básica para instanciar uma lista:

```java
List<String> myList = new ArrayList<>();
```
Aqui, criamos uma lista de `String`, utilizando a classe `ArrayList`, que é a implementação de `List`. Este formato é comum para criar listas flexíveis e de fácil manipulação.