## Aula43 - Discussão inicial sobre exceções 

#### #Exceções

- Uma exceção é qualquer condição de erro ou comportamento inesperado encontrado por um *programa em execução*
- Em Java, uma exceção é um objeto herdado da classe:
	- `java.lang.Exception` - O compilador obriga a tratar ou propagar
	- `java.lang.RuntimeException` - O compilador não obriga a tratar ou propagar
- Quando lançada, uma exceção é propagada na pilha de chamadas de métodos em execução, até que seja capturada (tratada) ou o programa seja encerrado.

#### Hierarquia de exceções do Java
![[hierarquiaExceção.jpg]]

#### Por que exceções?
- O modelo de tratamento de exceções permite que erros sejam tratados de forma consistente e flexível, usando boas práticas
- Vantagens
	- Delega lógica do erro para a classe responsável por conhecer as regras que podem ocasionar o erro
	- Trata de forma organizada (inclusive hierárquica) exceções de tipos diferentes
	- A exceção pode carregar dados quaisquer


## Aula144 - Estrutura #try-cath 

- Bloco *try:*
	- Contém o código que representa a execução normal do trecho de código pode acarretar em uma execução 
- Bloco *catch:*
	- Contém o código a ser executado caso uma exceção ocorra
	- Deve ser especificado o tipo de exceção a ser tratada (upcasting é permitido)

##### Sintaxe: 
```java
try{
// código que pode gerar uma ou mais exceções 
}
catch (ExceptionType name) {
// lógica que executa caso a exceção seja ocorrida 
}
catch (ExceptionType name){

}
catch (ExceptionType name){

}
```

## Aula146 - Bloco #finally

- É um bloco que contém um código a ser executado independente de ter ocorrido ou não uma exceção
- Exemplo clássico: Fechar um arquivo, conexão de banco de dados, ou outro recurso específico ao final do processamento

#### Sintaxe:
```java
try{
// código que pode gerar uma exceção
}
catch (ExceptionType name){
// lógica que é executa caso ocorra uma exceção
}
finally{
// executa sempre ao final do programa, tendo sido gerada uma exceção ou não
}
```
