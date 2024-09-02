Quando ocorre um erro que não se dá de forma sintática, o nome não é erro, e sim exceção.
Por exemplo, quando você digita uma string no input que pede um int, ocorre um ValueError, que no caso, é uma excessão.
```python
n = int(input("Valor: "))
print(f"VocÊ digitou {n}")
output:

Valor: ola
Traceback (most recent call last):
  File "d:\Estudos-Python\Estudos-Python\Treinos\tratamento_erros.py", line 1, in <module>
    n = int(input("Valor: "))
        ^^^^^^^^^^^^^^^^^^^^^
ValueError: invalid literal for int() with base 10: 'ola'
```


# Lista de exceções:

1. **BaseException**: Classe base para todas as exceções.
2. **Exception**: Classe base para todas as exceções que não sejam de saída do sistema.
3. **ArithmeticError**: Classe base para todas as exceções numéricas.
    - **OverflowError**: Ocorre quando um cálculo numérico resulta em um valor que é muito grande para ser representado.
    - **ZeroDivisionError**: Ocorre quando se tenta dividir um número por zero.
    - **FloatingPointError**: Ocorre quando uma operação em ponto flutuante falha.
4. **BufferError**: Ocorre quando uma operação relacionada ao buffer falha.
5. **LookupError**: Classe base para todas as exceções de pesquisa.
    - **IndexError**: Ocorre quando um índice de sequência é inválido.
    - **KeyError**: Ocorre quando uma chave de dicionário não é encontrada.
6. **AssertionError**: Ocorre quando uma instrução `assert` falha.
7. **AttributeError**: Ocorre quando um atributo de objeto não pode ser encontrado.
8. **EOFError**: Ocorre quando a função `input()` atinge o final do arquivo sem receber dados.
9. **ImportError**: Ocorre quando a importação de um módulo falha.
    - **ModuleNotFoundError**: Subclasse de `ImportError` que é levantada quando o módulo especificado não pode ser encontrado.
10. **MemoryError**: Ocorre quando uma operação não pode ser completada devido à falta de memória.
11. **NameError**: Ocorre quando uma variável local ou global não é encontrada.

- **UnboundLocalError**: Subclasse de `NameError` que ocorre quando uma variável local é referenciada antes de ser atribuída.

12. **OSError**: Classe base para erros relacionados ao sistema operacional.
    - **FileNotFoundError**: Ocorre quando um arquivo ou diretório é solicitado, mas não pode ser encontrado.
    - **PermissionError**: Ocorre quando uma operação tenta acessar um arquivo sem a devida permissão.
    - **TimeoutError**: Ocorre quando uma operação do sistema atinge o tempo limite.
13. **ReferenceError**: Ocorre quando uma referência fraca é usada para acessar um objeto que já foi coletado pelo garbage collector.
14. **RuntimeError**: Ocorre quando um erro geral não se encaixa em nenhuma outra categoria.
    - **NotImplementedError**: Ocorre quando uma parte do código é chamada, mas não está implementada.
    - **RecursionError**: Ocorre quando o limite máximo de recursão é excedido.
15. **StopIteration**: Ocorre para indicar o final de uma iteração.
16. **SyntaxError**: Ocorre quando há um erro na sintaxe do código Python.
    - **IndentationError**: Ocorre quando há um erro de indentação.
        - **TabError**: Ocorre quando misturas incorretas de tabulação e espaço são usadas.
17. **SystemError**: Ocorre quando um erro do sistema Python é encontrado.
18. **TypeError**: Ocorre quando uma operação ou função é aplicada a um objeto de tipo inadequado.
19. **ValueError**: Ocorre quando uma operação ou função recebe um argumento com o tipo certo, mas com um valor inadequado.
20. **UnicodeError**: Classe base para exceções relacionadas à codificação e decodificação de Unicode.
    - **UnicodeEncodeError**: Ocorre quando uma string Unicode não pode ser codificada.
    - **UnicodeDecodeError**: Ocorre quando uma string Unicode não pode ser decodificada.
    - **UnicodeTranslateError**: Ocorre quando uma string Unicode não pode ser traduzida.

### Exceções de Warnings

- **Warning**: Classe base para todas as advertências.
    - **DeprecationWarning**: Advertência sobre o uso de funcionalidades obsoletas.
    - **PendingDeprecationWarning**: Advertência para funcionalidades que estão sendo consideradas para obsolescência.
    - **RuntimeWarning**: Advertência sobre situações durante a execução.
    - **SyntaxWarning**: Advertência sobre sintaxe duvidosa.
    - **UserWarning**: Advertência gerada por código de usuário.
    - **FutureWarning**: Advertência para mudanças que ocorrerão no futuro.
    - **ImportWarning**: Advertência sobre problemas durante a importação de módulos.
    - **UnicodeWarning**: Advertência sobre problemas com Unicode.
    - **BytesWarning**: Advertência sobre operações de string e bytes.
    - **ResourceWarning**: Advertência sobre o uso de recursos.

para prevenir as exceções, utilizamos o #try e o #except 
exemplo: 
```python
try:
    a = int(input("Númerador: "))
    b = int(input("Denominador: "))
    r = a / b
except:
    print("Erro, não é possível fazer uma divisão por 0.")
else:
    print(f"O resultado é {r}")
```
se ocorrer uma exceção dentro do bloco try, a mensagem dentro de except é exibida
se não ocorrer nenhum erro no bloco try, a mensagem dentro do bloco else é impressa

```python
OUTPUT
Númerador: 10 # bloco try
Denominador: 5 # bloco try
O resultado é 2.0 # bloco else

OUTPUT 2
Númerador: 10 # bloco try
Denominador: 0 # bloco try
Erro, não é possível fazer uma divisão por 0. # bloco except
```

a clausula else, é opcional, nem sempre é preciso usar ela.
da mesma forma temos a clausula #finally 
```python
try:
    a = int(input("Númerador: "))
    b = int(input("Denominador: "))
    r = a / b
except:
    print("Erro, não é possível fazer uma divisão por 0.")
else:
    print(f"O resultado é {r}")
finally:
    print("Volte sempre!")
```
O código não mudou muita coisa, apenas foi adicionado a clausula finally, que será executada sempre, não importando se deu algum erro no caminho, ou não.
```python
OUTPUT
Númerador: 10 # try
Denominador: 5 # try
O resultado é 2.0  # else   
Volte sempre! # finaly

OUTPUT 2
Númerador: 10 # try
Denominador: 0 # try
Erro, não é possível fazer uma divisão por 0. # except
Volte sempre! # finally
```

também podemos capturar o nome do erro
```python
try:
    a = int(input("Númerador: "))
    b = int(input("Denominador: "))
    r = a / b
except Exception as erro:
    print(f"Problema encontrado foi: {erro.__class__}")
else:
    print(f"O resultado é {r}")
finally:
    print("Volte sempre!")
```
O código não mudou muito, porém na clausula #except adionamos o Exception e o renomeamos para erro, assim transformando em uma variável que podemos utilizar para capturar o erro, no caso acima, será exibida a classe do erro

```python
OUTPUT
Númerador: 10 # try
Denominador: 0 # try
Problema encontrado foi: <class 'ZeroDivisionError'> # except Exception
Volte sempre! # finally

OUTPUT 2
Númerador: 10 # try
Denominador: ola # try
Problema encontrado foi: <class 'ValueError'> # except Exception
Volte sempre! # finally
```

E um mesmo try, podemos ter vários except
```python
OUTPUT 1
Númerador: 7 # try
Denominador: 3 # try
O resultado é 2.3333333333333335 # else
Volte sempre! # finally

OUTPUT 2
Númerador: 8 # try
Denominador: dois # try
Tivemos um problema com o tipo de dado que você digitou. # except1 
Volte sempre! # finally

OUTPUT 3
Númerador: 10 # try
Denominador: 0 # try
Não é possível dividir um número por 0. # except 2
Volte sempre! # finally

OUTPUT 4
Númerador: 10 # try
Denominador: O usuário preferiu não informar os dados # except 3
Volte sempre! # finally

```