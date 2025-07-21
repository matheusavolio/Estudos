### Aula 111 - Instanciando data-hora

Este código faz uso da API de data e hora introduzida no Java 8, especificamente as classes do pacote `java.time`. Essa API oferece uma maneira simplificada e mais poderosa para trabalhar com datas e horários.

#### Explicação detalhada dos métodos e classes usados:

1. **`Instant`**:
    
    - Representa um ponto no tempo global com precisão de nanossegundos, baseado no fuso horário UTC (Coordinated Universal Time).
    - **Exemplo**:
        
        ```java
        Instant d03 = Instant.now(); // Data-hora global atual`
        ```
        O `Instant.now()` obtém a data e hora atuais no fuso horário UTC.
2. **`LocalDate`**:
    
    - Representa uma data sem a hora, como "2024-09-22".
    - **Exemplo**:
        
        ```java
        LocalDate d01 = LocalDate.now(); // Data local atual
        ```
        O método `LocalDate.now()` obtém a data atual no sistema local.
3. **`LocalDateTime`**:
    
    - Representa tanto a data quanto a hora local, sem fuso horário.
    - **Exemplo**:
        

        ```java
    LocalDateTime d02 = LocalDateTime.now(); // Data-hora local atual`
        ```
        `LocalDateTime.now()` retorna a data e hora do sistema local, sem levar em conta fusos horários globais.
4. **`DateTimeFormatter`**:
    
    - Permite definir um formato customizado para exibir datas e horas.
    - **Exemplo**:
        
        ```java
   DateTimeFormatter fmt2 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm");
        ```
        Esse método define um padrão de formatação que inclui dia/mês/ano e hora
        
        .
5. **`parse()`**:
    
    - É usado para converter uma string representando uma data/hora em um objeto `LocalDate`, `LocalDateTime` ou `Instant`.
    - **Exemplo**:
        
        ```java
        LocalDate d04 = LocalDate.parse("2024-09-22");`
        ```
        A string "2024-09-22" é convertida em um objeto `LocalDate` correspondente.
6. **`of()`**:
    
    - O método `of()` permite criar uma instância de `LocalDate` ou `LocalDateTime` passando os valores de dia, mês, ano e, no caso de `LocalDateTime`, hora e minuto.
    - **Exemplo**:
        
        ```java
    LocalDate d10 = LocalDate.of(2024, 7, 20); 
    // Instancia uma data específica 
        
    LocalDateTime d11 = LocalDateTime.of(2024, 7, 20, 1, 30); 
    // Data e hora específica`
        ```

#### Situações em que você pode usar:

- **`LocalDate`**: para armazenar datas sem preocupação com o horário, como data de nascimento.
- **`LocalDateTime`**: quando você precisa da data e hora, mas não precisa considerar fusos horários.
- **`Instant`**: quando precisa trabalhar com uma marcação global de tempo.

### Aula 112 - Convertendo data-hora para texto

Este trecho de código demonstra como converter objetos de data-hora em strings formatadas.

#### Explicação detalhada dos métodos e classes usados:

1. **`format()`**:
    
    - Usado para converter um objeto `LocalDate`, `LocalDateTime` ou `Instant` para uma string formatada de acordo com um padrão específico.
    - **Exemplo**:
        
```java
        
System.out.println("D01 = " + d01.format(fmt1)); 
// Formata a data para o padrão "dd/MM/yyyy"`
        ```
2. **Formatadores padrões e customizados**:
    
    - **Exemplo**:
        
        ```java
DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy"); DateTimeFormatter fmt3 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm").withZone(ZoneId.systemDefault());
      ```  
        O método `withZone(ZoneId.systemDefault())` define um fuso horário, o que é essencial quando lidamos com `Instant` (hora global).

#### Situações em que você pode usar:

- Quando precisa exibir datas e horas de forma legível para os usuários.
- Quando você deseja apresentar horários convertidos para o fuso horário do sistema local.

### Aula 113 - Convertendo data-hora local para global

Neste trecho, aprendemos como converter uma data-hora global (representada por `Instant`) para uma data-hora local, levando em conta diferentes fusos horários.

#### Explicação detalhada dos métodos e classes usados:

1. **`ofInstant()`**:
    
    - Converte uma instância de `Instant` em `LocalDate` ou `LocalDateTime` ajustando-a para um fuso horário específico.
    - **Exemplo**:
        
        ```java
        LocalDateTimeR2=LocalDateTime.ofInstant(d03,ZoneId.of("Europe/London")); 
LocalDateTimeR3=LocalDateTime.ofInstant(d03,ZoneId.of("America/Sao_Paulo"));
      ```  
        Aqui, o `Instant d03` é convertido para o horário local de Londres e São Paulo, levando em conta os fusos horários.
2. **`getDayOfMonth()`, `getMonthValue()`, `getYear()`**:
    
    - Esses métodos permitem extrair o dia, mês e ano de uma instância `LocalDate`.
    - **Exemplo**:
        
        ```java
        System.out.println("d01 dia = " + d01.getDayOfMonth());`
        ```
3. **`getAvailableZoneIds()`**:
    
    - Retorna uma lista com todos os fusos horários disponíveis.
    - **Exemplo**:
    
        ```java
	    for (String s: ZoneId.getAvailableZoneIds()) {     
	        System.out.println(s);   }`
       ``` 

#### Situações em que você pode usar:

- Quando precisa converter um evento global para um horário local.
- Quando precisa lidar com múltiplos fusos horários e ajustá-los corretamente para diferentes regiões.


### Resumo dos métodos:
### 1. **Conversão de `Instant` para `LocalDate` e `LocalDateTime`**

#### #Instant #LocalDate #LocalDateTime 
- **`LocalDate.ofInstant(Instant, ZoneId)`**  
    Converte um objeto `Instant` (representando uma data-hora global) para um `LocalDate` (data local), levando em consideração um fuso horário especificado.
    
- **`LocalDateTime.ofInstant(Instant, ZoneId)`**  
    Converte um objeto `Instant` para um `LocalDateTime` (data e hora local), também baseado em um fuso horário específico.
    

### 2. **Métodos de Extração de Informações de `LocalDate`**

- **`getDayOfMonth()`**  
    Retorna o dia do mês a partir de um objeto `LocalDate`.
    
- **`getMonthValue()`**  
    Retorna o valor numérico do mês (1 a 12) de um objeto `LocalDate`.
    
- **`getYear()`**  
    Retorna o ano correspondente da data armazenada em um `LocalDate`.
    

### 3. **Métodos de Extração de Informações de `LocalDateTime`**

- **`getHour()`**  
    Retorna a hora de um objeto `LocalDateTime`.
    
- **`getMinute()`**  
    Retorna os minutos de um objeto `LocalDateTime`.
    
- **`getSecond()`**  
    Retorna os segundos de um objeto `LocalDateTime`.
    

### 4. **Outros Métodos Relacionados a Fusos Horários**

- **`ZoneId.getAvailableZoneIds()`**  
    Retorna uma lista com os identificadores de todos os fusos horários disponíveis no sistema.

---
---

### Aula113 - #CálculosComData-Hora
#### Importações

```java
import java.time.Duration; 
import java.time.Instant; 
import java.time.LocalDate; 
import java.time.LocalDateTime; 
import java.time.temporal.ChronoUnit;`
```

Essas importações trazem as classes necessárias para trabalhar com datas, horas, fusos horários, e durações:

- **`LocalDate`**: Representa uma data (ano, mês e dia), sem horário.
- **`LocalDateTime`**: Representa data e hora (ano, mês, dia, hora, minuto, etc.).
- **`Instant`**: Representa um ponto específico na linha do tempo (instante), com fuso horário UTC (tempo universal coordenado).
- **`Duration`**: Representa uma duração entre dois instantes de tempo.
- **`ChronoUnit`**: Permite trabalhar com unidades de tempo (dias, horas, minutos, etc.) em operações.

#### Instanciando Objetos com Datas e Horas

```java
LocalDateTime d002 = LocalDateTime.parse("2004-12-02T06:30"); LocalDate d01 = LocalDate.parse("2024-09-24"); 
LocalDateTime d02 = LocalDateTime.parse("2024-09-22T13:25"); 
Instant d03 = Instant.parse("2024-09-22T13:25:09Z");`
```

Aqui são criados objetos para representar datas e horas usando os métodos `parse()`:

- **`d002`**: Representa a data e hora `2004-12-02T06:30`.
- **`d01`**: Representa apenas a data `2024-09-24`.
- **`d02`**: Representa a data e hora `2024-09-22T13:25`.
- **`d03`**: Representa um instante de tempo no formato UTC (padrão ISO 8601).

### #OperaçõesComDatasHoras

#### Subtraindo e Somando Dias

```java
LocalDate pasWeekLocalDate = d01.minusDays(7);  
LocalDate nextWeekLocalDate = d01.plusDays(7); 
LocalDate nextYearLocalDate = d01.plusYears(7);`
```

- **`minusDays(7)`**: Subtrai 7 dias de `d01`, retornando a data correspondente a 7 dias atrás.
- **`plusDays(7)`**: Adiciona 7 dias a `d01`, retornando a data correspondente a 7 dias à frente.
- **`plusYears(7)`**: Adiciona 7 anos a `d01`.

Essas operações são possíveis porque `LocalDate` e `LocalDateTime` são imutáveis, ou seja, os métodos retornam novos objetos com as alterações, mantendo os originais intactos.

#### Subtraindo e Somando Horas e Minutos

```java
LocalDateTime nextHourLocalDateTime = d02.minusHours(7); 
LocalDateTime nextMinuteLocalDateTime = d02.minusMinutes(7);`
```

Aqui, subtraímos horas e minutos de um objeto `LocalDateTime`:

- **`minusHours(7)`**: Subtrai 7 horas da data e hora `d02`.
- **`minusMinutes(7)`**: Subtrai 7 minutos da data e hora `d02`.

#### Manipulando Instantes de Tempo

```java
Instant pastWeekInstant = d03.minus(7, ChronoUnit.DAYS); Instant nextWeekInstant = d03.plus(7, ChronoUnit.DAYS);`
```

Aqui, utilizamos a classe **`Instant`** para calcular instantes de tempo:

- **`minus(7, ChronoUnit.DAYS)`**: Subtrai 7 dias do instante `d03`.
- **`plus(7, ChronoUnit.DAYS)`**: Adiciona 7 dias ao instante `d03`.

### Operações com Duração

#### Calculando Duração entre Datas

```java
Duration t1 = Duration.between(d002, d02); System.out.println("LocalDateTime -> Duração entre d001 e d002 = " + t1.toDays());`
```

Aqui, utilizamos o método `Duration.between()` para calcular a diferença entre duas datas-horas (`d002` e `d02`). O método `toDays()` retorna a duração em dias.

#### Calculando Duração com `Instant` e `LocalDate`

```java
Duration t2 = Duration.between(pasWeekLocalDate.atStartOfDay(), d01.atStartOfDay()); 
System.out.println("LocalDate -> Duração entre passWeekLocalDate e d01 = "+t2.toDays());  

Duration t3 = Duration.between(pastWeekInstant, d03); System.out.println("Instant -> duração entre passWeekInstant e d03 = "+t3.toDays());`
```

- **`atStartOfDay()`**: Converte um objeto `LocalDate` para `LocalDateTime` começando à meia-noite, necessário para realizar o cálculo da duração.
- **`Duration.between()`**: Calcula a duração entre dois instantes (ou datas).

### Resumo dos Métodos

- **`LocalDate.now()` e `LocalDateTime.now()`**: Retornam a data ou data-hora atual.
- **`parse()`**: Converte uma string em uma instância de `LocalDate`, `LocalDateTime` ou `Instant` de acordo com o padrão ISO.
- **`minus()` e `plus()`**: Subtraem ou adicionam unidades de tempo a uma data ou hora (dias, horas, anos, etc.).
- **`Duration.between()`**: Calcula a duração entre dois pontos no tempo.
- **`toDays()`**: Converte a duração para dias.