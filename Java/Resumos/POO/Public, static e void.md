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
