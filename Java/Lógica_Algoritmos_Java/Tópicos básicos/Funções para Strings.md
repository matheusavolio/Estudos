# Aula59 - Funções interessantes para String

Funções para formatar:
```java
toLowerCase() // transforma em minusculo
toUpperCase() // transforma em maiusculo
trim() // remove espaços
```

Recortar:
```java
substring(inicio)
substring(inicio, fim)
```

Substituir
```java
Replace(char, char) // substitui caractere por outro caractere especificado
Replace(String, String) // substitui string por outra string especificada
```

Buscar
```java
indexOf
LastIndexOf
```

Recortar com base em um separador informado dentro de parêntesis 
```java
str.Split("")
```

Sintaxes: 
```java
        // Funções para formatar
		String s01 = original.toLowerCase(); // transforma tudo em minusculo
        String s02 = original.toUpperCase(); // transforma tudo em maiusculo

  
        // Função para retirar espaços extras do começo e do fim
        String s03 = original.trim();

  
        // Funções para recortar
        String s04 = original.substring(2); // recorta todos os caracteres até chegar no  índice especificado
        String s05 = original.substring(6, 11); // recorta todos os caracteres que não estão entre o intervalo especificado

  
        // funções para substituir
        // serve tanto para converter strings para números, ou char para número,
        // ou substituir uma string ou um char por um outro
        String s06 = original.replace('o', '1'); // substitui todos os caracteres "o" por char "1"
        String s07 = original.replace("wor", "123"); // substitui todas as strings que tem "wor" por "123"

  
        // encontra a posição do char dentro da String
        int s08 = original.indexOf("world"); // imprime o número do índice em que começa a string especificada
        int s09 = original.lastIndexOf("world"); // imprime o número do índice da ultima ocrrência da string especificada


// vetor -> estrutura indexada que separa elementos por meio de índices
// split     [0]    [1]    [2]
        String s = "potato apple lemon";
        String[] vect = s.split(" "); // separa as strings em diferentes listas 'vetores?'
        String word1 = vect[0]; // vect -> é a lista
        String word2 = vect[1];
        String word3 = vect[2];

```
