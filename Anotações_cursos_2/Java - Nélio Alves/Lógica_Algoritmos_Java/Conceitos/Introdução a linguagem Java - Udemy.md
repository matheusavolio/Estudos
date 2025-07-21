LTS - Long Term Support

# Aula13 - Histórico e edições de Java
#### Java - Contextualização
O que é Java?
- `Linguagem de programação (regras sintáticas)
- `plataforma de desenvolvimento e execução
	- `biblioteca(API)
	- `ambientes de execução

#### Histórico
- `Problemas resolvidos e motivo de seu sucesso
	- `Ponteiros/gerenciamento de memória
	- `Poratabilidade falha: reescrever parte do código ao mudar de SO
	- `Utilização em dispositivos diversos
	- `Custo
- `Criado pela Sun Microsystems no meio da década de 1990 `
- `Adquirida pela Oracle Corporation em 2010`
- `Linguagem totalmente orientada a objetos`
- `Linguagem de alto nível`

#### Aspectos notáveis
- `Código compilado para bytecode e executado em máquina virtual (JVM)`
- `Portável, segura, robusta`
- `Roda em vários tipos de dispositivos`
- `Domina o mercado corporativo desde o fim do século 20`
- `Padrão Android por muitos anos`

#### Edições
-  `Java ME - Java Micro Edition - dispositivos embarcados e móveis - IoT`
- `Java SE - Java Standart Edition - core - desktop e servidores`
- `Java EE - Java Enterprise Edition - aplicações corporativas`

# Aula14 - JDK/JVM - Máquina Virtual do Java

#### Plataforma Java SE
- `JVM - Java Virtual Machine`
	- `Máquina virtual do Java - necessário para executar sistemas Java`

O modelo de execução do Java, é um modelo Híbrido, seguindo o seguinte caminho até a execução do programa:
Código -> compilador -> Bytecode -> Compilação JIT e JVM -> Código de máquina
Compilação JIT - Compilação Just in Time (Mais rápida que a interpretação)

# Aula15 - Estrutura de uma aplicação Java
- `Java é uma linguagem orientada a objetos, e a base de uma linguagem OO são as` #class
- `Depois das classes, temos o conceito de pacotes` #package -> `Agrupamento lógico de classes relacionadas
-  `Depois de #package`, `temos o conceito do módulos -> Agrupamento lógico de pacotes relacionados
- `Runtime -> Agrupamento físico
Cada #build ou #Runtime, é uma unidade física que pode ser instalada para ser rodadas nos dispositivos
- `Aplicação -> Agrupamento de módulos relacionados`

# Aula18 - Primeiro programa em Java no Eclipse

 -  `Workspace (selecione a pasta aonde os projetos serão salvos) 
 -  `Mudar o layout: Window -> Perspective -> Open Perspective -> Java 
 -  `Zerar o layout: Window -> Perspective -> Reset Perspective 
 -  `Mostrar a aba Console: Window -> Show View -> Console 
 -  `Criar projeto: File -> New -> Java Projec

Criar classe: 
- `` Botão direito na pasta "src" -> New -> Class 
-  `Package: deixe em branco 
- `Nome da classe: Main (com M maiúsculo) •
- `Marque a opção: public static void main(String[] args) •
- `Mudar o tamanho da fonte:
	- `Mudar o tamanho da fonte: 
		`- CTRL +
		`- CTRL -

