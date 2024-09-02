#  #Documentações

## #OperaçõesBooleanas — `and`, `or`, `not`[](https://docs.python.org/pt-br/3/library/stdtypes.html#boolean-operations-and-or-not "Link para este cabeçalho")

Esses são as operações booleanas, ordenados por prioridade ascendente:

| Operação  | Resultado                                            | Notas |
| --------- | ---------------------------------------------------- | ----- |
| `x or y`  | se _x_ é true, então _x_, do contrário _y_           | (1)   |
| `x and y` | se _x_ é falso, então _x_, do contrário _y_          | (2)   |
| `not x`   | se _x_ é falso, então `True`, caso contrário `False` | (3)   |

Notas:

1. Esse é um operador de curto-circuito, por isso só avalia o segundo argumento se o primeiro é falso.
    
2. Este é um operador de curto-circuito, por isso só avalia o segundo argumento se o primeiro é verdadeiro.
    
3. `not` tem uma prioridade mais baixa do que operadores não booleanos, então `not a == b` é interpretado como `not (a == b)` e `a == not b` é um erro de sintaxe.


# #TiposNuméricos — [`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int"), [`float`](https://docs.python.org/pt-br/3/library/functions.html#float "float"), [`complex`](https://docs.python.org/pt-br/3/library/functions.html#complex "complex")[](https://docs.python.org/pt-br/3/library/stdtypes.html#numeric-types-int-float-complex "Link para este cabeçalho")

Existem três tipos numéricos distintos: _inteiros_, _números de ponto flutuante_ e _números complexos_. Além disso, os booleanos são um subtipo de números inteiros. Inteiros têm precisão ilimitada. Números de ponto flutuante são geralmente implementados usando double em C; informações sobre a precisão e representação interna dos números de ponto flutuante para a máquina na qual seu programa está sendo executado estão disponíveis em [`sys.float_info`](https://docs.python.org/pt-br/3/library/sys.html#sys.float_info "sys.float_info"). Números complexos têm uma parte real e imaginária, cada um com um número de ponto flutuante. Para extrair essas partes de um número complexo _z_, use `z.real` e `z.imag`. (A biblioteca padrão inclui os tipos numéricos adicionais [`fractions.Fraction`](https://docs.python.org/pt-br/3/library/fractions.html#fractions.Fraction "fractions.Fraction"), para racionais, e [`decimal.Decimal`](https://docs.python.org/pt-br/3/library/decimal.html#decimal.Decimal "decimal.Decimal"), para números de ponto flutuante com precisão definida pelo usuário.)

Números são criados por literais numéricos ou como resultado de operadores e funções embutidas. Integrais literais planos (incluindo números hexadecimais, octais e binários) culminam em integrais. Literais numéricos contendo um ponto decimal ou um sinal exponencial resultam em números de ponto flutuante. Anexando `'j'` ou `'J'` para um literal numérico resulta em um número imaginário (um número complexo com uma parte real zero) com a qual você pode adicionar a um integral ou flutuante para receber um número complexo com partes reais e imaginárias.

Python suporta completamente aritmética mista: quando um operador de aritmética binária tem operandos de tipos numéricos diferentes, o operando com o tipo “mais estreito” é ampliado para o tipo do outro operando, onde um inteiro é mais estreito do que um ponto flutuante, que por sua vez é mais estreito que um número complexo. Uma comparação entre números de diferentes tipos se comporta como se os valores exatos desses números estivessem sendo comparados. [[2]](https://docs.python.org/pt-br/3/library/stdtypes.html#id13)

Os construtores [`int()`](https://docs.python.org/pt-br/3/library/functions.html#int "int"), [`float()`](https://docs.python.org/pt-br/3/library/functions.html#float "float"), e [`complex()`](https://docs.python.org/pt-br/3/library/functions.html#complex "complex") podem ser usados para produzir números de um tipo específico.

Todos os tipos numéricos (exceto complexos) suportam as seguintes operações (para prioridades das operações, consulte [Precedência de operadores](https://docs.python.org/pt-br/3/reference/expressions.html#operator-summary)):

#PrioridadesOperaõesAritméticas

| Operação          | Resultado                                                                                 | Notas  | Documentação completa                                                                   |
| ----------------- | ----------------------------------------------------------------------------------------- | ------ | --------------------------------------------------------------------------------------- |
| `x + y`           | soma de _x_ e _y_                                                                         |        |                                                                                         |
| `x - y`           | diferença de _x_ e _y_                                                                    |        |                                                                                         |
| `x * y`           | produto de _x_ e _y_                                                                      |        |                                                                                         |
| `x / y`           | quociente de _x_ e _y_                                                                    |        |                                                                                         |
| `x // y`          | piso do quociente de _x_ e _y_                                                            | (1)(2) |                                                                                         |
| `x % y`           | restante de `x / y`                                                                       | (2)    |                                                                                         |
| `-x`              | _x_ negado                                                                                |        |                                                                                         |
| `+x`              | _x_ inalterado                                                                            |        |                                                                                         |
| `abs(x)`          | valor absoluto ou magnitude de _x_                                                        |        | [`abs()`](https://docs.python.org/pt-br/3/library/functions.html#abs "abs")             |
| `int(x)`          | _x_ convertido em inteiro                                                                 | (3)(6) | [`int()`](https://docs.python.org/pt-br/3/library/functions.html#int "int")             |
| `float(x)`        | _x_ convertido em ponto flutuante                                                         | (4)(6) | [`float()`](https://docs.python.org/pt-br/3/library/functions.html#float "float")       |
| `complex(re, im)` | um número complexo com parte real _re_, parte imaginária _im_. _im_ tem como padrão zero. | (6)    | [`complex()`](https://docs.python.org/pt-br/3/library/functions.html#complex "complex") |
| `c.conjugate()`   | conjugado do número complexo _c_                                                          |        |                                                                                         |
| `divmod(x, y)`    | o par `(x // y, x % y)`                                                                   | (2)    | [`divmod()`](https://docs.python.org/pt-br/3/library/functions.html#divmod "divmod")    |
| `pow(x, y)`       | _x_ elevado a _y_                                                                         | (5)    | [`pow()`](https://docs.python.org/pt-br/3/library/functions.html#pow "pow")             |
| `x ** y`          | _x_ elevado a _y_                                                                         | (5)    |                                                                                         |

Notas:

1. Também referido como uma divisão inteira. Para operandos do tipo [`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int"), o resultado tem o tipo [`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int"); Para operandos do tipo [`float`](https://docs.python.org/pt-br/3/library/functions.html#float "float"), o resultado tem o tipo [`float`](https://docs.python.org/pt-br/3/library/functions.html#float "float"). Em geral o resultado é inteiro como todo, apesar do tipo do resultado não necessariamente ser [`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int"). O resultado é sempre arredondado para menos infinito: `1//2` é `0`, `(-1)//2` é `-1`, `1//(-2)` é `-1` e `(-1)//(-2)` é `0`.
    
2. Não para números complexos. Ao invés disso, converte para pontos flutuantes usando [`abs()`](https://docs.python.org/pt-br/3/library/functions.html#abs "abs") se for apropriado.
    
3. Conversão de [`float`](https://docs.python.org/pt-br/3/library/functions.html#float "float") para [`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int") trunca, descartando a parte fracionária. Veja as funções [`math.floor()`](https://docs.python.org/pt-br/3/library/math.html#math.floor "math.floor") e [`math.ceil()`](https://docs.python.org/pt-br/3/library/math.html#math.ceil "math.ceil") para conversões alternativas.
    
4. ponto flutuante também aceita a string “nan” e “inf” com um prefixo opcional “+” ou “-” a Não é um Número (NaN) e infinidade positiva ou negativa.
    
5. Python define `pow(0, 0)` e `0 ** 0` sendo `1`, como é comum para linguagens de programação.
    
6. Os literais numéricos aceitos incluem os dígitos de `0` a `9` ou qualquer equivalente Unicode (pontos de código com a propriedade `Nd`).
    
    Veja [o Unicode Standard](https://unicode.org/Public/UNIDATA/extracted/DerivedNumericType.txt) para obter uma lista completa de pontos de código com a propriedade `Nd`.
    

Todos os tipos [`numbers.Real`](https://docs.python.org/pt-br/3/library/numbers.html#numbers.Real "numbers.Real") ([`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int") e [`float`](https://docs.python.org/pt-br/3/library/functions.html#float "float")) também incluem as seguintes operações.

| Operação                                                                                     | Resultado                                                                                                                |
| -------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| [`math.trunc(x)`](https://docs.python.org/pt-br/3/library/math.html#math.trunc "math.trunc") | _x_ truncado para [`Integral`](https://docs.python.org/pt-br/3/library/numbers.html#numbers.Integral "numbers.Integral") |
| [`round(x[, n])`](https://docs.python.org/pt-br/3/library/functions.html#round "round")      | _x_ arredondado para _n_ dígitos, arredondando metade para igualar. Se _n_ é omitido, ele toma o padrão de 0.            |
| [`math.floor(x)`](https://docs.python.org/pt-br/3/library/math.html#math.floor "math.floor") | o maior [`Integral`](https://docs.python.org/pt-br/3/library/numbers.html#numbers.Integral "numbers.Integral") <= _x_    |
| [`math.ceil(x)`](https://docs.python.org/pt-br/3/library/math.html#math.ceil "math.ceil")    | pelo menos [`Integral`](https://docs.python.org/pt-br/3/library/numbers.html#numbers.Integral "numbers.Integral") >= _x_ |
|                                                                                              |                                                                                                                          |
Para operações numéricas adicionais, consulte os módulos [`math`](https://docs.python.org/pt-br/3/library/math.html#module-math "math: Mathematical functions (sin() etc.).") e [`cmath`](https://docs.python.org/pt-br/3/library/cmath.html#module-cmath "cmath: Mathematical functions for complex numbers.").


## Tipos  sequências ( #list , #tuple, #range) — [`list`](https://docs.python.org/pt-br/3/library/stdtypes.html#list "list"), [`tuple`](https://docs.python.org/pt-br/3/library/stdtypes.html#tuple "tuple"), [`range`](https://docs.python.org/pt-br/3/library/stdtypes.html#range "range")[](https://docs.python.org/pt-br/3/library/stdtypes.html#sequence-types-list-tuple-range "Link para este cabeçalho")

Existem três tipos básicos de sequência: listas, tuplas e objetos range. Tipos de sequência adicionais adaptados para o processamento de [dados binários](https://docs.python.org/pt-br/3/library/stdtypes.html#binaryseq) e [strings de texto](https://docs.python.org/pt-br/3/library/stdtypes.html#textseq) são descritos em seções dedicadas.

### Operações comuns de sequências[](https://docs.python.org/pt-br/3/library/stdtypes.html#common-sequence-operations "Link para este cabeçalho")

As operações nas seguintes tabelas são suportadas pela maioria dos tipos sequências, ambos mutáveis e imutáveis. A classe ABC [`collections.abc.Sequence`](https://docs.python.org/pt-br/3/library/collections.abc.html#collections.abc.Sequence "collections.abc.Sequence") é fornecida para tornar fácil a correta implementação desses operadores em tipos sequências personalizados.

Essa tabela lista as operações de sequência ordenadas em prioridade ascendente. Na tabela, _s_ e _t_ são sequências do mesmo tipo, _n_, _i_, _j_ e _k_ são inteiros e _x_ é um objeto arbitrário que atende a qualquer restrição de valor e tipo imposta por _s_.

As operações #in e #not in` têm as mesmas prioridades que as operações de comparação. As operações `+` (concatenação) e `*` (repetição) têm a mesma prioridade que as operações numéricas correspondentes. [[3]](https://docs.python.org/pt-br/3/library/stdtypes.html#id14)

|Operação|Resultado|Notas|
|---|---|---|
|`x in s`|`True` caso um item de _s_ seja igual a _x_, caso contrário `False`|(1)|
|`x not in s`|`False` caso um item de _s_ for igual a _x_, caso contrário `True`|(1)|
|`s + t`|a concatenação de _s_ e _t_|(6)(7)|
|`s * n` ou `n * s`|equivalente a adicionar _s_ a si mesmo _n_ vezes|(2)(7)|
|`s[i]`|_i_-ésimo item de _s_, origem 0|(3)|
|`s[i:j]`|fatia de _s_ de _i_ até _j_|(3)(4)|
|`s[i:j:k]`|fatia de _s_ de _i_ até _j_ com passo _k_|(3)(5)|
|`len(s)`|comprimento de _s_||
|`min(s)`|menor item de _s_||
|`max(s)`|maior item de _s_||
|`s.index(x[, i[, j]])`|índice da primeira ocorrência de _x_ em _s_ (no ou após o índice _i_, e antes do índice _j_)|(8)|
|`s.count(x)`|numero total de ocorrência de _x_ em _s_||

Sequências do mesmo tipo também suportam comparações. Em particular, tuplas e listas são comparadas lexicograficamente pela comparação de elementos correspondentes. Isso significa que para comparar igualmente, cada elemento deve comparar igual e as duas sequências devem ser do mesmo tipo e possuírem o mesmo comprimento. (Para detalhes completos, veja [Comparações](https://docs.python.org/pt-br/3/reference/expressions.html#comparisons) na referência da linguagem.)

Iteradores para frente e reversos sobre sequências mutáveis acessam valores usando um índice. Esse índice continuará avançando (ou retrocedendo) mesmo que a sequência subjacente seja alterada. O iterador termina somente quando um [`IndexError`](https://docs.python.org/pt-br/3/library/exceptions.html#IndexError "IndexError") ou um [`StopIteration`](https://docs.python.org/pt-br/3/library/exceptions.html#StopIteration "StopIteration") é encontrado (ou quando o índice cai abaixo de zero).

Notas:

1. Enquanto as operações `in` e `not in` são usadas somente para testes de contenção simples em modo geral, algumas sequências especializadas (tais como [`str`](https://docs.python.org/pt-br/3/library/stdtypes.html#str "str"), [`bytes`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytes "bytes") e [`bytearray`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytearray "bytearray")) também usam-nas para testes de subsequências:
    
    >>>
    
    >>> "gg" in "eggs"
    True
    
2. Os valores de _n_ menos `0` são tratados como `0` (o que produz uma sequência vazia do mesmo tipo que _s_). Observe que os itens na sequência _s_ não são copiados; eles são referenciados várias vezes. Isso frequentemente assombra novos programadores Python; considere então que:
    
    >>>
    
    >>> lists = [[]] * 3
    >>> lists
    [[], [], []]
    >>> lists[0].append(3)
    >>> lists
    [[3], [3], [3]]
    
    O que aconteceu é que `[[]]` é uma lista de um elemento contendo uma lista vazia, então todos os três elementos de `[[]] * 3` são referências a esta única lista vazia. Modificar qualquer um dos elementos de `lists` modifica a lista vazia. Podemos criar uma lista de listas diferentes dessa maneira:
    
    >>>
    
    >>> lists = [[] for i in range(3)]
    >>> lists[0].append(3)
    >>> lists[1].append(5)
    >>> lists[2].append(7)
    >>> lists
    [[3], [5], [7]]
    
    Outra explicação está disponível no FAQ [Como faço para criar uma lista multidimensional?](https://docs.python.org/pt-br/3/faq/programming.html#faq-multidimensional-list).
    
3. Se _i_ ou _j_ for negativo, o índice será relativo ao fim da sequência _s_: `len(s) + i` ou `len(s) + j` será substituído. Mas note que `-0` ainda será `0`.
    
4. A fatia _s_ de _i_ até _j_ é definida como a sequência de itens com índice _k_ tal que `i <= k < j`. Se _i_ ou _j_ foi maior do que `len(s)`, usa `len(s)`. Se _i_ for omitido ou `None`, use `0`. Se _j_ for omitido ou `None`, usa `len(s)`. Se _i_ for maior ou igual a _j_, a fatia é vazia.
    
5. A fatia _s_ de _i_ até _j_ com passo _k_ é definida como sendo a sequência de itens com índice `x = i + n*k` tal que `0 <= n < (j-i)/k`. Em outras palavras, os índices são `i`, `i+k`, `i+2*k`, `i+3*k` e assim por diante, parando quando _j_ for atingido (mas nunca incluindo _j_). Quando _k_ for positivo, _i_ e _j_ serão reduzidos a `len(s)` se forem maiores. Quando _k_ for negativo, _i_ e _j_ são reduzidos para `len(s) - 1` se forem maiores. Se _i_ ou _j_ forem omitidos ou `None`, eles se tornam valores “finais” (cujo final depende de _k_). Nota: _k_ não pode ser zero. Se _k_ for `None`, o mesmo será tratado como sendo igual a `1`.
    
6. Concatenar sequências imutáveis sempre resulta em um novo objeto. Isso significa que a criação de uma sequência por concatenação repetida terá um custo quadrático de tempo de execução no comprimento total da sequência. Para obter um custo de tempo de execução linear, devemos alternar para uma das alternativas abaixo:
    
    - Se estiver concatenando objetos [`str`](https://docs.python.org/pt-br/3/library/stdtypes.html#str "str"), você pode criar uma lista e usar [`str.join()`](https://docs.python.org/pt-br/3/library/stdtypes.html#str.join "str.join") no final ou então escrever numa instância de [`io.StringIO`](https://docs.python.org/pt-br/3/library/io.html#io.StringIO "io.StringIO") e recuperar o seu valor ao final
        
    - Se estiver concatenando objetos [`bytes`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytes "bytes"), você também pode usar o método [`bytes.join()`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytes.join "bytes.join") ou [`io.BytesIO`](https://docs.python.org/pt-br/3/library/io.html#io.BytesIO "io.BytesIO"), ou você pode fazer concatenação interna com um objeto [`bytearray`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytearray "bytearray"). A classe [`bytearray`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytearray "bytearray") são objetos mutáveis e possuem um eficiente mecanismo de superalocação
        
    - Se estiver concatenando objetos [`tuple`](https://docs.python.org/pt-br/3/library/stdtypes.html#tuple "tuple"), estenda a classe [`list`](https://docs.python.org/pt-br/3/library/stdtypes.html#list "list") em vez disso
        
    - para outros tipos, busque na documentação relevante da classe
        
7. Alguns tipos sequências (como [`range`](https://docs.python.org/pt-br/3/library/stdtypes.html#range "range")) apenas suportam sequências de itens que seguem padrões específicos e, portanto, não suportam concatenação ou repetição de sequência.
    
8. `index` levanta [`ValueError`](https://docs.python.org/pt-br/3/library/exceptions.html#ValueError "ValueError") quando _x_ não é encontrado em _s_. Nem todas as implementações suportam a passagem dos argumentos adicionais _i_ e _j_. Esses argumentos permitem a pesquisa eficiente de subseções da sequência. Passar os argumentos extras é aproximadamente equivalente a usar `s[i:j].index(x)`, apenas sem copiar nenhum dado e com o índice retornado sendo relativo ao início da sequência e não ao início da fatia.
    

### Tipos #SequênciaImutáveis[](https://docs.python.org/pt-br/3/library/stdtypes.html#immutable-sequence-types "Link para este cabeçalho")

A única operação que os tipos sequências imutáveis geralmente implementam que também não é implementada pelos tipos sequências mutáveis é suporte para a função embutida [`hash()`](https://docs.python.org/pt-br/3/library/functions.html#hash "hash").

Esse suporte permite sequências imutáveis, tais como instâncias da classe [`tuple`](https://docs.python.org/pt-br/3/library/stdtypes.html#tuple "tuple"), serem usadas como chaves de dicionários [`dict`](https://docs.python.org/pt-br/3/library/stdtypes.html#dict "dict") e armazenados em instâncias de [`set`](https://docs.python.org/pt-br/3/library/stdtypes.html#set "set") e de [`frozenset`](https://docs.python.org/pt-br/3/library/stdtypes.html#frozenset "frozenset").

A tentativa de obter um hash de uma sequência imutável que contém valores desnecessários resultará em um erro [`TypeError`](https://docs.python.org/pt-br/3/library/exceptions.html#TypeError "TypeError").

### Tipos #SequênciasMutáveis[](https://docs.python.org/pt-br/3/library/stdtypes.html#mutable-sequence-types "Link para este cabeçalho")

As operações na tabela a seguir são definidas em tipos sequência mutáveis. A ABC [`collections.abc.MutableSequence`](https://docs.python.org/pt-br/3/library/collections.abc.html#collections.abc.MutableSequence "collections.abc.MutableSequence") é fornecida para tornar mais fácil a implementação correta dessas operações em tipos sequências personalizados.

Na tabela _s_ é uma instância de um tipo de sequência mutável, _t_ é qualquer objeto iterável e _x_ é um objeto arbitrário que atende a qualquer restrição de tipo e valor imposto por _s_ (por exemplo [`bytearray`](https://docs.python.org/pt-br/3/library/stdtypes.html#bytearray "bytearray") só aceita inteiros que atendam a restrição de valor `0 <= x <= 255`).

|Operação|Resultado|Notas|
|---|---|---|
|`s[i] = x`|item _i_ de _s_ é substituído por _x_||
|`s[i:j] = t`|fatias de _s_ de _i_ até _j_ são substituídas pelo conteúdo do iterável _t_||
|`del s[i:j]`|o mesmo que `s[i:j] = []`||
|`s[i:j:k] = t`|os elementos de `s[i:j:k]` são substituídos por aqueles de _t_|(1)|
|`del s[i:j:k]`|remove os elementos de `s[i:j:k]` desde a listas||
|`s.append(x)`|adiciona _x_ no final da sequência (igual a `s[len(s):len(s)] = [x]`)||
|`s.clear()`|remove todos os itens de _s_ (mesmo que `del s[:]`)|(5)|
|`s.copy()`|cria uma cópia rasa de _s_ (mesmo que `s[:]`)|(5)|
|`s.extend(t)` ou `s += t`|estende _s_ com o conteúdo de _t_ (na maior parte do mesmo `s[len(s):len(s)] = t`)||
|`s *= n`|atualiza _s_ com o seu conteúdo por _n_ vezes|(6)|
|`s.insert(i, x)`|insere _x_ dentro de _s_ no índice dado por _i_ (igual a `s[i:i] = [x]`)||
|`s.pop()` ou `s.pop(i)`|retorna o item em _i_ e também remove-o de _s_|(2)|
|`s.remove(x)`|remove o primeiro item de _s_ sendo `s[i]` igual a _x_|(3)|
|`s.reverse()`|inverte os itens de _s_ in-place|(4)|

Notas:

1. If _k_ is not equal to `1`, _t_ must have the same length as the slice it is replacing.
    
2. O argumento opcional _i_ tem como padrão `-1`, de modo que, por padrão, o último item é removido e retornado.
    
3. `remove()` levanta [`ValueError`](https://docs.python.org/pt-br/3/library/exceptions.html#ValueError "ValueError") quando _x_ não é encontrado em _s_.
    
4. O método `reverse()` modifica a sequência no lugar para economizar espaço ao reverter uma grande sequência. Para lembrar os usuários que isso ocorre como sendo um efeito colateral, o mesmo não retorna a sequência invertida.
    
5. `clear()` e `copy()` estão incluídos para consistência com as interfaces de contêineres mutáveis que não suportam operações de fatiamento (como [`dict`](https://docs.python.org/pt-br/3/library/stdtypes.html#dict "dict") e [`set`](https://docs.python.org/pt-br/3/library/stdtypes.html#set "set")). `copy()` não faz parte da ABC de [`collections.abc.MutableSequence`](https://docs.python.org/pt-br/3/library/collections.abc.html#collections.abc.MutableSequence "collections.abc.MutableSequence"), mas a maioria das classes concretas de sequências mutáveis fornece isso.
    
    Adicionado na versão 3.3: Métodos `clear()` e `copy()`.
    
6. O valor _n_ é um inteiro, ou um objeto implementando [`__index__()`](https://docs.python.org/pt-br/3/reference/datamodel.html#object.__index__ "object.__index__"). Valores zero e negativos de _n_ limparão a sequência. Os itens na sequência não são copiados; eles são referenciados várias vezes, como explicado para `s * n` em [Operações comuns de sequências](https://docs.python.org/pt-br/3/library/stdtypes.html#typesseq-common).
    

### #Listas[](https://docs.python.org/pt-br/3/library/stdtypes.html#lists "Link para este cabeçalho")

As listas são sequências mutáveis, normalmente usadas para armazenar coleções de itens homogêneos (onde o grau preciso de similaridade variará de acordo com a aplicação).

_class_ list([_iterable_])[](https://docs.python.org/pt-br/3/library/stdtypes.html#list "Link para esta definição")

As listas podem ser construídas de várias maneiras:

- Usando um par de colchetes para denotar uma lista vazia: `[]`
    
- Usando colchetes, separando itens por vírgulas: `[a]`, `[a, b, c]`
    
- Usando uma compreensão de lista: `[x for x in iterable]`
    
- Usando o construtor de tipo: `list()` ou `list(iterable)`
    

O construtor produz uma lista cujos itens são iguais e na mesma ordem que os itens de _iterable_. _iterable_ pode ser uma sequência, um contêiner que suporte iteração ou um objeto iterador. Se _iterable_ já for uma lista, uma cópia será feita e retornada, semelhante a `iterable[:]`. Por exemplo, `list('abc')` retorna `['a', 'b', 'c']` e `list( (1, 2, 3) )` retorna `[1, 2, 3]`. Se nenhum argumento for dado, o construtor criará uma nova lista vazia `[]`.

Muitas outras operações também produzem listas, incluindo a função embutida [`sorted()`](https://docs.python.org/pt-br/3/library/functions.html#sorted "sorted").

Listas implementam todas as operações de sequências [comuns](https://docs.python.org/pt-br/3/library/stdtypes.html#typesseq-common) e [mutáveis](https://docs.python.org/pt-br/3/library/stdtypes.html#typesseq-mutable). As listas também fornecem o seguinte método adicional:

sort(_*_, _key=None_, _reverse=False_)[](https://docs.python.org/pt-br/3/library/stdtypes.html#list.sort "Link para esta definição")

Esse método classifica a lista in-place, usando apenas comparações `<` entre itens. As exceções não são suprimidas – se qualquer operação de comparação falhar, toda a operação de ordenação falhará (e a lista provavelmente será deixada em um estado parcialmente modificado).

[`sort()`](https://docs.python.org/pt-br/3/library/stdtypes.html#list.sort "list.sort") aceita 2 argumentos que só podem ser passados como [argumentos somente-nomeados](https://docs.python.org/pt-br/3/glossary.html#keyword-only-parameter):

_key_ especifica uma função de um argumento que é usado para extrair uma chave de comparação de cada elemento da lista (por exemplo, `key=str.lower`). A chave correspondente a cada item na lista é calculada uma vez e depois usada para todo o processo de classificação. O valor padrão `None` significa que os itens da lista são classificados diretamente sem calcular um valor de chave separado.

A função utilitária [`functools.cmp_to_key()`](https://docs.python.org/pt-br/3/library/functools.html#functools.cmp_to_key "functools.cmp_to_key") está disponível para converter a função _cmp_ no estilo 2.x para uma função _key_.

_reverse_ é um valor booleano. Se definido igual a `True`, então os elementos da lista são classificados como se cada comparação estivesse invertida.

Este método modifica a sequência in-place para economizar espaço ao classificar uma sequência grande. Para lembrar aos usuários que os mesmos operam por efeito colateral, ele não retorna a sequência ordenada (utilize a função [`sorted()`](https://docs.python.org/pt-br/3/library/functions.html#sorted "sorted") para solicitar explicitamente uma nova instância da lista ordenada).

O método [`sort()`](https://docs.python.org/pt-br/3/library/stdtypes.html#list.sort "list.sort") é garantido como sendo estável. Uma classificação é estável se ela garantir não alterar a ordem relativa de elementos que comparam igual – isso é útil para classificar em várias passagens (por exemplo, classificar por departamento, depois por nota salarial).

Para exemplos de classificação e um breve tutorial de classificação, veja [Sorting Techniques](https://docs.python.org/pt-br/3/howto/sorting.html#sortinghowto).

**Detalhes da implementação do CPython:** No momento em que uma lista está sendo ordenada, o efeito de tentar alterar, ou mesmo inspecionar, a lista é indefinida. A implementação C do Python faz com que a lista apareça vazia durante o tempo de processamento, e levanta a exceção [`ValueError`](https://docs.python.org/pt-br/3/library/exceptions.html#ValueError "ValueError") se puder detectar que a lista foi alterada durante uma ordenação.

### #Tuplas[](https://docs.python.org/pt-br/3/library/stdtypes.html#tuples "Link para este cabeçalho")

Tuplas são sequências imutáveis, tipicamente usadas para armazenar coleções de dados heterogêneos (como as tuplas de 2 elementos produzidas pelo função embutida [`enumerate()`](https://docs.python.org/pt-br/3/library/functions.html#enumerate "enumerate")). Tuplas também são usadas para casos em que seja necessária uma sequência imutável de dados homogêneos (como permitir o armazenamento em uma instância [`set`](https://docs.python.org/pt-br/3/library/stdtypes.html#set "set") ou [`dict`](https://docs.python.org/pt-br/3/library/stdtypes.html#dict "dict")).

_class_ tuple([_iterable_])[](https://docs.python.org/pt-br/3/library/stdtypes.html#tuple "Link para esta definição")

As tuplas podem ser construídas de várias maneiras:

- Usando um par de parênteses para denotar a tupla vazia: `()`
    
- Usando uma vírgula à direita para uma tupla singleton: `a,` ou `(a,)`
    
- Separando os itens com vírgulas: `a, b, c` ou `(a, b, c)`
    
- Usando a função embutida [`tuple()`](https://docs.python.org/pt-br/3/library/stdtypes.html#tuple "tuple"): `tuple()` ou `tuple(iterable)`
    

O construtor constrói uma tupla cujos itens são iguais e na mesma ordem dos itens de _iterable_. _iterable_ pode ser uma sequência, um contêiner que suporta iteração ou um objeto iterador. Se _iterable_ já for uma tupla, este será retornado inalterado. Por exemplo, `tuple('abc')` retorna `('a', 'b', 'c')` e `tuple( [1, 2, 3] )` retorna `(1, 2, 3)`. Se nenhum argumento for dado, o construtor criará uma tupla vazia, `()`.

Observe que, na verdade, é a vírgula que faz uma tupla, e não os parênteses. Os parênteses são opcionais, exceto no caso de tupla vazia, ou quando são necessários para evitar ambiguidades sintáticas. Por exemplo, `f(a, b, c)` é uma chamada da função com três argumentos, enquanto que `f((a, b, c))` é uma chamada de função com uma tupla de 3 elementos com um único argumento.

As tuplas implementam todas as operações [comuns](https://docs.python.org/pt-br/3/library/stdtypes.html#typesseq-common) de sequência.

Para coleções heterogêneas de dados onde o acesso pelo nome é mais claro do que o acesso pelo índice, [`collections.namedtuple()`](https://docs.python.org/pt-br/3/library/collections.html#collections.namedtuple "collections.namedtuple") pode ser uma escolha mais apropriada do que um objeto tupla simples.

### Intervalos[](https://docs.python.org/pt-br/3/library/stdtypes.html#ranges "Link para este cabeçalho")

O tipo [`range`](https://docs.python.org/pt-br/3/library/stdtypes.html#range "range") representa uma sequência imutável de números e é comumente usado para percorrer um número determinado de vezes em um laço [`for`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#for).

_class_ range(_stop_)[](https://docs.python.org/pt-br/3/library/stdtypes.html#range "Link para esta definição")

_class_ range(_start_, _stop_[, _step_])

Os argumentos para o construtor de intervalo devem ser inteiros ([`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int") embutido ou qualquer objeto que implemente o método especial [`__index__()`](https://docs.python.org/pt-br/3/reference/datamodel.html#object.__index__ "object.__index__")). Se o argumento _step_ for omitido, será usado o padrão `1`. Se o argumento _start_ for omitido, será usado o padrão `0`. Se _step_ for zero, uma exceção [`ValueError`](https://docs.python.org/pt-br/3/library/exceptions.html#ValueError "ValueError") será levantada.

Para um _step_ positivo, o conteúdo de um intervalo `r` será determinado pela fórmula `r[i] = start + step*i` onde `i >= 0` e `r[i] < stop`.

Para um _step_ negativo, o conteúdo do intervalo ainda será determinado pela fórmula `r[i] = start + step*i`, mas as restrições serão `i >= 0` e `r[i] > stop`.

Um objeto intervalo estará vazio se `r[0]` não atender à restrição de valor. Intervalos suportam índices negativos, mas estes são interpretados como indexadores partindo do final da sequência determinada pelos índices positivos.

Intervalos contendo valores absolutos maiores que [`sys.maxsize`](https://docs.python.org/pt-br/3/library/sys.html#sys.maxsize "sys.maxsize") são permitidos, mas alguns recursos (como [`len()`](https://docs.python.org/pt-br/3/library/functions.html#len "len")) podem levantar [`OverflowError`](https://docs.python.org/pt-br/3/library/exceptions.html#OverflowError "OverflowError").

Exemplos de intervalos:

>>>

>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> list(range(1, 11))
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> list(range(0, 30, 5))
[0, 5, 10, 15, 20, 25]
>>> list(range(0, 10, 3))
[0, 3, 6, 9]
>>> list(range(0, -10, -1))
[0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
>>> list(range(0))
[]
>>> list(range(1, 0))
[]

Ranges implementam todas as operações [comuns](https://docs.python.org/pt-br/3/library/stdtypes.html#typesseq-common) de sequência, exceto a concatenação e a repetição (devido ao fato de que os objetos intervalos só podem representar sequências que seguem um padrão rígido. e a repetição e a concatenação geralmente vão violar esse padrão).

start[](https://docs.python.org/pt-br/3/library/stdtypes.html#range.start "Link para esta definição")

O valor do parâmetro _start_ (ou `0` se o parâmetro não for fornecido)

stop[](https://docs.python.org/pt-br/3/library/stdtypes.html#range.stop "Link para esta definição")

O valor do parâmetro _stop_

step[](https://docs.python.org/pt-br/3/library/stdtypes.html#range.step "Link para esta definição")

O valor do parâmetro _step_ (ou `1` se o parâmetro não for fornecido)

A vantagem do tipo [`range`](https://docs.python.org/pt-br/3/library/stdtypes.html#range "range") sobre um [`list`](https://docs.python.org/pt-br/3/library/stdtypes.html#list "list") ou [`tuple`](https://docs.python.org/pt-br/3/library/stdtypes.html#tuple "tuple") regular é que um objeto [`range`](https://docs.python.org/pt-br/3/library/stdtypes.html#range "range") sempre terá a mesma quantidade (pequena) de memória, não importa o tamanho do intervalo o mesmo esteja representando (como ele apenas armazena os valores `start`, `stop` e `step`, calculando itens individuais e subintervalos conforme necessário).

Objetos intervalos implementam a ABC [`collections.abc.Sequence`](https://docs.python.org/pt-br/3/library/collections.abc.html#collections.abc.Sequence "collections.abc.Sequence"), e fornecem recursos como testes de contenção, pesquisa de índice de elemento, fatiamento e suporte a índices negativos (veja [Tipos sequências — list, tuple, range](https://docs.python.org/pt-br/3/library/stdtypes.html#typesseq)):

>>>

>>> r = range(0, 20, 2)
>>> r
range(0, 20, 2)
>>> 11 in r
False
>>> 10 in r
True
>>> r.index(10)
5
>>> r[5]
10
>>> r[:5]
range(0, 10, 2)
>>> r[-1]
18

Testar objetos intervalos por igualdade com `==` e `!=` os compara como sequências. Ou seja, dois objetos intervalos são considerados iguais se representarem a mesma sequência de valores. (Observe que dois objetos intervalos considerados iguais podem ter diferentes atributos [`start`](https://docs.python.org/pt-br/3/library/stdtypes.html#range.start "range.start"), [`stop`](https://docs.python.org/pt-br/3/library/stdtypes.html#range.stop "range.stop") e [`step`](https://docs.python.org/pt-br/3/library/stdtypes.html#range.step "range.step"), por exemplo `range(0) == range(2, 1, 3)` ou `range(0, 3, 2) == range(0, 4, 2)`.)

Alterado na versão 3.2: Implementa a ABC Sequence. Suporte a fatiamento e a índices negativos. Testa objetos [`int`](https://docs.python.org/pt-br/3/library/functions.html#int "int") para associação em tempo constante em vez de iterar através de todos os itens.

Alterado na versão 3.3: Define ‘==’ e ‘!=’ para comparar objetos intervalos com base na sequência de valores que eles definem (em vez de comparar com base na identidade do objeto).

Adicionados os atributos [`start`](https://docs.python.org/pt-br/3/library/stdtypes.html#range.start "range.start"), [`stop`](https://docs.python.org/pt-br/3/library/stdtypes.html#range.stop "range.stop") e [`step`](https://docs.python.org/pt-br/3/library/stdtypes.html#range.step "range.step").




## 8.1. A instrução #if[](https://docs.python.org/pt-br/3/reference/compound_stmts.html#the-if-statement "Link para este cabeçalho")

A instrução [`if`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#if) é usada para execução condicional:

**if_stmt** ::=  "if" [`assignment_expression`](https://docs.python.org/pt-br/3/reference/expressions.html#grammar-token-python-grammar-assignment_expression) ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)
             ("elif" [`assignment_expression`](https://docs.python.org/pt-br/3/reference/expressions.html#grammar-token-python-grammar-assignment_expression) ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite))*
             ["else" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]

Ele seleciona exatamente um dos conjuntos avaliando as expressões uma por uma até que uma seja considerada verdadeira (veja a seção [Operações booleanas](https://docs.python.org/pt-br/3/reference/expressions.html#booleans) para a definição de verdadeiro e falso); então esse conjunto é executado (e nenhuma outra parte da instrução [`if`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#if) é executada ou avaliada). Se todas as expressões forem falsas, o conjunto da cláusula [`else`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#else), se presente, é executado.

## 8.2. A instrução #while[](https://docs.python.org/pt-br/3/reference/compound_stmts.html#the-while-statement "Link para este cabeçalho")

A instrução [`while`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#while) é usada para execução repetida desde que uma expressão seja verdadeira:

**while_stmt** ::=  "while" [`assignment_expression`](https://docs.python.org/pt-br/3/reference/expressions.html#grammar-token-python-grammar-assignment_expression) ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)
                ["else" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]

Isto testa repetidamente a expressão e, se for verdadeira, executa o primeiro conjunto; se a expressão for falsa (o que pode ser a primeira vez que ela é testada) o conjunto da cláusula `else`, se presente, é executado e o laço termina.

Uma instrução #break [](https://docs.python.org/pt-br/3/reference/simple_stmts.html#break) executada no primeiro conjunto termina o loop sem executar o conjunto da cláusula #else. Uma instrução #continue[](https://docs.python.org/pt-br/3/reference/simple_stmts.html#continue) executada no primeiro conjunto ignora o resto do conjunto e volta a testar a expressão.

## 8.3. A instrução #for[](https://docs.python.org/pt-br/3/reference/compound_stmts.html#the-for-statement "Link para este cabeçalho")

A instrução [`for`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#for) é usada para iterar sobre os elementos de uma sequência (como uma #string, #tupla ou #lista) ou outro objeto iterável:

**for_stmt** ::=  "for" [`target_list`](https://docs.python.org/pt-br/3/reference/simple_stmts.html#grammar-token-python-grammar-target_list) "in" [`starred_list`](https://docs.python.org/pt-br/3/reference/expressions.html#grammar-token-python-grammar-starred_list) ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)
              ["else" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]

A expressão `starred_list` é avaliada uma vez; deve produzir um objeto [iterável](https://docs.python.org/pt-br/3/glossary.html#term-iterable). Um [iterador](https://docs.python.org/pt-br/3/glossary.html#term-iterator) é criado para esse iterável. O primeiro item fornecido pelo iterador é então atribuído à lista de alvos usando as regras padrão para atribuições (veja [Instruções de atribuição](https://docs.python.org/pt-br/3/reference/simple_stmts.html#assignment)), e o conjunto é executado. Isso se repete para cada item fornecido pelo iterador. Quando o iterador se esgota, o conjunto na cláusula `else`, se presente, é executado e o loop termina.

Uma instrução #break [](https://docs.python.org/pt-br/3/reference/simple_stmts.html#break)  executada no primeiro conjunto termina o loop sem executar o conjunto da cláusula #else. Uma instrução #continue[](https://docs.python.org/pt-br/3/reference/simple_stmts.html#continue) executada no primeiro conjunto pula o resto do conjunto e continua com o próximo item, ou com a cláusula `else` se não houver próximo item.

O laço for faz atribuições às variáveis na lista de destino. Isso substitui todas as atribuições anteriores a essas variáveis, incluindo aquelas feitas no conjunto do laço for:

for i in range(10):
    print(i)
    i = 5             # this will not affect the for-loop
                      # because i will be overwritten with the next
                      # index in the range

Os nomes na lista de destinos não são excluídos quando o laço termina, mas se a sequência estiver vazia, eles não serão atribuídos pelo laço. Dica: o tipo embutido [`range()`](https://docs.python.org/pt-br/3/library/stdtypes.html#range "range") representa sequências aritméticas imutáveis de inteiros. Por exemplo, iterar `range(3)` sucessivamente produz 0, 1 e depois 2.

Alterado na versão 3.11: Elementos marcados com estrela agora são permitidos na lista de expressões.

## 8.4. A instrução #try[](https://docs.python.org/pt-br/3/reference/compound_stmts.html#the-try-statement "Link para este cabeçalho")

A instrução #try especifica manipuladores de exceção e/ou código de limpeza para um grupo de instruções:

**try_stmt ** ::=  [`try1_stmt`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-try1_stmt) | [`try2_stmt`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-try2_stmt) | [`try3_stmt`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-try3_stmt)
**try1_stmt** ::=  "try" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)
               ("except" [[`expression`](https://docs.python.org/pt-br/3/reference/expressions.html#grammar-token-python-grammar-expression) ["as" [`identifier`](https://docs.python.org/pt-br/3/reference/lexical_analysis.html#grammar-token-python-grammar-identifier)]] ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite))+
               ["else" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]
               ["finally" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]
**try2_stmt** ::=  "try" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)
               ("except" "*" [`expression`](https://docs.python.org/pt-br/3/reference/expressions.html#grammar-token-python-grammar-expression) ["as" [`identifier`](https://docs.python.org/pt-br/3/reference/lexical_analysis.html#grammar-token-python-grammar-identifier)] ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite))+
               ["else" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]
               ["finally" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)]
**try3_stmt** ::=  "try" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)
               "finally" ":" [`suite`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#grammar-token-python-grammar-suite)

Informações adicionais sobre #exceções podem ser encontradas na seção [Exceções](https://docs.python.org/pt-br/3/reference/executionmodel.html#exceptions), e informações sobre como usar a instrução #raise[](https://docs.python.org/pt-br/3/reference/simple_stmts.html#raise) para gerar exceções podem ser encontradas na seção [A instrução raise](https://docs.python.org/pt-br/3/reference/simple_stmts.html#raise).

## 4.4. Comandos #break e #continue, e cláusula #else, nos laços de repetição[](https://docs.python.org/pt-br/3/tutorial/controlflow.html#break-and-continue-statements-and-else-clauses-on-loops "Link para este cabeçalho")A instrução [`break`](https://docs.python.org/pt-br/3/reference/simple_stmts.html#break) sai imediatamente do laço de repetição mais interno, seja [`for`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#for) ou [`while`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#while).

Um laço `for` ou `while` pode incluir uma cláusula `else`.

Em um laço [`for`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#for), a cláusula `else` é executada após o laço atingir sua iteração final.

Em um laço [`while`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#while), ele é executado após a condição do laço se tornar falsa.

Em qualquer tipo de laço, a cláusula `else` **não** é executada se o laço for encerrado por um [`break`](https://docs.python.org/pt-br/3/reference/simple_stmts.html#break).

Isso é exemplificado no seguinte laço `for`, que procura por números primos:

>>>

>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(n, 'equals', x, '*', n//x)
...             break
...     else:
...         # loop fell through without finding a factor
...         print(n, 'is a prime number')
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
6 equals 2 * 3
7 is a prime number
8 equals 2 * 4
9 equals 3 * 3

(Sim, o código está correto. Olhe atentamente: a cláusula `else` pertence ao laço [`for`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#for), e **não** ao comando [`if`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#if).)

Quando usado em um laço, a cláusula `else` tem mais em comum com a cláusula `else` de um comando [`try`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#try) do que com a de um comando [`if`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#if): a cláusula `else` de um comando [`try`](https://docs.python.org/pt-br/3/reference/compound_stmts.html#try) executa quando não ocorre exceção, e o `else` de um laço executa quando não ocorre um `break`. Para mais informações sobre comando `try` e exceções, veja [Tratamento de exceções](https://docs.python.org/pt-br/3/tutorial/errors.html#tut-handling).

A instrução [`continue`](https://docs.python.org/pt-br/3/reference/simple_stmts.html#continue), também emprestada da linguagem C, continua com a próxima iteração do laço:

>>>

>>> for num in range(2, 10):
...     if num % 2 == 0:
...         print("Found an even number", num)
...         continue
...     print("Found an odd number", num)
...
Found an even number 2
Found an odd number 3
Found an even number 4
Found an odd number 5
Found an even number 6
Found an odd number 7
Found an even number 8
Found an odd number 9
