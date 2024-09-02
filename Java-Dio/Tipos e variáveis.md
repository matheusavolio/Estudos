# Tipos e Variáveis

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/variaveis.md#tipos-e-vari%C3%A1veis)

## Tipos de dados

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/variaveis.md#tipos-de-dados)

No Java, existem algumas palavras reservadas para a representação dos tipos de dados básicos que precisam ser manipulados para a construção de programas. Estes tipos de dados são conhecidos como tipos primitivos (Primitive Types).

{% hint style="info" %} Os oito tipos primitivos em Java são:

int, byte, short, long, float, double, boolean e char – esses tipos não são considerados objetos, e portanto representam valores brutos. Eles são armazenados diretamente na pilha de memória. (Memory stack) {% endhint %}

Tabela de Tipos Primitivos e seus valores:

|Tipo|Memória|Valor Mínimo|Valor Máximo|
|---|---|---|---|
|byte|1 byte|-128|127|
|short|2 byte|-32.768|32.767|
|int|4 bytes|-2.147.483.648|2.147.483.647|
|long|8 bytes|-9.223.372.036.854.775.808|9.223.372.036.854.775.807|

Os tipos primitivos que podem conter partes fracionárias podem ser representados por dois tipos:

|Tipo|Memória|Mínimo|Máximo|Precisão|
|---|---|---|---|---|
|float|4 bytes|-3,4028E + 38|3,4028E + 38|6 – 7 dígitos|
|double|8 bytes|-1,7976E + 308|1,7976E + 308|15 dígitos|

Apesar de o tipo **float** ocupar metade da memória consumida do que um tipo double, ele é menos utilizado. Ele sofre de uma limitação que compromete seu uso em determinadas situações: somente mantém uma precisão decimal entre 6 e 7 dígitos.

Atualmente, com os computadores modernos, se tornou desnecessário utilizar os tipos `short` e `byte`, pois não precisamos nos preocupar tanto assim com o espaço de memória reduzido.

Da mesma forma, dificilmente utilizaremos o tipo `long`, pois não é tão comum trabalharmos com valores tão grandes.

Portanto, para representar números, na grande maioria das vezes utilizaremos o tipo `int` para representar números inteiros ou `double` para representar números fracionados.

{% hint style="info" %} _O ponto mais relevante em compreender a definição dos tipos de dados é o momento da definição do tipo para uma variável. **Qual tipo de dados eu utilizaria para determinar a idade de uma pessoa ou o salário de um funcionário?**_

{% endhint %}

[![Tabela criada pela minha aluna Priscilla Aniboleti - Github - Pripii](https://github.com/digitalinnovationone/trilha-java-basico/raw/main/gitbook/.gitbook/assets/image%20(10).png)](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/.gitbook/assets/image%20(10).png)

## Declaração de Variáveis

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/variaveis.md#declara%C3%A7%C3%A3o-de-vari%C3%A1veis)

Variável é uma identificação de um espaço em memória utilizado pelo nosso programa. Seguindo as convenções em linguagem de programação, toda variável é composta por: tipo de dados + identificação + valor atribuído.

A estrutura padrão para se declarar uma variável sempre é:

`<Tipo> <nomeVariavel> <atribuicaoDeValorOpcional>`

Exemplos abaixo:

```java
int idade; //Tipo "int", nome "idade", com nenhum valor atribuído. 
int anoFabricacao = 2021; //tipo "int", nome "anoFabricacao", com valor 2021.
double salarioMinimo = 2.500; //tipo "double", nome "salarioMinimo", valor 2.500.
```

Atenção: existe algumas peculiaridades a trabalhar com alguns tipos específicos. Observe no exemplo abaixo:

```java
public class TipoDados {
	public static void main(String[] args) {
		byte idade = 123;
		short ano = 2021;
		int cep = 21070333; // se começar com zero, talvez tenha que ser outro tipo
		long cpf = 98765432109L; // se começar com zero, talvez tenha que ser outro tipo
		float pi = 3.14F;
		double salario = 1275.33;
	}
}
```

{% hint style="warning" %} Observe que o tipo long precisa terminar com L, o tipo float precisa terminar com F e alguns cenários do dia-a-dia podem estimular uma alteração de tipos de dados convencional. {% endhint %}

Muitas das vezes criamos uma variável, definimos um valor correspondente, manipulamos esta variável e temos consciência de seu valor na aplicação. Mas cuidado !!

{% hint style="warning" %} Java é fortemente "tipado" {% endhint %}

Veja o cenário abaixo:

```java
// TiposEVariaveis.java

short numeroCurto = 1;
int numeroNormal = numeroCurto;
short numeroCurto2 = numeroNormal;
```

{% hint style="info" %} Por mais que temos ciência que valor de `numeroNormal` cabe é um short, o **Java** não permite correr o risco. {% endhint %}

## Variáveis e Constantes

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/variaveis.md#vari%C3%A1veis-e-constantes)

Uma **variável** é uma área de memória, associada a um nome, que pode armazenar valores de um determinado tipo. Um tipo de dado define um conjunto de valores e um conjunto de operações. **Java** é uma linguagem com rigidez de tipos, diferente de linguagens como JavaScript, onde declarar o tipo da variável não é obrigatório.

No Java utilizamos identificadores que representam uma referência (ponteiro) a um valor em memória, e esta referência pode ser redirecionada a outro valor, sendo portanto esta a causa do nome "variável", pois o valor pode variar.

Já as **Constantes** são valores armazenados em memória que não podem ser modificados depois de declarados. Em Java, esses valores são representados pela palavra reservada `final`, seguida do tipo.

Por convenção, **Constantes** são sempre escritas em CAIXA ALTA.

Abaixo temos um exemplo explicativo sobre uso de variáveis e constantes:

```java
public class ExemploVariavel {
	public static void main(String[] args) {
		/*
		 * esta linha é considerada como declaração de variável iniciamos a existência
		 * variavel numero com valor 5 regra: tipo + nome + valor
		 */
		int numero = 5;

		/*
		 * na linha abaixo iremos alterar o valor do varíavel para 10 observe que o tipo
		 * não é mais necessário, pois a variável já foi declarada anteriormente
		 */
		numero = 10;

		System.out.print(numero);
		
		/*
		 * ao usar a palavra reservada final, você determina que jamais
		 * esta variavel poderá obter outro valor;
		 * logo a linha 25 vai apresentar um erro de compilação
		 * isso é considerado uma CONSTANTE na linguagem Java
		 */
		final double VALOR_DE_PI = 3.14;
		
		VALOR_DE_PI=3.15; //Esta linha vai apresentar erro de compilação!
	}
}
```

{% hint style="warning" %} Compreendemos que para declarar uma variável como uma constante, utilizamos a palavra `final`, mas por convenção, esta variável deverá ser escrita toda em caixa alta. {% endhint %}


### 1. **`byte`**

- **Tamanho**: 8 bits (1 byte)
- **Valor Mínimo**: -128
- **Valor Máximo**: 127
- **Uso**: Para economizar memória em grandes arrays onde os valores estão dentro do intervalo.
- **Exemplo**:
    
    
    `byte idade = 25;`
    

### 2. **`short`**

- **Tamanho**: 16 bits (2 bytes)
- **Valor Mínimo**: -32,768
- **Valor Máximo**: 32,767
- **Uso**: Similar ao `byte`, mas com um intervalo maior.
- **Exemplo**:
    
    
    `short ano = 2024;`
    

### 3. **`int`**

- **Tamanho**: 32 bits (4 bytes)
- **Valor Mínimo**: -2³¹
- **Valor Máximo**: 2³¹ - 1
- **Uso**: O tipo inteiro mais comum para números.
- **Exemplo**:
    
    
    `int populacao = 1000000;`
    

### 4. **`long`**

- **Tamanho**: 64 bits (8 bytes)
- **Valor Mínimo**: -2⁶³
- **Valor Máximo**: 2⁶³ - 1
- **Uso**: Para valores inteiros muito grandes.
- **Exemplo**:
    
    
    `long distanciaEstrelas = 9460730472580800L;  // O 'L' indica que é um long`
    

### 5. **`float`**

- **Tamanho**: 32 bits (4 bytes)
- **Precisão**: Aproximadamente 7 dígitos decimais
- **Uso**: Para números de ponto flutuante (decimais) com menor precisão.
- **Exemplo**:
    
    
    `float temperatura = 36.6f;  // O 'f' indica que é um float`
    

### 6. **`double`**

- **Tamanho**: 64 bits (8 bytes)
- **Precisão**: Aproximadamente 15 dígitos decimais
- **Uso**: Para números de ponto flutuante com maior precisão, é o tipo padrão para números decimais.
- **Exemplo**:
    
    
    `double peso = 70.5;`
    

### 7. **`boolean`**

- **Tamanho**: 1 bit (teoricamente, mas depende da JVM)
- **Valores Possíveis**: `true` ou `false`
- **Uso**: Para valores binários ou lógicos (verdadeiro/falso).
- **Exemplo**:
    
    
    `boolean ativo = true;`
    

### 8. **`char`**

- **Tamanho**: 16 bits (2 bytes)
- **Valor Mínimo**: '\u0000' (ou 0)
- **Valor Máximo**: '\uffff' (ou 65,535)
- **Uso**: Para representar um único caractere Unicode.
- **Exemplo**:
    
    
    `char inicial = 'M';`
    

### Resumo

Esses tipos primitivos são a base para operações simples e desempenham um papel fundamental na manipulação de dados em Java, oferecendo eficiência e controle sobre a memória.



A classe `String` em Java é uma das classes mais fundamentais e amplamente utilizadas. Diferente dos tipos primitivos, `String` é uma classe, o que significa que as strings em Java são objetos. Aqui estão alguns pontos importantes sobre a classe `String`:

### 1. **Imutabilidade**

- Uma das características mais importantes de uma `String` em Java é que ela é **imutável**. Isso significa que, uma vez criada, a string não pode ser alterada. Qualquer operação que pareça modificar uma string na verdade cria uma nova string.
- **Exemplo**:
    
    
	`String saudacao = "Olá"; saudacao = saudacao + " Mundo!"; // Agora, "saudacao" referencia uma nova string "Olá Mundo!".`
    

### 2. **Criação de Strings**

- As strings podem ser criadas de várias maneiras:
    - **Literal**: Strings criadas com aspas duplas são armazenadas no **pool de strings**.
    - **Construtor**: Pode-se usar o construtor `new String()` para criar uma nova instância.
- **Exemplo**:
    
    
    `String nome = "Matheus";  // Criado no pool de strings 
    `String sobrenome = new String("Avolio");  // Criado como uma nova instância`
    

### 3. **Concatenação**

- Strings podem ser concatenadas usando o operador `+` ou o método `concat()`.
- **Exemplo**:
    
    
    `String nomeCompleto = nome + " " + sobrenome;`
    

### 4. **Métodos Comuns**

- A classe `String` fornece muitos métodos úteis para manipular e consultar strings. Alguns dos mais comuns incluem:
    - **`length()`**: Retorna o comprimento da string.
    - **`charAt(int index)`**: Retorna o caractere na posição especificada.
    - **`substring(int beginIndex, int endIndex)`**: Retorna uma parte da string.
    - **`toUpperCase()` e `toLowerCase()`**: Converte a string para maiúsculas ou minúsculas.
    - **`trim()`**: Remove espaços em branco no início e no fim da string.
    - **`replace(CharSequence old, CharSequence new)`**: Substitui todas as ocorrências de um caractere ou sequência de caracteres por outro.
    - **`contains(CharSequence s)`**: Verifica se a string contém uma sequência específica de caracteres.
    - **`split(String regex)`**: Divide a string em um array de strings com base em um delimitador.
- **Exemplo**:
    
    
    `String frase = " Aprender Java "; 
    `String novaFrase = frase.trim().toUpperCase().replace("JAVA", "Programação"); // novaFrase agora é "APRENDER PROGRAMAÇÃO"`
    

### 5. **Comparação de Strings**

- Strings podem ser comparadas usando:
    - **`equals(Object another)`**: Verifica se duas strings são iguais em conteúdo.
    - **`equalsIgnoreCase(String another)`**: Compara strings ignorando maiúsculas e minúsculas.
    - **`compareTo(String another)`**: Compara lexicograficamente, retornando um valor negativo, zero ou positivo.
- **Exemplo**:
    
    
    `String s1 = "java"; 
    `String s2 = "Java"; 
    `boolean iguais = s1.equals(s2);  
    `// false
    `boolean iguaisIgnorandoCase = s1.equalsIgnoreCase(s2);  
    `// true`
    

### 6. **Performance e Pool de Strings**

- Quando uma string é criada usando literais (por exemplo, `String s = "Hello";`), ela é armazenada no **pool de strings**, que é uma área especial da memória onde strings idênticas são armazenadas para reutilização. Isso melhora a performance e economiza memória.
- Strings criadas com `new String("Hello")` não entram no pool imediatamente e são armazenadas no heap como objetos distintos.

### 7. **Segurança**

- A imutabilidade das strings também as torna seguras para uso em ambientes de multi-threading, já que múltiplas threads podem acessar uma string sem risco de alteração de seu valor.

### Resumo

A classe `String` em Java é fundamental para manipulação de texto, fornecendo uma vasta gama de métodos para operações comuns. Sua imutabilidade oferece vantagens em termos de segurança e performance, enquanto a facilidade de uso faz dela uma das classes mais utilizadas na linguagem.