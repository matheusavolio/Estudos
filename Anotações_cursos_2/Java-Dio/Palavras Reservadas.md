Palavras reservadas são identificadores de uma linguagem que já possuem uma finalidade específica, portanto não podem ser utilizados para nomear variáveis, classes, métodos ou atributos.

A linguagem Java possui 52 palavras reservadas. Todas essas palavras são classificadas em grupos e escritas com letra minúscula, sendo identificadas com uma cor especial pela maioria das IDE's. Abaixo temos a lista de palavras agrupadas por sua finalidades.

![](https://felipe-aguiar.gitbook.io/~gitbook/image?url=https%3A%2F%2F2590158637-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F2qZwrhEqcOsERZF1L25d%252Fuploads%252Fgit-blob-d55c8e2cee24f556c8be85dcfbba3022ad042ab4%252Fimage%2520%2810%29%2520%281%29%2520%281%29%2520%281%29.png%3Falt%3Dmedia&width=768&dpr=4&quality=100&sign=6b4ac4e8&sv=1)

|Controle de pacotes|
|---|
|**import:** importa pacotes ou classes para dentro do código<br><br>**package:** especifica a que pacote todas as classes de um arquivo pertencem|

|Modificadores de acesso|
|---|
|**public:** acesso de qualquer classe<br><br>**private:** acesso apenas dentro da classe<br><br>**protected:** acesso por classes no mesmo pacote e subclasses|

|Primitivos|
|---|
|**boolean:** um valor indicando verdadeiro ou falso<br><br>**byte:** um inteiro de 8 bits (signed)<br><br>**char:** um character unicode (16-bit unsigned)<br><br>**double:** um número de ponto flutuante de 64 bits (signed)<br><br>**float:** um número de ponto flutuante de 32 bits (signed)<br><br>**int:** um inteiro de 32 bits (signed)<br><br>**long:** um inteiro de 64 bits (signed)<br><br>**short:** um inteiro de 32 bits (signed)<br><br>**void:** indica que o método não tem retorno **de valor**|

|Modificadores de classes, variáveis ou métodos|
|---|
|**abstract:** classe que não pode ser instanciada ou método que precisa ser implementado por uma subclasse não abstrata<br><br>**class:** especifica uma classe<br><br>**extends:** indica a superclasse que a subclasse está estendendo<br><br>**final:** impossibilita que uma classe seja estendida, que um método seja sobrescrito ou que uma variável seja reinicializada<br><br>**implements:** indica as interfaces que uma classe irá implementar<br><br>**interface:** especifica uma interface<br><br>**native****:** indica que um método está escrito em uma linguagem dependente de plataforma, como o C<br><br>**new:** instancia um novo objeto, chamando seu construtor<br><br>**static:** faz um método ou variável pertencer à classe ao invés de às instâncias<br><br>**strictfp****:** usado em frente a um método ou classe para indicar que os números de ponto flutuante seguirão as regras de ponto flutuante em todas as expressões<br><br>**synchronized:** indica que um método só pode ser acessado por uma thread de cada vez<br><br>**transient:** impede a serialização de campos<br><br>**volatile****:** indica que uma variável pode ser alterada durante o uso de threads|

|Controle de fluxo dentro de um bloco de código|
|---|
|**break:** sai do bloco de codigo em que ele está<br><br>**case:** executa um bloco de código dependendo do teste do switch<br><br>**continue:** pula a execução do código que viria após essa linha e vai para a próxima passagem do loop<br><br>**default:** executa esse bloco de codigo caso nenhum dos teste de switch-case seja verdadeiro<br><br>**do:** executa um bloco de código uma vez, e então realiza um teste em conjunto com o while para determinar se o bloco deverá ser executado novamente<br><br>**else:** executa um bloco de código alternativo caso o teste if seja falso<br><br>**for:** usado para realizar um loop condicional de um bloco de código<br><br>**if:** usado para realizar um teste lógico de verdadeiro o falso<br><br>**instanceof:** determina se um objeto é uma instância de determinada classe, superclasse ou interface<br><br>**return:** retorna de um método sem executar qualquer código que venha depois desta linha (também pode retornar uma variável)<br><br>**switch:** indica a variável a ser comparada nas expressões case<br><br>**while:** executa um bloco de código repetidamente enquanto a condição for verdadeira|

|Tratamento de erros|
|---|
|**assert:** testa uma expressão condicional para verificar uma suposição do programador<br><br>**catch:** declara o bloco de código usado para tratar uma exceção<br><br>**finally:** bloco de código, após um try-catch, que é executado independentemente do fluxo de programa seguido ao lidar com uma exceção<br><br>**throw:**usado para passar uma exceção para o método que o chamou<br><br>**throws:** indica que um método pode passar uma exceção para o método que o chamou<br><br>**try:** bloco de código que tentará ser executado, mas que pode causar uma exceção|

|Variáveis de referência|
|---|
|**super:** refere-se a superclasse imediata<br><br>**this:** refere-se a instância atual do objeto|

|Palavras reservadas não utilizadas|
|---|
|**const:** Não utilize para declarar constantes; use public static final<br><br>**goto:** não implementada na linguagem Java por ser considerada prejudicial|

|Literais reservados|
|---|
|De acordo com a Java Language Specification, **null**, **true** e **false** são tecnicamente chamados de valores literais, e não keywords. Se você tentar criar algum identificador com estes valores, você também terá um erro de compilação.|

#### 

[](https://felipe-aguiar.gitbook.io/dio-java/gitbook/sintaxe/palavras-reservadas#escopo-de-uso)

Escopo de uso

|Uso|Palavras|Observação|
|---|---|---|
|Arquivo|package, import, static||
|Classe|public ou protected ou private + final ou abstract + extends ou implements|**private** (em caso de classe interna), **final** ou **abstract** ?|
|Método|public ou protected ou private + static ou final ou abstract + void e return|**void** em caso de não ter retorno ou **return** se houver|
|Atributo|public ou protected ou private + static ou final + tipo primitivo|****|

#### 

[](https://felipe-aguiar.gitbook.io/dio-java/gitbook/sintaxe/palavras-reservadas#palavras-opostas)

Palavras "opostas"

Assim como nas classificações gramaticais da língua portuguesa, existem algumas palavras que são completamente opostas (antônimas) na linguagem Java conforme tabela abaixo:

| Palavra | Palavra    | Explicação                                                                                                                                                                                                                                                                |
| ------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| package | import     | Enquanto **package** determina o diretório real da classe, o **import** informe de onde será imprtada a classe. Isso porque podemos ter classes de mesmo nome.                                                                                                            |
| extends | implements | enquanto **extends** determinas que uma classe estende outra classe, **implements** determina que uma classe implementa uma interface, porém nunca o contrário                                                                                                            |
| final   | abstract   | enquanto **final** determina fim de alteração de valor ou lógica comportamental, **abstract** em métodos exige que sub-classes precisarão definir comportamento é um método abstrato. NOTA: Se uma classe contém um único método abstrato, toda classe precisa ser.       |
| throws  | throw      | Esta é uma das situações mais complicadas de compreensão destas duas palavras. Enquanto a **throws** determina que um método pode lançar uma exceção, **throw** é a implementação que dispara a exceção**. Vamos conhecer mais sobre este conceito no assunto Exceções.** |
