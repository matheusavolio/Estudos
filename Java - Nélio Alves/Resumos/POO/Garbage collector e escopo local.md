## Garbage Collector

O **Garbage Collector** (GC) é um componente do Java responsável pela gestão automática da memória. Ele cuida da desalocação de objetos que não são mais utilizados, liberando espaço na memória heap. Aqui está uma explicação mais detalhada:

- **Função do Garbage Collector**: Automatiza a gestão da memória ao identificar e remover objetos que não têm mais referências válidas, evitando o uso excessivo de memória e prevenindo vazamentos de memória.
    
- **Memória Heap**: Área da memória onde os objetos são alocados dinamicamente. O Garbage Collector trabalha monitorando essa área para limpar objetos que não são mais necessários.
    
- **Funcionamento**: O GC faz uma varredura periódica para encontrar objetos que não são mais referenciados por nenhuma parte do programa. Esses objetos são então desalocados, liberando espaço para novos objetos.
    

![Garbage Collector](garbageCollector.jpg)

## Desalocação por Escopo

Em Java, a memória para variáveis locais é alocada na **Stack**. Quando o escopo de uma variável termina, ela é desalocada automaticamente. Vamos ver um exemplo prático:

```java

void method1() {     
	int x = 10;     
	if (x > 0) {         
		int y = 20;     
	}     
	System.out.println(x); 
}
		`
```
### Explicação do Exemplo:

1. **Variável `x` no Escopo do Método**:
    
    - Ao iniciar a execução do método `method1()`, a variável `x` é declarada e inicializada com o valor `10`.
    - A variável `x` é armazenada na **Stack** e está disponível durante toda a execução do método.
2. **Variável `y` no Escopo do `if`**:
    
    - Dentro do bloco `if`, a variável `y` é declarada e inicializada com o valor `20`.
    - A variável `y` também é armazenada na **Stack**, mas dentro do escopo limitado ao bloco `if`.
    - Quando o bloco `if` termina, a variável `y` deixa de existir e é removida da memória.
3. **Após o `if`**:
    
    - Após o término do bloco `if`, a variável `y` é desalocada, mas a variável `x` continua disponível no escopo do método.
    - O comando `System.out.println(x)` imprime o valor de `x`, que ainda é `10`.

### Outro Exemplo de Desalocação por Escopo

### Explicação Baseada na Imagem:

1. **Método `method1()`**:
    
    - No método `method1()`, uma variável `p` do tipo `Product` é criada e recebe a referência retornada pelo método `method2()`.
    - O método `method2()` cria um novo objeto `Product` e o aloca na **Heap**.
2. **Método `method2()`**:
    
    - O método `method2()` cria um novo objeto `Product` usando `new Product("TV", 900.0, 0)`. Este objeto é alocado na **Heap**.
    - A variável `prod`, que é uma referência ao objeto, é criada na **Stack** dentro do escopo de `method2()`.
    - Após a criação do objeto, a referência `prod` é retornada para o método `method1()`.
3. **Alocação de Memória**:
    
    - **Na Stack**:
        
        - A variável `p` em `method1()` passa a referenciar o objeto `Product`.
        - A variável `prod` em `method2()` aponta para o mesmo objeto. Quando `method2()` termina, `prod` é desalocada da **Stack**, mas o objeto ainda existe na **Heap**.
    - **Na Heap**:
        
        - O objeto `Product`, contendo os atributos "TV", `900.0` e `0`, permanece na **Heap** até que o Garbage Collector o remova, desde que a referência `p` em `method1()` ainda esteja ativa.

### Fluxo da Execução:

1. O método `method1()` chama `method2()`.
2. Dentro de `method2()`, um objeto `Product` é criado na **Heap** e a variável `prod` aponta para ele.
3. Quando `method2()` retorna, a referência ao objeto é passada para `p` em `method1()`.
4. O método `method1()` imprime o atributo `Name` do objeto, que é "TV".

### Conclusão:

- **Objetos Alocados Dinamicamente**: Permanecem na **Heap** até que não haja mais referências para eles. O Garbage Collector é responsável por desalocá-los.
- **Variáveis Locais**: São desalocadas da **Stack** assim que seu escopo local termina.