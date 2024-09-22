# Aula107 - Introdução a #data-hora e duração

- *Data-[hora] local:*
	- ano-mês-dia-[hora] sem fuso horário
	- [hora] opcional
- *Data-hora global*
	- ano-mês-dia-hora com fuso horário
- *Duração:*
	- tempo decorrido entre duas datas-horas

![[data-hora.jpg]]
### Quando usar:

- *Data-hora local:*
	- Quando o momento exato não interessa a pessoas de outro fuso horário.
	- Uso comum:
		- Data de nascimento: "15/06/2001"
		- Data-hora da venda: "13/08/2022 às 15:32 (presumindo não interessar o fuso horário)"
- *Data-hora global:*
	- Quando o momento exato interessa a pessoas de outro fuso horário.
	- Uso comum:
		- Quando será o sorteio? "21/08/2022 às 20h (horário de Brasília)"
		- Quando o comentário foi postado? "hà 17 minutos"
		- Quando foi realizada a venda? "13/08:2022 às 15:32 (horário de São Paulo)"
		- Início e fim o evento? "21/08/2022 às 14h até as 16h (horário de São Paulo)"  

# Aula108 - Entendo a #timezone (fuso-horário)

### *Timezone (fuso-horário)*
-  #GMT - Greenwich Mean Time 
	- Horário de Londres
	- Horário do padrão UTC - Coordinated Universal Time
	- Também chamado de "Z" time, ou Zulu Time
- *Outros fusos horários são relativos ao GMT/UTC*
	- São Paulo: GMT-3
	- Manaus: GMT-4
	- Portugal: GMT+1
- *Muitas linguagens/tecnologias usam nomes para as timezones:*
	- "US/Pacifc"
	- "America/Sao_Paulo"
	- etc.

---
---

# Aula109 - Padrão #ISO8601

Especifica como devem ser representados datas e horas em forma de texto.

#### *Padrão ISO 8601:*
- #Data-hora local:
	- 2022-07-21
	- 2022-07-21T14:52
	- 2022-07-22T14:52:09
	- 2022-07-22T14:52:09.4073
- Data-hora global:
	- 2022-07-23T14:52:09Z
	- 2022-07-23T14:52:09.254935Z
	- 2022-07-23T14:52:09-03:00

---
---

# Aula110 - Operações importantes com data-hora

- *Instanciação*
	- (agora) -> Data-hora
	- Texto ISO 8601-> Data-hora
	- Texto formato customizado -> Data-hora
	- dia, mês, ano, [horário] -> Data-hora local
- *Formatação*
	- Data-hora -> Texto ISO 8601
	- Data-hora Texto formato customizado
- *Obter dados de uma data-hora local*
	- Data-hora local -> dia, mês, ano, horárip
- *Converter data-hora global para local*
	- Data-hora global, timezone, (sistema local) -> Data-hora local
- *Cálculos com Data-hora*
	- Data-hora +/- tepo -> Data-hora
	- Data-hora 1, Data-hora 2 -> duração


# Aula111 - Instanciando data-hora 

- *Data-hora local*
	- #LocalDate
	- #LocalDateTime
- *Data-hora global*
	- #Instant
- *Duração*
	- #Duration
- *Outros*
	- #Zoneld
	- #ChronoUnit


#### *Instanciação*
```java
import java.time.Instant; // data-hora global atual  
import java.time.LocalDate; // data atual local  
import java.time.LocalDateTime; // data-hora atual local  
import java.time.format.DateTimeFormatter; // definir um fornato personalizado

// instanciando formatação personalizada de data  
// DateTimeFormatter fmt1 = DateTimeFormatter.ofPattern("dd/MM/yyyy");  
  
// instanciando formatação personalizada de data-hora  
DateTimeFormatter fmt2 = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm");  
  
// Data atual local  
LocalDate d01 = LocalDate.now();  
  
// Data-hora atual local  
LocalDateTime d02 = LocalDateTime.now();  
  
// data-hora global  
Instant d03 = Instant.now(); // data-hora global padrão -> londres  
  
// data personalizada padrão ISO 8601  
LocalDate d04 = LocalDate.parse("2024-09-22");  
  
// Data-hora personalizada  
LocalDateTime d05 = LocalDateTime.parse("2024-09-22T13:25");  
  
// Data-hora global personalizada  
Instant d06 = Instant.parse("2024-09-22T13:25:09Z");  
  
// Especificando um timezone diferente  
Instant d07 = Instant.parse("2024-09-22T13:25:09-03:00");  
  
// Especificando formato personalizado  
// podemos também inserir a chamada direta da formatação ao invés de instanciar ela  
LocalDate d08 = LocalDate.parse("20/07/2022", DateTimeFormatter.ofPattern("dd/MM/yyyy"));  
  
// data-hora formatada  
LocalDateTime d09 = LocalDateTime.parse("20/07/2022 01:30", fmt2);  
  
// instancia dia, mês e ano isoladamente  
LocalDate d10 = LocalDate.of(2024, 7, 20);  
  
// intancia dia, mês, ano e horário isoladamente  
LocalDateTime d11 = LocalDateTime.of(2024, 7, 20, 1, 30);
```
