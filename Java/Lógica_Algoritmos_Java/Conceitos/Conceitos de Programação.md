# Aula05 - Algoritmos, Automação, Programa de Computador:
#Algoritmo é a sequência finita de instruções para se resolver um problema, é aplicado a diversas áreas de conhecimento.
É como se fosse uma sequência de passos a serem seguidos em ordem para resolver determinada coisa.
Por exemplo:
```
Se eu tenho um problema como lavar a roupa suja.
Podemos utilizar o seguinte algoritmo:
1 - Colocar a roupa em um recipiente 
2 - Colocar un pouco de sabão e amaciante
3 - Encher de água
4 - Mexer tudo até dissolver todo o sabão
5 - Deixar de molho por vinte minutos
6 - Esfregar a roupa
7 - Enxaguar 
8 - Torcer
```

#Automação consiste em utilizar máquinas para executar o procedimento desejado de forma automática ou semiautomática.
No exemplo acima, podemos utilizar uma máquina de lavar roupa para realizar parte do procedimento

Mas o que o algoritmo e automação tem a ver com programação de computadores?
Um computador é formado por #Hardware (que é a parte física(o que se bate)) e o #Software( que é a parte lógica/programas, Sistemas Operacionais, Aplicativos, Jogos, Navegadores, Utilitários e etc.)

E temos uma similaridade entre algoritmo, automação e computador.
Programas de computador são algoritmos executados pelo computador.
O computador é uma máquina que automatiza a execução de algoritmos.
Não qualquer algoritmo, apenas algoritmos computacionais como Processamento de dados e Cálculos

#ResumoAula05: 
- Algoritmo: sequência de passos para se resolver determinado problema.
- Automação: Quando uma máquina realiza o algoritmo
	- Hardware(parte física)  
	- Software(Sistemas)
	- máquina que automatiza algoritmos (cálculo)
- Programa de computador: Algoritmo executado pelo computador

# Aula06 - O que é preciso para se fazer um programa de computador:

Para construirmos um programa de computador(algoritmos executados pelo pc) precisaremos de 4 coisas:
- Uma `linguagem de programação:` Regras `léxicas` e `sintáticas` para se escrever o programa.
- Uma `IDE:` Software para editar e testar o programa
- Um `compilador` Software para transformar o `código-fonte` em `código-objeto`
- Um `gerador de código` ou `máquina virtual`: Software que permite que o programa seja executado

# Aula07 - Linguagem de programação, léxica, sintática

Linguagem de programação é um conjunto de regras `léxicas` (ortografia) e `sintáticas` (gramática) para se escrever programas.
Léxica diz respeito à correção das palavras "isoladas" (ortografia) 
Por exemplo:
```
Léxica(ortografia)
Exemplo(português)             |  Linguagem de programação
cachorro(ortografia correta)   |   main (ortografia correta)
caxorro(ortografia incorreta)  |   main (ortografia incorreta)
```

Sintática diz respeito à correção das sentenças(gramática)
```
Sintática(grámatica)
Exemplo(portugês)                               |  Linguagem de programação
O cachorro está com fome.(ortografia correta)   | x = 2 + y (ortografia correta)
A cachorro está com fome.(ortografia incorreta) | x = + 2 y (ortografia incorreta)

```

Exemplos de linguagem: C, Pascal, C++, C#, Python, Ruby, PHP, JavaScript, etc.

Vamos usar o exemplo de um programa:
```java
Suponha um programa que solicita do usuário dois números e depois mostra a média aritmética deles:
Digite o primeiro número: 3
Digite o segundo número: 6
Media = 4.5

Solução em linguagem C:
int main(){
	double x, y, media
	printf("Digite o primeiro número: ");
	scanf("%if", &x);
	printf("Digite o segundo número: ");
	scanf("%yf", &y);
	media = (x + y) / 2
	printf("Media = %.if\n", media);
	return 0;
}

Solução na linguagem C++'
using namespace std;
int main() {
	double x, y, media;
	cout <<,"Digite o primeiro número: ";
	cin >> x;
	cout << "Digite o segundo número: ";
	cin << y;
	media = (x + y) / 2.0;
	cout << "Media = " << media << endl;
	return 0;
}
```

#ResumoAula7 
- #Linguagem: Conjunto de regras léxicas e sintáticas para se escrever um programa 
	- `Léxica` = ortografia. Palavras isoladas
	- `Sintática` = gramática. Sentença como um todo
- Exemplos de linguagem: C, Pascal, C++, C#, Python, Ruby, PHP, JavaScript, etc.
- Exemplos de códigos feitos em C e C++

# Aula08 - IDE - Ambiente de Desenvolvimento Integrado

#IDE é um conjunto de software utilizado para a construção de programas.
Exemplos:
```
C/C++ : Code Blocks
Java : Eclipse, NetBeans
C# : Microsoft Visual Studio
```

#Funcionalidades de uma IDE:
- Edição de código finte (endentação, autocompletar, destaque de palavras, etc.)
- Depuração e testes
- Construção do produto final (build)
- Sugestão de modelos (templates)
- Auxiliar em várias tarefas do seu projeto

#ResumoAula8 
- #IDE : Conjunto de software utilizado para a construção de programas.
	- C/C++ : Code Blocks
	- Java : Eclipse, NetBeans
	- C# : Microsoft Visual Studio
- Uma IDE oferece várias funcionalidades para facilidades para facilitar a construção dos programas

# Aula09 - Compilação, Interpretação, código fonte, código objeto, máquina virtual

#CódigoFonte: É aquele escrito pelo programador em linguagem de programação.
Porém esse código não é compreendido pelo computador e nem pelo sistema operacional, ele tem que ser convertido em um código que possa ser executado pelo PC e SO.

### Compilação
Ai que entra o processo chamado de #Compilação: É um processo que transforma o código fonte em código objeto, esse processo é feito por um software compilador, e durante esse processo esse software detectar algum erro léxico ou sintático, a compilação é abortada e o programador é obrigado a corrigir o erro léxico ou sintático. Uma vez que o código fonte foi compilado e transformado em código objeto, ele irá passar por um gerador de código, chamado construção( #build) e ai sim esse código pode ser executado pelo SO

Esse modelo de compilação é utilizado por várias linguagens, como: C, C++
### Interpretação
Porém, nem toda linguagem utiliza o processo acima, existe um processo chamado #Interpretação que é quando eu tenho um software chamado #Interpretador que ele vai ler o código fonte e vai realizar a Análise Léxica, Análise Sintática, Geração de Código sob demanda, ou seja gradualmente o interpretador vai lendo o código fonte traduzindo ele para código executável e executando.

Esse modelo de interpretação é utilizado por várias linguagens, como: PHP, JavaScript, Python, Ruby

### Abordagem Híbrida

O código fonte passa por uma #preCompilação que faz a análise #léxica e #sintática, gerando um código objeto chamado de byte-code, o byte-code é um código precompilado
Ao invés de passar por gerador de código e gerar um código executável, esse código vai ser executado por uma máquina virtual, e nessa máquina o código é #Interpretado ai sim faz a geração do código sob demanda e a execução do código

Essa abordagem híbrida é adotada por algumas linguagens como: Java(JVM), C#(Microsoft .NET Framework)

A máquina virtual que executa o byte-code do Java é chamada de #JVM, e máquina virtual que executa o C# é o dot .net framework

### Vantagens da #Compilação
- Velocidade do programa
- Auxílio do compilador antes da execução
### Vantagens da #Interpretação
- Flexibilidade de manutenção do aplicativo em produção
- Expressividade da linguagem
- Código fonte não precisa ser recompilado para rodar em plataformas diferentes

### Vantagens do Híbrido
- Auxílio do compilador antes da execução (muito aproveitada)
- Código fonte não precisa ser recompilado para rodar em plataformas diferentes (muito aproveitada)
- Velocidade do programa (parcialmente aproveitada)
- Flexibilidade de manutenção do aplicativo em produção (parcialmente aproveitada)
### Funcionamento das três abordagens

```
Compilação               Interpretação              Híbrido
-------------------|   |--------------------      |---------------------|
Código fonte       |   | Código fonte      |      |  Código Fonte       |
Sistema Operacional|   | Interpretador     |      |   ByteCode          | 
Hardware           |   |Sistema Operacional|      | Máquina Virtual     |
-------------------|   |    Hardware       |      |  Sistema Operacional|
C, C++             |   |-------------------|      |   Hardware          | 
                       | PHP, Python,      |      | -------------------- |
                       | JavaScript        |      |    Java, C#          |
                                                
 
```

### #ResumoAula09
- Tipos de Código
	- Código Fonte
	- Código Objeto/ bytecode
- Modelos de Execução
	- Compilação
		- Gerador de código
	- Interpretação
	- Híbrida
		- Máquina Virtual
