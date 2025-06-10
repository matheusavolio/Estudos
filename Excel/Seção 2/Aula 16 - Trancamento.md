### #Trancamento - Referência absoluta

quando vamos replicar as fórmulas de uma célula arrastando o canto inferior direito, pode dar um erro quando toda a fórmula se baseia na informação que contém em uma célula e queremos manter uma referência absoluta.
Por exemplo, se tivermos um número na célula A1, e queremos multiplicar 3 linhas de uma coluna pelo valor da célula A1, quando formos arrastar para copiar a fórmula da célula já feita irá apresentar um erro.
É nisso que aparece o #Trancamento que utilizamos nesses casos, 
```Excel
Basta apenas selecionar a referência absoluta dentro da primeira fórmula, e apertar F4
```
