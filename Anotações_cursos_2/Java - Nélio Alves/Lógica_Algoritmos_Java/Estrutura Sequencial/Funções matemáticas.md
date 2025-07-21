# Aula28 - Funções matemáticas


| Exemplo:              | Singnificado                                   |
| --------------------- | ---------------------------------------------- |
| _A = Math.sqrt(x);_   | Variável A recebe raiz quadrada de x           |
| _A = Math.pow(x, y);_ | Variável A recebe o resultado de x elevado a y |
| _A = Math.abs(x);_    | Variável A recebe o valor absoluto de x        |
`Valor abosluto -> Retirar sinal negativo do número, caso exista`

E é possível fazer equações mais complexas 
Por exemplo a formula de baskhara:
```java
delta = Math.pow(b, 2.0) - 4*a*c; 

x1 = (-b + Math.sqrt(delta)) / (2.0 * a); 
x2 = (-b - Math.sqrt(delta)) / (2.0 * a);
```

### Funções Aritméticas
1. **`Math.abs(x)`**: Retorna o valor absoluto de `x` (ignora o sinal).
    
    - Exemplo: `Math.abs(-5)` retorna `5`.
2. **`Math.max(x, y)`**: Retorna o maior valor entre `x` e `y`.
    
    - Exemplo: `Math.max(5, 10)` retorna `10`.
3. **`Math.min(x, y)`**: Retorna o menor valor entre `x` e `y`.
    
    - Exemplo: `Math.min(5, 10)` retorna `5`.
4. **`Math.pow(x, y)`**: Retorna `x` elevado à potência de `y`.
    
    - Exemplo: `Math.pow(2, 3)` retorna `8.0`.
5. **`Math.sqrt(x)`**: Retorna a raiz quadrada de `x`.
    
    - Exemplo: `Math.sqrt(16)` retorna `4.0`.
6. **`Math.cbrt(x)`**: Retorna a raiz cúbica de `x`.
    
    - Exemplo: `Math.cbrt(27)` retorna `3.0`.
7. **`Math.exp(x)`**: Retorna `e` elevado à potência de `x` (exponencial).
    
    - Exemplo: `Math.exp(1)` retorna `2.718281828459045`.
8. **`Math.log(x)`**: Retorna o logaritmo natural (base `e`) de `x`.
    
    - Exemplo: `Math.log(2.71828)` retorna `1.0`.
9. **`Math.log10(x)`**: Retorna o logaritmo de base 10 de `x`.
    
    - Exemplo: `Math.log10(100)` retorna `2.0`.
10. **`Math.log1p(x)`**: Retorna o logaritmo natural de `1 + x`.
    
    - Exemplo: `Math.log1p(1)` retorna `0.6931471805599453`.

### Funções Trigonométricas

1. **`Math.sin(x)`**: Retorna o seno de `x`, onde `x` é em radianos.
    
    - Exemplo: `Math.sin(Math.PI / 2)` retorna `1.0`.
2. **`Math.cos(x)`**: Retorna o cosseno de `x`, onde `x` é em radianos.
    
    - Exemplo: `Math.cos(0)` retorna `1.0`.
3. **`Math.tan(x)`**: Retorna a tangente de `x`, onde `x` é em radianos.
    
    - Exemplo: `Math.tan(Math.PI / 4)` retorna `1.0`.
4. **`Math.asin(x)`**: Retorna o arco seno de `x` em radianos.
    
    - Exemplo: `Math.asin(1)` retorna `π/2`.
5. **`Math.acos(x)`**: Retorna o arco cosseno de `x` em radianos.
    
    - Exemplo: `Math.acos(1)` retorna `0.0`.
6. **`Math.atan(x)`**: Retorna o arco tangente de `x` em radianos.
    
    - Exemplo: `Math.atan(1)` retorna `π/4`.
7. **`Math.atan2(y, x)`**: Retorna o arco tangente de `y/x` em radianos, considerando o sinal de ambos os argumentos.
    
    - Exemplo: `Math.atan2(1, 1)` retorna `π/4`.
8. **`Math.toRadians(x)`**: Converte graus para radianos.
    
    - Exemplo: `Math.toRadians(180)` retorna `π`.
9. **`Math.toDegrees(x)`**: Converte radianos para graus.
    
    - Exemplo: `Math.toDegrees(Math.PI)` retorna `180.0`.

### Funções Exponenciais e Logarítmicas

1. **`Math.exp(x)`**: Retorna `e` elevado à potência de `x`.
    
    - Exemplo: `Math.exp(2)` retorna `7.3890560989306495`.
2. **`Math.expm1(x)`**: Retorna `e^x - 1`, mais preciso para valores pequenos de `x`.
    
    - Exemplo: `Math.expm1(0.1)` retorna `0.10517091807564763`.
3. **`Math.hypot(x, y)`**: Calcula a hipotenusa (raiz quadrada de `x² + y²`).
    
    - Exemplo: `Math.hypot(3, 4)` retorna `5.0`.

### Funções de Arredondamento

1. **`Math.round(x)`**: Arredonda `x` para o inteiro mais próximo.
    
    - Exemplo: `Math.round(5.5)` retorna `6`.
2. **`Math.ceil(x)`**: Arredonda `x` para o menor inteiro mais próximo (sempre para cima).
    
    - Exemplo: `Math.ceil(5.1)` retorna `6.0`.
3. **`Math.floor(x)`**: Arredonda `x` para o maior inteiro mais próximo (sempre para baixo).
    
    - Exemplo: `Math.floor(5.9)` retorna `5.0`.
4. **`Math.rint(x)`**: Retorna o inteiro mais próximo de `x` como valor do tipo `double`.
    
    - Exemplo: `Math.rint(5.5)` retorna `6.0`.
5. **`Math.copySign(x, y)`**: Retorna `x` com o sinal de `y`.
    
    - Exemplo: `Math.copySign(5, -3)` retorna `-5.0`.

### Funções Aleatórias

1. **`Math.random()`**: Retorna um valor aleatório entre `0.0` (inclusive) e `1.0` (exclusivo).
    - Exemplo: `Math.random()` pode retornar algo como `0.432167`.

### Funções Hiperbólicas

1. **`Math.sinh(x)`**: Retorna o seno hiperbólico de `x`.
    
    - Exemplo: `Math.sinh(0)` retorna `0.0`.
2. **`Math.cosh(x)`**: Retorna o cosseno hiperbólico de `x`.
    
    - Exemplo: `Math.cosh(0)` retorna `1.0`.
3. **`Math.tanh(x)`**: Retorna a tangente hiperbólica de `x`.
    
    - Exemplo: `Math.tanh(0)` retorna `0.0`.

### Constantes

1. **`Math.PI`**: A constante `π` (3.141592653589793).
2. **`Math.E`**: A constante `e` (2.718281828459045).