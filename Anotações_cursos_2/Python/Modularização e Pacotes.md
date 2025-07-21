Modularizar, é o conceito de construir módulos
Surgiu no início da década de 60 com os sistemas ficando cada vez maiores

- `Foco:` dividir um programa grande em pequenos pedaços
- `Foco:` Aumentar a legibilidade
- `Foco:` facilitar a manutenção

para o python, todo arquivo .py podem módulos.

```python
# ARQUIVO DO PROGRAMA PRINCIPAL MODULARIZACAO_TREINO.PY
import uteis
# programa principal
num = int(input("Digite um valor: "))
print(f"O fatorial de {num} é {uteis.fatorial(num)}")
print(f"O dobro de {num} é {uteis.dobro(num)}")
print(f"O triplo de {num} é {uteis.triplo(num)}")
print(f"O número {num} é {uteis.par_impar(num)}")
```

```python
# funções do programa principal
# ARQUIVO AONDE FICAM AS FUNÇÕES UTEIS.PY
def fatorial(n):
    f = 1
    for c in range(1, n + 1):
        f *= c
    return f
def dobro(n):
    return n * 2
def triplo(n):
    return n * 3
def par_impar (n):
    if n % 2 == 0:
        return "par"
    else:
        return "ímpar"
```
No programa principal, ficou apenas as chamadas das funções e impressões de resultado, ja no arquivo das funções, ficou todo o código.
E podemos modularizar apenas utilizando o import nome_do_arquivo

# Pacotes
Para criar pacotes é simples, basta criar uma pasta com o nome desejado do pacote, e dentro dessa pasta você cria outra pasta com o nome do módulo desejado, e dentro da pasta do módulo, você coloca o arquivo .py como `__init__.py`
ai ficou assim
`UTEIS`
	`|__NUMEROS`
		|_`__INIT__.PY
E podemos criar varios moduglos dentro do pacote
`UTEIS`
	`|__NUMEROS`
		|`__ `  `__INIT__.PY
	`STRINGS`
		|`__ ` `__INIT__.PY`

 e assim se segue.
 para importar o pacote é simples
` import nome_do_pacote`
 ou podemos importar apenas o módulo
` from nome_do_pacote import nome_do_modulo`
Exemplo:
`import uteis`

`from uteis import numeros`