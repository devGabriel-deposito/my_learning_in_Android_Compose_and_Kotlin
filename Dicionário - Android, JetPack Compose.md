- **modifier**: é uma coleção de elementos usados para decorar ou modificar o comportamento dos elementos da IU do Compose.
	- [`wrapContentSize()`](https://developer.android.com/reference/kotlin/androidx/compose/ui/Modifier?hl=pt-br#(androidx.compose.ui.Modifier).wrapContentSize(androidx.compose.ui.Alignment,kotlin.Boolean)) especifica que o espaço disponível precisa ser pelo menos tão grande quanto os componentes dentro dele. No entanto, como o método `fillMaxSize()` é usado, se os componentes dentro do layout forem menores que o espaço disponível, um objeto [`Alignment`](https://developer.android.com/reference/kotlin/androidx/compose/ui/Alignment?hl=pt-br) poderá ser transmitido ao método `wrapContentSize()` que especifica como os componentes precisam se alinhar dentro do espaço disponível.

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
