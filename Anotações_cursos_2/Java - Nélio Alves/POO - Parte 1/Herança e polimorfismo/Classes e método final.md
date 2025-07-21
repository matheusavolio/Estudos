## Aula133 - Classes e método #final 

- Palavra chave: *final*
- *Classe: evita que a classe seja herdada*
	- ![[Método final.jpg]]
	- `public final class classe`
- *Método: evita que o método sob seja sobreposto*
	- ![[MétodoFinal.jpg]]
	- `public final void withDraw(double amount)


### Porquê usar a palavra #final?
- *Segurança:*
	- Dependendo das regras do negócio, ás vezes é desejável garantir que uma classe não seja herdada, ou que um método não seja sobreposto
		- Geralmente convém acrescentar `final` em métodos sobrepostos, pois sobreposições múltiplas podem ser uma porta de entrada para inconsistências 
- *Performance:*
	- Atributos de tipo de uma classe final são analisados de forma mais rápida em tempo de execução
		- Exemplo clássico: `String`

