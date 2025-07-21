# #While/Else

Quando o laço #while é executado completamente, executa o laço do #else ao final de tudo.
Por exemplo:
`str = "Valor Qualquer`
`cont = 0`
`while cont <len(str)
	`letra = str[1`
	`print(letra)`
	`cont +=1
`else:`
	`print("O else foi executado")
	`print("fora do while")`

# No exemplo acima, enquanto o loop for true, ao final dele será executado o else, porém se em algum momento o loop for false, irá pular direto para o else.

`while condição:     
	 `Bloco de código do while     
	`Instruções aqui 
`else:     
	 `Bloco de código do else     
	 `` Instruções aqui`

- **`condição`**: É a expressão booleana que é avaliada antes de cada execução do bloco de código do `while`. Enquanto essa condição for verdadeira (`True`), o bloco de código dentro do `while` é executado repetidamente.
    
- **Bloco de código do `while`**: São as instruções que serão executadas repetidamente enquanto a condição especificada for verdadeira. Esse bloco deve ser indentado corretamente para indicar que está dentro do `while`.
    
- **`else`**: O bloco de código do `else` é opcional e é executado quando a condição do `while` se torna falsa (`False`). Isso significa que o `else` será executado quando o `while` terminar naturalmente, ou seja, quando a condição não for mais atendida.
    

### Funcionamento do `while/else`

O bloco de código do `else` será executado nas seguintes situações:

- **Condição Falsa**: Quando a condição do `while` se torna falsa, ou seja, quando a expressão booleana não é mais verdadeira.
- **Não interrupção por `break`**: Se o `while` terminar devido à conclusão normal da condição (sem um `break`), o bloco de código do `else` será executado.