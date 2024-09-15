### #public, #static e #void na Criação de #Métodos

Quando criamos métodos em linguagens como Java, usamos palavras-chave que definem **como** e **onde** o método pode ser usado. Vamos entender o que significam `public`, `static` e `void`:

|**public**|**static**|**void**|
|---|---|---|
|Define que o método pode ser acessado por outras classes. Isso significa que, se um método for declarado como `public`, ele poderá ser chamado de qualquer outra parte do programa, desde que a classe que o contém seja acessível.|Permite que o método seja chamado **sem a necessidade de criar um objeto** da classe. Métodos `static` pertencem à classe em si, e não a instâncias (objetos) da classe. Isso é útil para funções auxiliares ou utilitárias, como `Math.sqrt()`.|Indica que o método **não retorna nenhum valor**. Em vez de retornar algo, ele executa uma ação e termina. Por exemplo, um método `void` pode exibir uma mensagem ou alterar o estado de um objeto, mas não dará uma resposta direta.|

### Exemplo Prático

```java
`public class Calculadora {          
	// Método estático que não retorna valor     
	public static void exibirMensagem() {         
		System.out.println("Bem-vindo à Calculadora!");     
	}          
	
	// Método público e estático que retorna um valor     
	public static int somar(int a, int b) {         
		return a + b;     
		} 
	}`
```
- **`public`**: O método `somar()` pode ser acessado por qualquer outra classe.
- **`static`**: Ambos os métodos `exibirMensagem()` e `somar()` podem ser chamados diretamente, sem a necessidade de criar um objeto da classe `Calculadora`.
- **`void`**: O método `exibirMensagem()` não retorna nenhum valor, apenas exibe uma mensagem.

---
---
## #MembrosEstáticos 

### Membros Estáticos de uma Classe

Uma classe possui **membros**, que podem ser **atributos** e **métodos**. Quando esses membros são **estáticos**, seu comportamento é um pouco diferente.

#### O que são Membros Estáticos?

Os **membros estáticos**, também chamados de **membros de classe**, são aqueles que pertencem à **classe em si**, e não a um objeto específico da classe. Isso significa que eles podem ser acessados **diretamente pelo nome da classe**, sem a necessidade de criar uma instância (objeto).

- **Membros de Instância**: São os membros comuns de uma classe, que precisam de um objeto para serem acessados.
- **Membros Estáticos**: Não precisam de um objeto para serem chamados e podem ser usados diretamente pela classe.

#### Aplicações Comuns dos Membros Estáticos:

- **Classes Utilitárias**: Como a classe `Math` em Java, que possui métodos como `Math.sqrt()` para calcular raízes quadradas. Esses métodos são chamados diretamente a partir do nome da classe.
- **Declaração de Constantes**: Atributos que representam constantes (valores que não mudam) geralmente são declarados como estáticos, pois esses valores são iguais para todos os objetos da classe.

#### Classes Estáticas:

Se uma classe tem **apenas membros estáticos**, ela pode ser declarada como uma **classe estática**. Isso significa que a classe não poderá ser instanciada, ou seja, **não será possível criar objetos dela**. Exemplos comuns são classes utilitárias que apenas agrupam métodos e constantes que não dependem de estado.

---
---

## #final 

### O que é a Palavra-chave `final`?

A palavra-chave **`final`** em Java é usada para declarar **constantes**, ou seja, variáveis cujo valor **não pode ser alterado** após ser definido. Quando um membro da classe é declarado como `final`, ele deve ser inicializado no momento da sua criação, e seu valor permanecerá o mesmo durante toda a execução do programa.

#### Uso do `final` em Membros Estáticos

Quando combinamos `final` com membros **estáticos**, estamos criando **constantes globais** que pertencem à classe e não podem ser modificadas. Isso é muito útil para valores fixos, como taxas, constantes matemáticas, ou limites que nunca mudam.

#### Convenção de Nomenclatura

Ao declarar uma constante, a convenção em Java é usar letras **maiúsculas** (upper case) para o nome, separando palavras com **underscore** (`_`). Isso ajuda a identificar rapidamente que o valor é uma constante. Exemplos:


```java
public static final double PI = 3.14159; 
public static final double NET_SALARY = 4500.00; 
public static final int MEDIA_STUDENT = 70;`
```
#### Regras para Classes Estáticas

Em uma **classe estática**, que contém apenas membros estáticos, você **não pode chamar métodos que não sejam estáticos**. Isso porque métodos não estáticos dependem de instâncias (objetos), e uma classe estática não permite a criação de objetos.

