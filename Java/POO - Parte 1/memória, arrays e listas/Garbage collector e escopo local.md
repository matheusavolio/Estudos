# Aula88 - Desalocação de memória - garbage collector e escopo local

#### #GarbageCollector

- É um processo que automatiza o gerenciamento de memória de um programa em execução
- O garbage collector monitora os objetos alocados dinamicamente pelo programa (no #heap), desalocando aqueles que não estão sendo utilizados .

![[garbageCollector.jpg]]


### Desalocação por escopo
```java
void method1 (){
	int x = 10;
	if (x > 0){
		int y = 20;
		}
	System.out.println(x)
}
```
- Quando o método `method1()` é executado, ele utiliza a **área de memória Stack**, que é onde ficam armazenadas as variáveis locais e os escopos.

1. **Variável `x` no Escopo do Método**:
    
    - Ao iniciar a execução do método, a variável `x` é declarada com o valor `10`.
    - Nesse momento, a variável `x` é armazenada na **Stack** dentro do escopo principal do método `method1()`.
    - A variável `x` estará disponível em todo o método, até que ele termine sua execução.
2. **Variável `y` no Escopo do `if`**:
    
    - Em seguida, o programa entra no bloco `if`, onde a variável `y` é declarada com o valor `20`.
    - A variável `y` é armazenada na **Stack**, mas dentro de um escopo menor, que é o bloco do `if`. Isso significa que `y` só existe **enquanto o bloco `if` estiver sendo executado**.
    - Quando o bloco `if` termina (ou seja, ao sair das chaves `{}`), o escopo de `y` deixa de existir e a variável `y` é removida da memória.
3. **Após o `if`**:
    
    - Após a execução do bloco `if`, a variável `y` não existe mais, pois seu escopo terminou. No entanto, a variável `x` continua existindo no escopo do método.
    - Quando o `System.out.println(x)` é executado, o valor de `x` (10) é impresso, pois `x` ainda está disponível no escopo do método.
### Resumo:

- A **variável `x`** está no escopo do método e existe durante toda a execução de `method1()`.
- A **variável `y`** está no escopo do bloco `if`, e só existe enquanto o bloco `if` está sendo processado.
- Após o bloco `if`, a variável `y` deixa de existir, mas a variável `x` ainda pode ser usada, pois ela faz parte do escopo mais abrangente do método.

![[desalocaçãoEscopo.jpg]]


#### Outro exemplo: 
![[desalocçãoEscopo2.jpg]]

### Explicação Baseada na Imagem:

1. **Método `method1()`**:
    
    - No método `method1()`, uma variável `p` do tipo `Product` é criada e recebe o valor retornado pelo método `method2()`.
    - Esse valor é um objeto `Product` criado dentro do método `method2()`, como veremos mais adiante.
    - Após a criação do objeto, o valor do atributo `Name` do objeto `p` é impresso.
2. **Método `method2()`**:
    
    - O método `method2()` cria uma nova instância de `Product` utilizando o comando `new Product("TV", 900.0, 0)`. Esse comando aloca o objeto na **Heap**, que é a área da memória destinada a objetos criados dinamicamente.
    - A variável `prod`, que é uma referência ao objeto, é criada na **Stack** dentro do escopo do método `method2()`.
    - Após a criação do objeto, a referência `prod` é retornada para o método `method1()`.
3. **Alocação de Memória**:
    
    - Na **Stack**:
        - A variável `p` em `method1()` é uma referência ao objeto `Product`.
        - A variável `prod`, que aponta para o mesmo objeto, é criada dentro do escopo de `method2()`. Quando `method2()` finaliza, o espaço de `prod` na **Stack** é desalocado, mas a referência do objeto é passada para `p`.
    - Na **Heap**:
        - O objeto `Product` com os valores "TV", `900.0`, e `0` (nome, preço e quantidade, respectivamente) é criado e permanece na **Heap** até que o garbage collector remova-o.

### Fluxo da Execução:

1. O método `method1()` chama `method2()`.
2. Dentro de `method2()`, o objeto `Product` é alocado na **Heap** e a variável `prod` aponta para ele.
3. Quando `method2()` retorna, a referência ao objeto é passada para a variável `p` de `method1()`.
4. O método `method1()` imprime o valor do atributo `Name` do objeto, que é "TV".

### Conclusão:

- As variáveis de referência como `p` e `prod` estão na **Stack**, mas o objeto propriamente dito (com seus atributos) está na **Heap**.
- Após o término de `method2()`, a variável `prod` é removida da **Stack**, mas o objeto ainda existe na **Heap** porque a referência `p` continua ativa.


### Resumo Aula88
- Objetos alocados dinamicamente, quando não possuem mais referência para eles, serão desalocados pelo garbage collector
- Variáveis locais são desalocadas imediatamente assim que seu escopo local sai de execução