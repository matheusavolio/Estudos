
![[02-exercicios1-estrutura-sequencial (1).pdf]]


> [!Exercício 6 debug] 

```java
CÓDIGO
-------
		Locale.setDefault(Locale.US);
		Scanner sc = new Scanner(System.in);
		
		double A, B, C, triangulo, circulo, trapezio, quadrado, retangulo;
		
		A = sc.nextDouble();
		B = sc.nextDouble();
		C = sc.nextDouble();
		
		triangulo = A * C / 2.0;
		circulo = 3.14159 * C * C;
		trapezio = (A + B) / 2.0 * C;
		quadrado = B * B;
		retangulo = A * B;
		
		System.out.printf("TRIANGULO: %.3f%n", triangulo);
		System.out.printf("CIRCULO: %.3f%n", circulo);
		System.out.printf("TRAPEZIO: %.3f%n", trapezio);
		System.out.printf("QUADRADO: %.3f%n", quadrado);
		System.out.printf("RETANGULO: %.3f%n", retangulo);
		
		sc.close();   
```

```java
ANÁLISE
--------
`Locale.setDefault(Locale.US);`
- **Linha 1**: Define a localidade padrão como `Locale.US`, garantindo que os números com ponto decimal usem o ponto (`.`) como separador em vez da vírgula, conforme o padrão dos Estados Unidos.


`Scanner sc = new Scanner(System.in);`
- **Linha 2**: Cria um objeto `Scanner` chamado `sc`, que será usado para ler dados da entrada do usuário (via teclado).



`double A, B, C, triangulo, circulo, trapezio, quadrado, retangulo;`
- **Linha 3**: Declara várias variáveis do tipo `double`.
    - `A`, `B`, e `C` armazenarão os valores que o usuário vai fornecer.
    - `triangulo`, `circulo`, `trapezio`, `quadrado`, e `retangulo` armazenarão os resultados dos cálculos das áreas das respectivas figuras geométricas.



`A = sc.nextDouble(); B = sc.nextDouble(); C = sc.nextDouble();`
- **Linhas 4-6**: Essas linhas leem três números do usuário (valores com ponto flutuante) e atribuem os valores às variáveis `A`, `B`, e `C`.


`triangulo = A * C / 2.0;`
- **Linha 7**: Calcula a área de um triângulo usando a fórmula `base * altura / 2`. Nesse caso, `A` é a base e `C` é a altura. O resultado é armazenado em `triangulo`.



`circulo = 3.14159 * C * C;`
- **Linha 8**: Calcula a área de um círculo usando a fórmula `π * raio²`. O valor de `π` é aproximado para `3.14159`, e `C` é o raio. O resultado é armazenado em `circulo`.



`trapezio = (A + B) / 2.0 * C;`
- **Linha 9**: Calcula a área de um trapézio usando a fórmula `(base maior + base menor) / 2 * altura`. Aqui, `A` e `B` são as bases, e `C` é a altura. O resultado é armazenado em `trapezio`.



`quadrado = B * B;`
- **Linha 10**: Calcula a área de um quadrado usando a fórmula `lado²`. O valor de `B` é considerado o lado do quadrado. O resultado é armazenado em `quadrado`.



`retangulo = A * B;`
- **Linha 11**: Calcula a área de um retângulo usando a fórmula `base * altura`. Aqui, `A` é a base e `B` é a altura. O resultado é armazenado em `retangulo`.



`System.out.printf("TRIANGULO: %.3f%n", triangulo); 
System.out.printf("CIRCULO: %.3f%n", circulo); 
System.out.printf("TRAPEZIO: %.3f%n", trapezio); 
System.out.printf("QUADRADO: %.3f%n", quadrado); 
System.out.printf("RETANGULO: %.3f%n", retangulo);`
- **Linhas 12-16**: Imprimem os resultados dos cálculos formatados com 3 casas decimais.
    - `%f` é usado para números de ponto flutuante e `%.3f` garante que serão exibidas 3 casas decimais.
    - `%n` pula para uma nova linha após a impressão.


`sc.close();`
- **Linha 17**: Fecha o objeto `Scanner`, liberando os recursos que ele utilizava. Embora não seja obrigatório em pequenos programas, é uma boa prática fechar o `Scanner` após o uso.
```
