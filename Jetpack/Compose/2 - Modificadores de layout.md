
Os modificadores são usados para decorar ou adicionar comportamentos aos elementos da interface do Jetpack Compose. Por exemplo, você pode adicionar planos de fundo, padding ou comportamento a linhas, textos ou botões. Para fazer a configuração deles, um elemento combinável ou layout precisa aceitar um modificador como parâmetro.

Em um codelab anterior, você aprendeu sobre os modificadores e usou o de padding (`Modifier.padding`) para adicionar espaço ao redor do elemento combinável `Text`. Os modificadores podem ajudar muito, e você verá isso neste e nos próximos programas de aprendizagem.

Por exemplo, o elemento combinável `Text` tem um argumento `Modifier` que muda a cor do plano de fundo para verde.

```Kotlin
//Example
Text(
    text = "Hello, World!",
    // Solid element background color
    modifier = Modifier.background(color = Color.Green)
)
```

Assim como no exemplo acima, você pode adicionar modificadores a layouts para posicionar os elementos filhos usando propriedades de organização e alinhamento.

Para definir a posição dos filhos em uma [`Row`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Row(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Horizontal,androidx.compose.ui.Alignment.Vertical,kotlin.Function1)), defina os argumentos `horizontalArrangement` e `verticalAlignment`. Para uma [`Column`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Column(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Vertical,androidx.compose.ui.Alignment.Horizontal,kotlin.Function1)), defina os argumentos `verticalArrangement` e `horizontalAlignment`.

A propriedade de organização é usada para dispor os elementos filhos quando o tamanho do layout é maior que a soma dos filhos.

Por exemplo: quando o tamanho da [`Column`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Column(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Vertical,androidx.compose.ui.Alignment.Horizontal,kotlin.Function1)) é maior que a soma dos tamanhos dos filhos, uma [`verticalArrangement`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Column(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Vertical,androidx.compose.ui.Alignment.Horizontal,kotlin.Function1)) pode ser especificada para definir o posicionamento do elementos filhos na `Column`. Veja abaixo uma ilustração dos diferentes arranjos verticais:

![mesma altura, espaçamento, espaço ao redor, espaçamento uniforme, em cima, no centro e embaixo](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-add-images/img/df69881d07b064d0.gif?hl=pt-br)

Da mesma forma, quando o tamanho da [`Row`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Row(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Horizontal,androidx.compose.ui.Alignment.Vertical,kotlin.Function1)) é maior que a soma dos tamanhos dos filhos, uma `horizontalArrangement` pode ser especificada para definir o posicionamento dos filhos dentro da `Row`. Verifique abaixo uma ilustração das diferentes organizações horizontais:

![peso igual, espaçamento, espaço ao redor, espaçamento uniforme, fim, centro e início](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-add-images/img/c1e6c40e30136af2.gif?hl=pt-br)

A propriedade de alinhamento é usada para alinhar os elementos filhos no início, no centro ou no fim do layout.