# Aula57 - Restrições e convenções para nomes

- Não pode começar com dígito: Use uma letra ou _
- Não pode usar acentos ou ~
- Não pode ter espaço em branco
- Usar nomes que tenham significado

**Errado**
`int 5minutos;`
`int salário;`
`int salario do funcionario;`

**Correto**
`int _5minutos;`
`int salario;`
`int salarioDoFuncionario`

Utilizar sempre o padrão #CamelCase 
#### Convenções
- Camel Case -> lastName
	- pacotes
	- atributos
	- métodos
	- variáveis e parâmetros
- Pascal Case: ProductService
	- classes

---
---

# Aula58 - Operadores Bitwise

| Operador |            Significado            |
| :------: | :-------------------------------: |
|    &     |      Operação "E" bit a bit       |
|    \|    |      Operação "OU" bit a bit      |
|    ^     | Operação "OU-exclusivo bit a bit" |

---
---

# Aula60 - Comentários em Java (básico)

#### Comentário de bloco é composto por:
Utilizado para explicar um bloco de código
```java
/*
Comentário
por
bloco
*/
```

#### Comentário de linha:
Usado para explicar coisas dentro do código
```java
// comentario
// de 
// linha
```

#### #BoasPráticasComentários

É considerado boa pratica evitar colocar muitos comentários durante o código, e sempre tentar deixar o nome de suas funções e variáveis e mais autoexplicativo possível, para evitar colocar comentários explicando o que são.

---
---
