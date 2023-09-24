- **sp**: *scalable pixels (pixels escalonáveis)*.
	- São uma unidade de medida para tamanho da fonte de texto. Por padrão, a unidade SP é do mesmo tamanho que a DP, mas ela é redimensionada com base no tamanho de texto preferencial do usuário nas configurações do smartphone.

Exemplo:
```Kotlin
Text(
   text = message,
   fontSize = 100.sp
)
```



- **dp**: *density pixels (pixels de densidade independente)*.
	- São uma unidade de medida para tamanho da fonte de texto

Exemplo:
```Kotlin
Text(
   text = message,
   fontSize = 100.sp
)
```