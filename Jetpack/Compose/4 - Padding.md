Um elemento da IU envolve o conteúdo. Para evitar que eles fiquem muito próximos, você pode especificar a quantidade de _padding_ em cada lado.

|   |   |
|---|---|
|![Elemento combinável de texto sem padding](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-add-images/img/f5ec4094db454c65.png?hl=pt-br)|![Elemento combinável de texto com padding](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-add-images/img/95e98cb1a1f6d3b3.png?hl=pt-br)|

Um padding é usado como um modificador, o que significa que ele pode ser aplicado a qualquer elemento combinável. Para cada lado do elemento, o modificador `padding` usa um argumento opcional que define a quantidade de padding.

![O diagrama mostra os paddings das partes de cima e de baixo, assim como de início e fim](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-add-images/img/2e96e127f9f8c7.png?hl=pt-br)

```Kotlin
// This is an example.
Modifier.padding(
    start = 16.dp,
    top = 16.dp,
    end = 16.dp,
    bottom = 16.dp
)
```
