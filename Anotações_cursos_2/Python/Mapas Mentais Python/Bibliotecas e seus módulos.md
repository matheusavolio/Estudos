# Para importar novas bibliotecas utiliza-se o
`import nome_da_biblioteca 

>`esse comando importa todo o conteúdo da biblioteca

# Para importar somente um modulo da biblioteca: 
`from biblioteca import modulo` 

>`diferente do exemplo acima que importa todo o conteúdo da biblioteca
>`esse importa apenas o conteúdo selecionado após o import

# Para renomear o nome da biblioteca ou modulo:
`from biblioteca import modulo as nome_desejado
`import nome_da_biblioteca as nome_desejado
>`coloca se o as e em seguida o nome que deseja
`por exemplo: 
`from math   import sqrt     as  rQ
#biblioteca   #módulo    #renomeando

------------------------------------------------------------------------
------------------------------------------------------------------------
Para #importar uma #biblioteca externa, basta entrar no site https://pypi.org.
pesquisar a biblioteca que deseja instalar, e copiar o código de instalação no terminal, ai esta pronta para se importada

# um exemplo de biblioteca que não vem instalada no python:

`import emoji
`print(emoji.emojize("Teste emoji :red_heart:"))

`utilizei o emoji.emojize("":nome_do_emoji:") para adicionar o emoji dentro da string
### Baixando Bibliotecas Externas em Python

#### 1. **Usando o Gerenciador de Pacotes `pip`**

- **Comando Básico:**
    
    - #pip install nome_da_biblioteca
    - Exemplo: Para instalar a biblioteca `requests`, use:
        
        python
        
        Copiar código
        
        `pip install requests`
        
- **Especificando Versão:**
    
    - #pip install nome_da_biblioteca==versão
    - Exemplo: Para instalar a versão 2.25.1 da biblioteca `requests`:
        
        python
        
        Copiar código
        
        `pip install requests==2.25.1`
        
- **Instalando Múltiplas Bibliotecas:**
    
    - #pip install biblioteca1 biblioteca2
    - Exemplo: Para instalar `requests` e `numpy` simultaneamente:
        
        python
        
        Copiar código
        
        `pip install requests numpy`
        
- **Atualizando uma Biblioteca:**
    
    - #pip install --upgrade nome_da_biblioteca
    - Exemplo: Para atualizar `requests` para a versão mais recente:
        
        python
        
        Copiar código
        
        `pip install --upgrade requests`
        
- **Instalando de um Arquivo `requirements.txt`:**
    
    - #pip install -r requirements.txt
    - Exemplo: Se você tem um arquivo `requirements.txt` com várias dependências, use:
        
        python
        
        Copiar código
        
        `pip install -r requirements.txt`


------------------------------------------------------------------------
------------------------------------------------------------------------


### Biblioteca #math do Python

#### 1. **Funções Matemáticas Básicas**

- #ceil(x): Arredonda para cima.
- #floor(x): Arredonda para baixo.
- #fabs(x): Valor absoluto.
- #factorial(x): Fatorial de x.
- #copysign(x, y): Copia o sinal de y para x.
- #fsum(iterable): Soma precisa de valores em um iterável.
- #gcd(x, y): Maior divisor comum.

#### 2. **Funções Exponenciais e Logarítmicas**

- #exp(x): Exponencial de x.
- #log(x[, base]): Logaritmo de x na base fornecida.
- #log2(x): Logaritmo base 2 de x.
- #log10(x): Logaritmo base 10 de x.
- #pow(x, y): Potência, equivalente a x**y.
- #sqrt(x): Raiz quadrada.

#### 3. **Funções Trigonométricas**

- #sin(x): Seno.
- #cos(x): Cosseno.
- #tan(x): Tangente.
- #asin(x): Arco seno.
- #acos(x): Arco cosseno.
- #atan(x): Arco tangente.
- #atan2(y, x): Arco tangente de y/x considerando o quadrante.
- #hypot(x, y): Hipotenusa, equivalente a sqrt(x² + y²).

#### 4. **Funções Hiperbólicas**

- #sinh(x): Seno hiperbólico.
- #cosh(x): Cosseno hiperbólico.
- #tanh(x): Tangente hiperbólica.
- #asinh(x): Arco seno hiperbólico.
- #acosh(x): Arco cosseno hiperbólico.
- #atanh(x): Arco tangente hiperbólica.

#### 5. **Funções de Ângulos**

- #degrees(x): Converte radianos para graus.
- #radians(x): Converte graus para radianos.

#### 6. **Funções de Manipulação de Números**

- #modf(x): Separa parte inteira e fracionária.
- #trunc(x): Trunca o valor para a parte inteira.
- #frexp(x): Decompõe x em mantissa e expoente.
- #ldexp(x, i): Retorna x * (2**i).

#### 7. **Constantes**

- #pi: Valor de π (pi).
- #e: Base do logaritmo natural.
- #tau: Valor de 2π.
- #inf: Representa o infinito.
- #nan: Representa “Not a Number” (não é um número).

------------------------------------------------------------------------
------------------------------------------------------------------------

### Biblioteca #datetime do Python

#### 1. **Classes Principais**

- #datetime: Combinação de data e hora.
- #date: Representa uma data (ano, mês, dia).
- #time: Representa uma hora (hora, minuto, segundo, microssegundo).
- #timedelta: Representa a diferença entre duas datas ou horas.
- #tzinfo: Base para classes de fuso horário.
- #timezone: Subclasse de tzinfo para fusos horários fixos.

#### 2. **Métodos da Classe datetime**

- #today(): Retorna a data e hora atuais.
- #now([tz]): Retorna a data e hora atuais com fuso horário opcional.
- #utcnow(): Retorna a data e hora atuais em UTC.
- #fromtimestamp(timestamp[, tz]): Converte um timestamp para datetime.
- #strptime(date_string, format): Converte uma string em um objeto datetime usando o formato especificado.
- #strftime(format): Converte o objeto datetime em uma string formatada.
- #combine(date, time): Combina objetos date e time em um objeto datetime.
- #replace(year, month, day, hour, minute, second, microsecond, tzinfo): Retorna um novo objeto datetime com valores substituídos.

#### 3. **Métodos da Classe date**

- #today(): Retorna a data atual.
- #fromtimestamp(timestamp): Converte um timestamp para date.
- #fromordinal(ordinal): Converte um número ordinal em date.
- #isoformat(): Retorna a data no formato ISO (YYYY-MM-DD).
- #strftime(format): Converte o objeto date em uma string formatada.
- #replace(year, month, day): Retorna um novo objeto date com valores substituídos.

#### 4. **Métodos da Classe time**

- #isoformat(): Retorna a hora no formato ISO.
- #strftime(format): Converte o objeto time em uma string formatada.
- #replace(hour, minute, second, microsecond): Retorna um novo objeto time com valores substituídos.

#### 5. **Métodos da Classe timedelta**

- #total_seconds(): Retorna o total de segundos.
- #days: Retorna o número de dias.
- #seconds: Retorna o número de segundos (excluindo dias completos).
- #microseconds: Retorna o número de microssegundos.

#### 6. **Métodos da Classe timezone**

- #utc: Retorna o objeto timezone UTC.
- #fromutc(dt): Converte um objeto datetime para UTC.
- #dst(dt): Retorna o horário de verão (se aplicável).
- #tzname(dt): Retorna o nome do fuso horário.

#### 7. **Constantes**

- MINYEAR: Valor mínimo para o ano (1).
- MAXYEAR: Valor máximo para o ano (9999).

------------------------------------------------------------------------
-----------------------------------------------------------------------

### Biblioteca #time do Python

#### 1. **Funções de Manipulação de Tempo**

- #time(): Retorna o tempo atual em segundos desde a Época (Epoch).
- #ctime([secs]): Converte um tempo em segundos para uma string representando a data e hora local.
- #gmtime([secs]): Converte um tempo em segundos para uma struct_time em UTC.
- #localtime([secs]): Converte um tempo em segundos para uma struct_time na hora local.
- #mktime(t): Converte uma struct_time para segundos desde a Época (Epoch).
- #strftime(format[, t]): Formata uma struct_time ou tupla de tempo de acordo com o formato especificado.
- #strptime(string, format): Converte uma string representando uma data/hora em um objeto struct_time de acordo com o formato especificado.
- #asctime([t]): Converte uma struct_time ou tupla de tempo para uma string representando a data e hora.
- #sleep(secs): Suspende a execução do programa por um número especificado de segundos.

#### 2. **Funções de Precisão de Tempo**

- #perf_counter(): Retorna o valor do cronômetro de alta resolução em segundos (inclui tempo de suspensão).
- #process_time(): Retorna o tempo de CPU usado pelo processo atual em segundos.
- #monotonic(): Retorna o valor de um relógio que não retrocede, em segundos.
- #time_ns(): Retorna o tempo atual em nanossegundos desde a Época (Epoch).
- #perf_counter_ns(): Retorna o valor do cronômetro de alta resolução em nanossegundos.
- #process_time_ns(): Retorna o tempo de CPU em nanossegundos.
- #monotonic_ns(): Retorna o valor de um relógio que não retrocede, em nanossegundos.

#### 3. **Funções de Ajuste de Tempo**

- #tzset(): Define as variáveis de ambiente para a timezone atual.
- #gettimeofday(): Retorna o tempo atual em segundos e microssegundos desde a Época (Epoch).
- #settimeofday(t, tz): Define o tempo do sistema.

#### 4. **Estruturas de Dados**

- struct_time: Uma tupla que representa um tempo, incluindo atributos como ano, mês, dia, hora, minuto, segundo, dia da semana, dia do ano e horário de verão.

#### 5. **Constantes**

- timezone: Diferença em segundos entre UTC e a hora local padrão.
- altzone: Diferença em segundos entre UTC e a hora local de horário de verão.
- daylight: Flag que indica se o horário de verão está em vigor (1) ou não (0).
- tzname: Uma tupla com os nomes das zonas de fuso horário local (normal e de horário de verão).


------------------------------------------------------------------------
------------------------------------------------------------------------
### Biblioteca #operator do Python

#### 1. **Operadores Aritméticos**

- #add(a, b): Adição (a + b).
- #sub(a, b): Subtração (a - b).
- #mul(a, b): Multiplicação (a * b).
- #truediv(a, b): Divisão verdadeira (a / b).
- #floordiv(a, b): Divisão inteira (a // b).
- #mod(a, b): Módulo (a % b).
- #pow(a, b): Potência (a ** b).
- #neg(a): Negativo (-a).
- #pos(a): Positivo (+a).
- #abs(a): Valor absoluto (abs(a)).

#### 2. **Operadores de Comparação**

- #eq(a, b): Igual (a == b).
- #ne(a, b): Diferente (a != b).
- #lt(a, b): Menor que (a < b).
- #le(a, b): Menor ou igual a (a <= b).
- #gt(a, b): Maior que (a > b).
- #ge(a, b): Maior ou igual a (a >= b).

#### 3. **Operadores Lógicos**

- #and_(a, b): E lógico (a and b).
- #or_(a, b): Ou lógico (a or b).
- #not_(a): Não lógico (not a).

#### 4. **Operadores Bit a Bit**

- #invert(a): Inversão bit a bit (~a).
- #lshift(a, b): Deslocamento à esquerda (a << b).
- #rshift(a, b): Deslocamento à direita (a >> b).
- #or_(a, b): Ou bit a bit (a | b).
- #xor(a, b): XOR bit a bit (a ^ b).
- #and_(a, b): E bit a bit (a & b).

#### 5. **Operadores de Acesso a Itens e Atributos**

- #getitem(obj, key): Acessa o item em `obj[key]`.
- #setitem(obj, key, value): Define o item em `obj[key]` para `value`.
- #delitem(obj, key): Remove o item em `obj[key]`.
- #getattr(obj, name): Acessa o atributo `obj.name`.
- #setattr(obj, name, value): Define o atributo `obj.name` para `value`.
- #delattr(obj, name): Remove o atributo `obj.name`.

#### 6. **Operadores de Sequência**

- #concat(a, b): Concatena duas sequências (a + b).
- #contains(a, b): Verifica se b está em a (b in a).
- #countOf(a, b): Conta o número de ocorrências de b em a.
- #indexOf(a, b): Retorna o índice de b em a.
- #is_(a, b): Verifica se a é b (a is b).
- #is_not(a, b): Verifica se a não é b (a is not b).

#### 7. **Funções Utilitárias**

- #itemgetter(*items): Retorna uma função que obtém itens específicos de um objeto.
- #attrgetter(*attrs): Retorna uma função que obtém atributos específicos de um objeto.
- #methodcaller(name, *args, **kwargs): Retorna uma função que chama um método específico em um objeto, com argumentos opcionais.


------------------------------------------------------------------------
------------------------------------------------------------------------
### Biblioteca #random do Python

#### 1. **Funções de Geração de Números Aleatórios**

- #random(): Retorna um número float aleatório entre 0.0 e 1.0.
- #uniform(a, b): Retorna um número float aleatório entre `a` e `b`.
- #randint(a, b): Retorna um número inteiro aleatório entre `a` e `b` (inclusive).
- #randrange(start, stop[, step]): Retorna um número inteiro aleatório selecionado a partir da sequência `range(start, stop, step)`.
- #choice(seq): Retorna um elemento aleatório de uma sequência não-vazia.
- #choices(population, weights=None, *, cum_weights=None, k=1): Retorna uma lista com `k` elementos escolhidos aleatoriamente da `population`, com a possibilidade de aplicar pesos.
- #sample(population, k): Retorna uma lista de `k` elementos únicos escolhidos aleatoriamente da `population`.
- #shuffle(x[, random]): Embaralha a sequência x in place.
- #seed(a=None, version=2): Inicializa o gerador de números aleatórios.
- #getrandbits(k): Retorna um inteiro com `k` bits aleatórios.
- #betavariate(alpha, beta): Retorna um número float aleatório com distribuição Beta.
- #expovariate(lambd): Retorna um número float aleatório com distribuição Exponencial.
- #gammavariate(alpha, beta): Retorna um número float aleatório com distribuição Gama.
- #gauss(mu, sigma): Retorna um número float aleatório com distribuição Gaussiana (Normal).
- #lognormvariate(mu, sigma): Retorna um número float aleatório com distribuição Lognormal.
- #normalvariate(mu, sigma): Retorna um número float aleatório com distribuição Normal.
- #vonmisesvariate(mu, kappa): Retorna um número float aleatório com distribuição Von Mises.
- #paretovariate(alpha): Retorna um número float aleatório com distribuição de Pareto.
- #weibullvariate(alpha, beta): Retorna um número float aleatório com distribuição Weibull.

#### 2. **Funções de Distribuições**

- #triangular(low, high, mode): Retorna um número float aleatório com distribuição triangular.
- #choices(population, weights=None, *, cum_weights=None, k=1): Retorna uma lista com `k` elementos escolhidos aleatoriamente da `population`, com a possibilidade de aplicar pesos.

#### 3. **Funções Utilitárias**

- #random(): Retorna um número float aleatório entre 0.0 e 1.0.
- #seed(a=None, version=2): Inicializa o gerador de números aleatórios.
- #getstate(): Retorna o estado interno do gerador de números aleatórios.
- #setstate(state): Define o estado interno do gerador de números aleatórios.

#### 4. **Constantes**

- Não há constantes definidas na biblioteca `random`, mas é comum definir valores como a semente (`seed`) para controlar a reprodutibilidade de sequências aleatórias.