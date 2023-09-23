## Hierarquia da interface

A hierarquia da interface é baseada em contenção, o que significa que um componente pode conter um ou mais componentes, e às vezes os termos pai e filho são usados. O contexto é que os elementos pais da interface têm elementos filhos, que por sua vez podem conter outros elementos filhos. Nesta seção, você vai aprender sobre os elementos combináveis `Column`, `Row` e `Box`, que podem atuar como elementos pais da interface.

![9270b7e10f954dcb.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/9270b7e10f954dcb.png?hl=pt-br)

Os três elementos básicos de layout padrão do Compose são [`Column`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Column(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Vertical,androidx.compose.ui.Alignment.Horizontal,kotlin.Function1)), [`Row`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Row(androidx.compose.ui.Modifier,androidx.compose.foundation.layout.Arrangement.Horizontal,androidx.compose.ui.Alignment.Vertical,kotlin.Function1)) e [`Box`](https://developer.android.com/reference/kotlin/androidx/compose/foundation/layout/package-summary?hl=pt-br#Box(androidx.compose.ui.Modifier,androidx.compose.ui.Alignment,kotlin.Boolean,kotlin.Function1)). Você vai saber mais sobre o elemento combinável `Box` no próximo codelab.

![coluna mostrando três elementos organizados verticalmente e uma linha mostrando três elementos organizados horizontalmente](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/51c199c8a23bd6a8.png?hl=pt-br)

`Column`, `Row` e `Box` são funções combináveis que usam conteúdo de composição como argumentos para que você possa colocar itens dentro desses elementos de layout. Por exemplo, cada elemento filho dentro de um elemento combinável `Row` é posicionado horizontalmente um ao lado do outro em uma linha.

```Kotlin
// Don't copy.
Row {
    Text("First Column")
    Text("Second Column")
}
```

Esses elementos de texto são mostrados lado a lado na tela, como visto nesta imagem.

As bordas azuis são apenas para fins demonstrativos e não são mostradas.

![5fd18dbcbee17ffd.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/5fd18dbcbee17ffd.png?hl=pt-br)

## Sintaxe de lambdas finais

No snippet de código anterior, são usadas chaves, em vez de parênteses, na função combinável `Row`. Isso é chamado de _sintaxe de lambdas finais_. Você vai aprender sobre _lambdas_ e sintaxe de lambdas finais em detalhes mais adiante no curso. Por enquanto, conheça esta sintaxe mais usada do Compose.

O Kotlin oferece uma sintaxe especial para transmitir funções como parâmetros para outras funções, quando o último parâmetro também é uma função.

![o parâmetro de função é o último parâmetro](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/496bc9b8f2dbd2c2.png?hl=pt-br)

Ao transmitir uma função como esse parâmetro, você pode usar a sintaxe de lambdas finais. Em vez de colocar o corpo da função junto ao nome dela entre parênteses (`{}`), coloque os parênteses com o corpo da função após o nome. Essa é uma prática comum e recomendada no Compose, então você precisa se familiarizar com a aparência do código.

Por exemplo, o último parâmetro na função combinável `Row()` é o parâmetro `content`, uma função que descreve os elementos de interface filhos. Suponha que você queira criar uma linha com três elementos de texto. Esse código funcionaria, mas seria muito complicado usar o parâmetro nomeado para a lambda final:

```Kotlin
Row(
    content = {
        Text("Some text")
        Text("Some more text")
        Text("Last text")
    }
)
```

O parâmetro `content` é o último na assinatura da função, e o valor dele é transmitido como uma expressão lambda. Por enquanto, não tem problema se você não souber o que é uma lambda, apenas conheça a sintaxe. É possível remover o parâmetro `content` e os parênteses desta maneira:

```Kotlin
Row {
    Text("Some text")
    Text("Some more text")
    Text("Last text")
}
```

## Organizar os elementos de texto em uma linha

Nesta tarefa, você organiza os elementos de texto no seu app em uma linha para evitar sobreposição.

1. No arquivo `MainActivity.kt`, role até a função `GreetingText()`.
2. Adicione o elemento combinável `Row` ao redor dos elementos de texto para que ele mostre uma linha com dois desses elementos. Selecione os dois combináveis `Text` e clique no ícone de lâmpada. Selecione **Surround with widget** > **Surround with Row**.

![6425f0ac8e0fb453.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/6425f0ac8e0fb453.png?hl=pt-br)

![31505d33fc2fcb97.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/31505d33fc2fcb97.png?hl=pt-br)

Agora, a função ficará parecida com este snippet de código:

```Kotlin
@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Row {
        Text(
            text = message,
            fontSize = 100.sp,
            lineHeight = 116.sp,
        )
        Text(
            text = from,
            fontSize = 36.sp
        )
    }
}
```

3. O Android Studio importa automaticamente a função `Row` para você. Role até a parte de cima e observe a seção de importação. O **`import`** `androidx.compose.foundation.layout.Row` deve ter sido adicionado.
4. Observe a prévia atualizada no painel **Design**. Mude temporariamente o tamanho da fonte da mensagem de aniversário para `30.sp`.

![A mensagem de aniversário e a assinatura são mostradas lado a lado em uma linha.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/6c96bec2beebb1ad.png?hl=pt-br)

A prévia parece muito melhor agora que não há sobreposição. No entanto, não é isso que você quer porque não há espaço suficiente para sua assinatura. Na próxima tarefa, você vai organizar os elementos de texto em uma coluna para resolver esse problema.

## Organizar os elementos de texto em uma coluna

Nesta tarefa, é sua vez de mudar a função `GreetingText()` para organizar os elementos de texto em uma coluna. A prévia vai ficar assim:

![Mensagem de aniversário e assinatura mostradas uma embaixo da outra em uma coluna.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/d5d4c5a752ca8274.png?hl=pt-br)

Agora que você já tentou fazer isso por conta própria, compare seu código ao da solução neste snippet:

```Kotlin
@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
   Column {
       Text(
           text = message,
           fontSize = 100.sp,
           lineHeight = 116.sp
       )
       Text(
           text = from,
           fontSize = 36.sp
       )
   }
}
```

Observe o pacote importado automaticamente pelo Android Studio:

```Kotlin
import androidx.compose.foundation.layout.Column
```

Não se esqueça que você precisa transmitir o parâmetro modificador aos elementos filhos dos combináveis. Isso significa que você precisa transmitir o parâmetro ao elemento combinável `Column`.

```Kotlin
@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column(modifier = modifier) {
        Text(
            text = message,
            fontSize = 100.sp,
            lineHeight = 116.sp
        )
        Text(
            text = from,
            fontSize = 36.sp
        )
    }
}
```