
# Anatomia das classes
A escrita de códigos de um programa é feito através da composição de palavras pré-definidas pela linguagem com as expressões que utilizamos para determinar o nome do nossos arquivos, classes, atributos e métodos.

É muito comum mesclarmos expressões no idioma americano com o nosso vocabulário. Existem projetos que recomendam que toda a implementação do seu programa seja escrita na língua inglesa.

**Sintaxe de declaração de uma nova classe:**

![[Pasted image 20240820001556.png]]
- 99,9% das nossas classes iniciarão com `public class;`
- Toda classe precisa de nome, exemplo `MinhaClasse;`
- O nome do arquivo deve ser idêntico ao nome da classe pública;
- Após o nome, definir o corpo `{ }` , onde iremos compor nossas classes com atributos e métodos.

se minha classe for uma classe executável, ela precisa ter um método especial,um método principal, e esse método se chama main, e ele precisa seguir um padrão, e esse padrão é `public static void main` e ele espera dentro de um parâmetro especial: `public static void main (String [] args)` 
Tudo que está dentro de `()` é um método, e esse método vai ser executado

![[Pasted image 20240820001633.png]]

- É de suma importância que agora você consiga se localizar dentro do conjunto de chaves `{ }` existentes em sua classe.
- Dentro de uma aplicação, **recomenda-se que somente uma classe possua o método** `main`, responsável por iniciar todo o nosso programa.
- O método main recebe seu nome `main`, sempre terá a visibilidade `public`, será difinido como `static`, não retornará nenhum valor com `void` e receberá um parâmetro do tipo array de caracteres `String[]`.

## Padrão de nomenclatura

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#padr%C3%A3o-de-nomenclatura)

Quando se trata de escrever códigos na linguagem Java, é recomendado seguir algumas convenções de escrita. Esses padrões estão expressos nos itens abaixo:

- **Arquivo .java**: Todo arquivo .java deve começar com letra MAIÚSCULA. Se a palavra for composta, a segunda palavra deve também ser maiúscula, exemplo:
    
    `Calculadora.java`, `CalculadoraCientifica.java`
    
- **Nome da classe no arquivo**: A classe deve possuir o mesmo nome do arquivo.java, exemplo:
    

```java
// arquivo CalculadoraCientifica.java

public class CalculadoraCientifica {

}
```

- **Nome de variável**: toda variável deve ser escrita com letra minúscula, porém se a palavra for composta, a primeira letra da segunda palavra deverá ser MAIÚSCULA, exemplo: `ano` e `anoFabricacao`. O nome dessa prática para nomear variáveis dessa forma se chama "camelCase".

Existe uma regra adicional para variáveis quando na mesma queremos identificar que ela não sofrerá alteração de valor, exemplo: queremos determinar que uma variável de nome **br** sempre representará **"Brasil"** e nunca mudará seu valor, logo, determinamos como escrita o código abaixo: 

```java
String BR = "Brasil"
double PI = 3.14
int ESTADOS_BRASILEIRO = 27
int ANO_2000 = 2000
```

Recomendações: Para declarar uma variável nós podemos utilizar caracteres, números e símbolos, porém devemos seguir algumas regras da linguagem. {% endhint %}

- Deve conter apenas letras, _ (underline), $ ou os números de 0 a 9
- Deve obrigatoriamente se iniciar por uma letra (preferencialmente), _ ou $, jamais com número
- Deve iniciar com uma letra minúscula (boa prática – ver abaixo)
- Não pode conter espaços
- Não podemos usar palavras-chave da linguagem
- O nome deve ser único dentro de um escopo

```java
// Declação inválida de variáveis

int numero&um = 1; //Os únicos símbolos permitidos são _ e $
int 1numero = 1;    //Uma variável não pode começar com númerico
int numero um = 1; //Não pode ter espaço no nome da variável
int long = 1; //long faz parte das palavras reservadas da linguagem
 
 // Declaração válida de veriáveis
int numero$um = 1;
int numero1 = 1;
int numeroum = 1;
int longo = 1;
		
```

## Declarando variáveis e métodos

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#declarando-vari%C3%A1veis-e-m%C3%A9todos)

Como identificar entre declaração de variáveis e métodos em nossa programa? Existe uma estrutura comum para ambas as finalidades, exemplo:

- Declarar uma variável em Java segue sempre a seguinte estrutura:

```java
// Estrutura

Tipo NomeBemDefinido = Atribuição (opcional em alguns casos)

// Exemplo

int idade = 23;
double altura = 1.62;
Dog spike; //observe que aqui a variável spike não tem valor, é normal
```

- Declarando métodos em Java segue uma estrutura bem simples:

```java
// Estrutura

TipoRetorno NomeObjetivoNoInfinitivo Parametro(s)

//Exemplo

int somar (int numeroUm, int numero2)

String formatarCep (long cep)
```

Como parte da estrutura de declaração de variáveis e métodos também temos o aspecto da **visibilidade**, mas ainda não é necessário nesta etapa de estudos. {% endhint %}

## Identação

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#identa%C3%A7%C3%A3o)

Basicamente **indentar** é um termo utilizado para escrever o código do programa de forma hierárquica, facilitando assim a visualização e o entendimento do programa.

[![](https://github.com/digitalinnovationone/trilha-java-basico/raw/main/gitbook/.gitbook/assets/image%20(5)%20(1)%20(1)%20(1).png)](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/.gitbook/assets/image%20(5)%20(1)%20(1)%20(1).png)

Abaixo, veja um exemplo de um algoritmo de validação de aprovação de estudante. Em uma aba, temos um código sem identação nenhuma, e na outra aba, temos o mesmo código seguindo um padrão de identação. Observe como é muito mais fácil entender a hierarquia do código na segunda aba.

{% tabs %} {% tab title="Sem Identação" %}

```java
// arquivo BoletimEstudantil.java

public class BoletimEstudantil {
public static void main(String[] args) {
int mediaFinal = 6;
if(mediaFinal<6)	
System.out.println("REPROVADO"); 
else if(mediaFinal==6)
System.out.println("PROVA MINERVA"); 
else
System.out.println("APROVADO"); 		
}
}
```

{% endtab %}

{% tab title="Com Identação" %}

```java
public class BoletimEstudantil {
	public static void main(String[] args) {
		int mediaFinal = 6;
		if (mediaFinal < 6)
			System.out.println("REPROVADO");
		else if (mediaFinal == 6)
			System.out.println("PROVA MINERVA");
		else
			System.out.println("APROVADO");
	}
}
```

{% endtab %} {% endtabs %}

## Organizando arquivos

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#organizando-arquivos)

À medida que nosso sistema vai evoluindo, surgem novos arquivos (código fonte) em nossa estrutura de arquivos do projeto. Isso exige que seja realizado uma organização destes arquivos através de pacotes (packages).

[![Ilustração de uso de pacotes](https://github.com/digitalinnovationone/trilha-java-basico/raw/main/gitbook/.gitbook/assets/image%20(2).png)](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/.gitbook/assets/image%20(2).png)

Com o uso de pacotes as nossas classes (.java) passam a possuir duas identificações, o nome simples e nome qualificado:

- **Nome Simples**: Nome do arquivo, exemplo `ContaBanco`.
- **Nome Qualificado**: Nome do pacote + nome do arquivo, exemplo: `com.suaempresa.ContaBanco`.

## Java Beans

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#java-beans)

Umas das maiores dificuldades na programação é escrever algoritmos legíveis a níveis que sejam compreendidos por todo seu time ou por você mesmo no futuro. Para isso a linguagem Java sugere, através de convenções, formas de escrita universal para nossas classes, atributos, métodos e pacotes.

#### Variáveis

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#vari%C3%A1veis)

Mais cedo já aprendemos algumas regras de declaração de variáveis, mas agora iremos conhecer algumas sugestões de de nomenclatura:

- Uma variável deve ser clara, sem abreviações ou definição sem sentido;
- Uma variável é sempre no singular, **exceto quando se referir a um array ou coleção**.
- Defina um idioma único para suas variáveis. Se você for declarar variáveis em inglês, defina todas em inglês.

#### Não recomendado

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#n%C3%A3o-recomendado)

```java
double salMedio = 1500.23  //variável abreviada, o que dificulta a compreensão
String emails = "aluno@escola.com" //confuso se a variável seria um array ou único e-mail
String myName = "JOSEPH" //se idioma pt-BR, o valor poder ser de outro idioma mas o nome da variável não 
```

#### Recomendado

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#recomendado)

```java
double salarioMedio=1500.23;
String email ="aluno@escola.com";
String [] emails = {"aluno@escola.com","professor@escola.com"}
String meuNome = "JOSEPH" 
```

#### Métodos

[](https://github.com/digitalinnovationone/trilha-java-basico/blob/main/gitbook/sintaxe/anatomia-das-classes.md#m%C3%A9todos)

Os métodos deverão ser nomeados como verbos, através de uma mistura de letras minúsculas e maiúsculas. Em princípio todas as letras que compõem o nome devem ser mantidas em minúsculo, com exceção da primeira letra de cada palavra composta a partir da segunda palavra.

Exemplos sugeridos para nomenclatura de métodos:

```java
somar(int n1, int n2){}

abrirConexao(){}

concluirProcessamento() {}

findById(int id){} // não se assuste, você verá muito método em inglês em sua jornada

calcularImprimir(){} // há algo de errado neste método, ele deveria ter uma única finalidade
```


```java
public class MinhaClasse {    
    public static void main (String [] args) {
        String primeiroNome = "Matheus";
        String segundoNome = "Avolio";
        String nomeCompleto = nomeCompleto(primeiroNome, segundoNome);
        System.out.println(nomeCompleto);
}
public static String nomeCompleto(String primeiroNome, String segundoNome){
    return primeiroNome.concat(" ").concat(segundoNome);
}  
}
```
```java
OUTPUT
Matheus Avolio

ANÁLISE
Vou fazer a depuração e explicar o funcionamento do código linha por linha.



`public class MinhaClasse {`

1. **`public class MinhaClasse {`**:
    - Define uma classe pública chamada `MinhaClasse`. Em Java, toda aplicação é composta por classes, e o código deve estar dentro de uma classe.



`public static void main(String[] args) {`

2. **`public static void main(String[] args) {`**:
    - Declaração do método `main`, que é o ponto de entrada de um programa Java. Quando você executa um programa Java, o método `main` é o primeiro a ser chamado.
    - `public`: o método é acessível de qualquer lugar.
    - `static`: permite que o método seja chamado sem precisar criar uma instância da classe.
    - `void`: o método não retorna nenhum valor.
    - `String[] args`: um array de strings que permite passar argumentos para o programa via linha de comando.


`String primeiroNome = "Matheus";`

3. **`String primeiroNome = "Matheus";`**:
    - Declara uma variável `primeiroNome` do tipo `String` e atribui a ela o valor `"Matheus"`.
    - Em Java, uma `String` é uma sequência de caracteres.



`String segundoNome = "Avolio";`

4. **`String segundoNome = "Avolio";`**:
    - Declara uma variável `segundoNome` do tipo `String` e atribui a ela o valor `"Avolio"`.



`String nomeCompleto = nomeCompleto(primeiroNome, segundoNome);`

5. **`String nomeCompleto = nomeCompleto(primeiroNome, segundoNome);`**:
    - Chama o método `nomeCompleto` passando `primeiroNome` e `segundoNome` como argumentos.
    - O valor retornado por esse método (uma nova `String` combinando os nomes) é armazenado na variável `nomeCompleto`.



`System.out.println(nomeCompleto);`

6. **`System.out.println(nomeCompleto);`**:
    - Imprime o valor da variável `nomeCompleto` no console.
    - `System.out.println` é usado para exibir informações na tela.


`}`

7. **`}`**:
    - Fecha o método `main`.



`public static String nomeCompleto(String primeiroNome, String segundoNome){`

8. **`public static String nomeCompleto(String primeiroNome, String segundoNome){`**:
    - Declara um método chamado `nomeCompleto` que recebe dois parâmetros do tipo `String` (`primeiroNome` e `segundoNome`).
    - O método é `public`, ou seja, pode ser chamado de qualquer lugar.
    - `static` significa que o método pode ser chamado sem instanciar um objeto da classe.
    - O método retorna uma `String`.



`return primeiroNome.concat(" ").concat(segundoNome);`

9. **`return primeiroNome.concat(" ").concat(segundoNome);`**:
    - Retorna o resultado da concatenação de `primeiroNome`, um espaço (`" "`), e `segundoNome`.
    - O método `concat` é usado para unir duas strings.



`}`

10. **`}`**:
    - Fecha o método `nomeCompleto`.


`}`

11. **`}`**:
    - Fecha a classe `MinhaClasse`.

### Resumo do Funcionamento

O código define uma classe `MinhaClasse` com um método `main` que cria duas strings (`primeiroNome` e `segundoNome`), passa essas strings para um método `nomeCompleto` que as concatena, e então imprime o nome completo no console. No caso fornecido, a saída seria `Matheus Avolio`.
```
