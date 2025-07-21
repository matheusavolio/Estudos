## Aula89 -  #Vetores parte 1/2

- *Checklist*
	- Declaração e instanciação
	- Manipulação de vetor de elementos tipo valor (tipo primitivo)
	- Manipulação de vetor de elementos tipo referência (classe)
	- Acesso aos elementos
	- propriedade #lenght

#### *O que são vetores:*
- Em programação, "vetor" é o nome dado a arranjos unidimensionais
- *Arranjo ( #array) é uma estrutura de dados:*
	- Homogênea (dados do mesmo tipo)
	- Ordenada (elementos acessados por meio de posições/índices)
	- Alocadas de uma vez só, em um bloco contíguo de memória
- *Vantagens*
	- Acesso imediato aos elementos pela sua posição
- *Desvantagens*
	- Tamanho fixo
	- Dificuldade para se realizar inserções e deleções
	
![[myVect.jpg]]

para declararmos um #vetor, utilizamos essa sintaxe:
```java
tipoPrimitivo[] nomeDoVetor = new tipoPrimitivo [tamanhoDoVetor]
```
*Exemplo:*
```java
double[] vect = new double [n];
```


#### *Problema exemplo 1*
Fazer um programa para ler um número inteiro N e a altura de N pessoas. Armazene as N alturas em um vetor. Em seguida mostrar a altura média dessas pessoas

```java
int n = sc.nextInt();  
double[] vect = new double [n];  
for (int i=0; i<n; i++){  
    vect[i] = sc.nextDouble();  
}  
  
double sum = 0.0;  
for (int i=0;i<n;i++){  
    sum += vect[i];  
}  
double avg = sum / n;
```

### *Explicação Detalhada*

#### 1. Leitura e Armazenamento dos Valores

```java
`int n = sc.nextInt(); 
double[] vect = new double[n]; 
for (int i = 0; i < n; i++) {     
	vect[i] = sc.nextDouble(); 
}`
```
- Este trecho é igual ao que discutimos anteriormente. Ele lê um número inteiro `n` e cria um array `vect` de `double` com `n` elementos. Depois, preenche esse array com `n` valores `double` inseridos pelo usuário.

#### 2. Cálculo da Soma dos Valores

```java
double sum = 0.0; for (int i = 0; i < n; i++) {     
	sum += vect[i]; 
}
```
- **`double sum = 0.0;`**: Declara uma variável `sum` do tipo `double` e a inicializa com `0.0`. Esta variável será usada para armazenar a soma dos valores do array.
- **`for (int i = 0; i < n; i++)`**: Um laço `for` que itera sobre cada índice do array `vect`, de `0` até `n-1`.
- **`sum += vect[i];`**: Adiciona o valor do elemento `vect[i]` à variável `sum` em cada iteração do laço. Assim, após o término do laço, `sum` conterá a soma de todos os valores armazenados no array `vect`.

#### 3. Cálculo da Média

```java
double avg = sum / n;
```
- **`double avg`**: Declara uma variável `avg` do tipo `double`.
- **`sum / n`**: Divide a soma total dos valores (`sum`) pelo número de elementos (`n`) para calcular a média dos valores.
- **`avg`**: Armazena o resultado dessa divisão, que é a média dos valores armazenados no array `vect`.

### Resumo do Funcionamento

1. **Leitura e Armazenamento**: O código lê `n` valores `double` inseridos pelo usuário e armazena esses valores em um array `vect` de tamanho `n`.
2. **Soma**: O código calcula a soma de todos os valores no array `vect` e armazena o resultado na variável `sum`.
3. **Média**: O código calcula a média dos valores dividindo a soma (`sum`) pelo número total de valores (`n`) e armazena esse valor na variável `avg`.

---
---
# *Aula90 - #Vetores parte 2/2*

#### *Problema exemplo 2:*
Fazer um programa para ler um número inteiro N e os dados (nome e preço) de N produtos. Armazene os N produtos em um vetor. Em seguida, mostrar o preço médio dos produtos

*Exemplo:

| Input: |        Output:         |
|:------:|:----------------------:|
|   3    | AVERAGE PRICE = 700.00 |
|   TV   |                        |
| 900.00 |                        |
| Fryer  |                        |
| 400.00 |                        |
| Stove  |                        |
| 800.00 |                        |

### *Código:*
```java
int n = sc.nextInt();  
Product[] vect = new Product[n];  
  
for (int i=0; i<n; i++){  
    sc.nextLine();  
    String name = sc.nextLine();  
    double price = sc.nextDouble();  
    vect[i] = new Product(name, price);  
}  
double sum = 0.0;  
for (int i=0;i<n;i++){  
    sum += vect[i].getPrice();  
}  
double avg = sum / n;  
System.out.printf("AVERAGE PRICE = %.2f", avg);
```


### Explicação Detalhada

#### 1. Leitura do Número de Produtos

```java
int n = sc.nextInt();`
```
- **`int n`**: Declara uma variável `n` do tipo `int`, que armazena o número de produtos que o usuário deseja cadastrar.
- **`sc.nextInt()`**: Usa o objeto `sc` (presumidamente um `Scanner`) para ler um valor inteiro que representa a quantidade de produtos.

#### 2. Criação de um Array de Produtos
```java
Product[] vect = new Product[n];`
```
- **`Product[] vect`**: Declara um array chamado `vect` que armazenará objetos do tipo `Product`. O tamanho desse array é determinado pelo valor de `n`, que foi lido anteriormente.
- **`new Product[n]`**: Inicializa o array de `Product` com `n` posições, ou seja, será possível armazenar até `n` produtos.

#### 3. Leitura dos Dados de Cada Produto

```java
for (int i = 0; i < n; i++) {     
	sc.nextLine();     
	String name = sc.nextLine();     
	double price = sc.nextDouble();     
	vect[i] = new Product(name, price); 
}`
```
- **`for (int i = 0; i < n; i++)`**: Um laço `for` que itera de `0` até `n-1`, permitindo que sejam lidos e armazenados os dados de cada produto.
- **`sc.nextLine();`**: Lê a linha de entrada para consumir a quebra de linha que pode ter sido deixada pela leitura anterior (usada aqui para evitar problemas com a leitura do `String`).
- **`String name = sc.nextLine();`**: Lê o nome do produto como uma `String`, usando o método `nextLine()` do objeto `Scanner`.
- **`double price = sc.nextDouble();`**: Lê o preço do produto como um `double`.
- **`vect[i] = new Product(name, price);`**: Cria um novo objeto `Product` passando o nome e o preço como parâmetros para o construtor e o armazena na posição `i` do array `vect`.

#### 4. Cálculo da Soma dos Preços
```java
double sum = 0.0; 
for (int i = 0; i < n; i++) {     
	sum += vect[i].getPrice(); 
}`
```
- **`double sum = 0.0;`**: Declara uma variável `sum` do tipo `double` e a inicializa com `0.0`. Essa variável será usada para armazenar a soma dos preços de todos os produtos.
- **`for (int i = 0; i < n; i++)`**: Um laço `for` que percorre o array de produtos.
- **`sum += vect[i].getPrice();`**: Adiciona o preço do produto armazenado na posição `i` do array ao valor de `sum`. O método `getPrice()` deve ser um método da classe `Product` que retorna o preço de um produto.

#### 5. Cálculo da Média dos Preços

```java
double avg = sum / n;`
```
- **`double avg = sum / n;`**: Calcula a média dos preços dividindo a soma total (`sum`) pelo número de produtos (`n`). O resultado é armazenado na variável `avg`.

#### 6. Exibição da Média

```java
System.out.printf("AVERAGE PRICE = %.2f", avg);`
```
- **`System.out.printf()`**: Usa o método `printf` para formatar e imprimir a média dos preços com duas casas decimais (`%.2f`), seguido pela mensagem `"AVERAGE PRICE = "`.

### Resumo do Funcionamento

1. O código lê um número `n` que representa a quantidade de produtos a serem cadastrados.
2. Ele cria um array de objetos `Product` de tamanho `n`.
3. O laço `for` lê os dados de cada produto (nome e preço) e os armazena no array.
4. Outro laço calcula a soma dos preços de todos os produtos.
5. A média dos preços é calculada dividindo a soma pelo número de produtos.
6. A média é exibida com duas casas decimais.

---
---

### Método #lenght 

### O que é  #length?

A propriedade **`length`** em Java é utilizada para obter o tamanho de arrays. No caso do código, `vect.length` retorna o número de elementos do array `vect`, que foi declarado anteriormente como sendo do tipo `Product[]` (um array de objetos da classe `Product`).

Em outras palavras, **`length`** nos dá a quantidade de posições ou elementos que o array pode armazenar, ou seja, o número total de produtos.

Agora, vamos analisar o papel de `length` em cada trecho do código:

### 1. Uso de `vect.length` no Laço `for` de Leitura de Produtos


```java
for (int i = 0; i < vect.length; i++) {     
	sc.nextLine();     
	String name = sc.nextLine();     
	double price = sc.nextDouble();     
	vect[i] = new Product(name, price); 
}`
```
- **`vect.length`** aqui está sendo utilizado para garantir que o laço `for` itere exatamente **n** vezes, onde **n** é o tamanho do array `vect`. Esse valor foi definido quando o array foi criado, possivelmente com base na entrada do usuário.
- **`for (int i = 0; i < vect.length; i++)`**: Isso significa que o laço começa em `i = 0` e vai até `i = vect.length - 1`, assegurando que cada posição do array será acessada e preenchida com um objeto `Product`.
- **Por que usar `length`?**: Isso é útil para fazer o laço percorrer todo o array, independentemente do tamanho exato do array. Isso torna o código flexível e adaptável, pois `length` automaticamente se ajusta ao tamanho do array.

### 2. Uso de `vect.length` no Laço `for` para Cálculo da Soma dos Preços

```java
double sum = 0.0; 
for (int i = 0; i < vect.length; i++) {     
	sum += vect[i].getPrice(); 
}`
```
- Aqui, o código novamente usa `vect.length` para garantir que todos os elementos do array sejam percorridos. Em cada iteração do laço, o preço de cada produto armazenado no array é somado à variável `sum`.
- **`for (int i = 0; i < vect.length; i++)`**: Garante que o laço percorra o array inteiro para somar o preço de todos os produtos.

### 3. Uso de `vect.length` no Cálculo da Média dos Preços

```java
double avg = sum / vect.length;`
```
- **`vect.length`** é utilizado para calcular a média dos preços. Após somar todos os preços na variável `sum`, o código divide essa soma pelo número de elementos no array, ou seja, o número de produtos.
- **Por que usar `vect.length` aqui?**: Isso garante que a média seja calculada corretamente, independentemente do tamanho do array. Se o número de produtos for 5, `vect.length` será 5, e a soma será dividida por 5, o que resultará na média correta.

### Resumo da Função de `length`

1. **`vect.length` no laço `for`**: Controla o número de iterações do laço, garantindo que o laço percorra todas as posições do array.
2. **`vect.length` no cálculo da média**: Determina o divisor correto para calcular a média dos preços, ajustando-se ao número de elementos do array.

### Vantagem de Usar `length`

- **Automatiza o tamanho do array**: Não importa quantos elementos o array `vect` tem, `length` sempre fornecerá o tamanho correto, eliminando a necessidade de controles manuais no código.
- **Flexibilidade**: Se o tamanho do array mudar (por exemplo, se o número de produtos variar), o código funcionará corretamente, pois `length` se ajustará ao novo tamanho do array.