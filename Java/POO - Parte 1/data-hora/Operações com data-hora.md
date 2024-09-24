# Aula114 - Operações com data-hora
```java
import java.time.Duration;  
import java.time.Instant;  
import java.time.LocalDate;  
import java.time.LocalDateTime;  
import java.time.temporal.ChronoUnit;  
  
public class Program {  
    public static void main(String[] args) {  
        LocalDateTime d002 = LocalDateTime.parse("2004-12-02T06:30");  
        LocalDate d01 = LocalDate.parse("2024-09-24");  
        LocalDateTime d02 = LocalDateTime.parse("2024-09-22T13:25");  
        Instant d03 = Instant.parse("2024-09-22T13:25:09Z");  
  
        LocalDate pasWeekLocalDate = d01.minusDays(7); // os dias menos os dias dentro do parâmetro  
        LocalDate nextWeekLocalDate = d01.plusDays(7); // os dias mais os dias especificados dentro do parâmetro  
        LocalDate nextYearLocalDate = d01.plusYears(7); // os dias mais os dias especificados dentro do parâmetro  
        System.out.println("Padrão = " + d01);  
        System.out.println("Subtraindo dias LocalDate = " + pasWeekLocalDate);  
        System.out.println("Adicionando dias LocalDate= " + nextWeekLocalDate);  
        System.out.println("Adicionando anos LocalDate = " + nextYearLocalDate);  
  
        LocalDateTime pasWeekLocalDateTime = d02.minusDays(7); // os dias menos os dias dentro do parâmetro  
        LocalDateTime nextWeekLocalDateTime = d02.plusDays(7); // os dias mais os dias especificados dentro do parâmetro  
        LocalDateTime nextHourLocalDateTime = d02.minusHours(7); // as horas menos as horas especificados dentro do parâmetro  
        LocalDateTime nextMinuteLocalDateTime = d02.minusMinutes(7); // os minutos menos os minutos especificados dentro do parâmetro  
        System.out.println("Menos 7 dias LocalDateTime = "+ pasWeekLocalDateTime);  
        System.out.println("Mais 7 dias = "+nextWeekLocalDateTime);  
        System.out.println("Menos 7 horas LocalDateTime = "+nextHourLocalDateTime);  
        System.out.println("Menos 7 minutos LocalDateTime = "+nextMinuteLocalDateTime);  
  
        Instant pastWeekInstant = d03.minus(7, ChronoUnit.DAYS);  
        Instant nextWeekInstant = d03.plus(7, ChronoUnit.DAYS);  
        System.out.println("PastWeekInstant = "+pastWeekInstant);  
        System.out.println("NextWeekInstant = "+nextWeekInstant);  
  
        Duration t1 = Duration.between(d002, d02);  
        System.out.println("LocalDateTime -> Duração entre d001 e d002 = " + t1.toDays());  
  
        // não é possível calcular tempo entre dois LocalDate, temos que converter para LocalDateTime  
        Duration t2 = Duration.between(pasWeekLocalDate.atStartOfDay(), d01.atStartOfDay());  
        System.out.println("LocalDate -> Duração entre passWeekLocalDate e d01 = "+t2.toDays());  
  
        Duration t3 = Duration.between(pastWeekInstant, d03);  
        System.out.println("Instant -> duração entre passWeekInstant e d03 = "+t3.toDays());  
  
        Duration t4 = Duration.between(d03, pastWeekInstant);  
        System.out.println("Instant -> duração entre d03 e passWeekInstant = "+t4.toDays());  
    }  
}
```