## O que é Jetpack Compose?

O Jetpack Compose é um kit de ferramentas moderno para a criação de IUs do Android. O Compose simplifica e acelera o desenvolvimento da interface no Android com menos código, ferramentas poderosas e recursos Kotlin intuitivos. Com o Compose, você pode criar a interface definindo um conjunto de funções, conhecidas como funções combináveis, que recebem dados e descrevem elementos da interface.

O Compose é um framework de interface declarativo, o que significa que a interface é definida no código. Para atualizar a interface durante a execução do app ou em resposta a interações do usuário, é necessário usar um processo chamado recomposição. A recomposição é responsável por atualizar a descrição da interface com base em mudanças de estado.

A composição é a descrição da interface criada pelo Compose quando ele executa elementos combináveis. O Compose chama funções combináveis para criar elementos da interface e, quando ocorre uma mudança de estado, ele executa novamente as funções combináveis afetadas para criar uma interface atualizada, chamando esse processo de recomposição. O Compose automaticamente programa a recomposição quando ocorrem atualizações de estado.

A composição só pode ser criada inicialmente e atualizada por meio da recomposição. O Compose rastreia o estado que deve ser monitorado, como a variável "amountInput" no exemplo, e programa recomposições sempre que esse estado muda, garantindo que a interface seja sempre atualizada de acordo com as mudanças de dados.

## Funções combináveis

As funções combináveis são o elemento básico de uma interface no Compose. Uma função combinável:

- descreve uma parte da interface;
- não retorna nada;
- recebe uma entrada e gera o que será mostrado na tela.
## Anotações

Anotações são meios de anexar informações extras ao código. Essas informações ajudam ferramentas como o compilador do Jetpack Compose e outros desenvolvedores a entender o código do app.

Uma anotação é aplicada adicionando o caractere `@` como prefixo ao nome dela no início da declaração em questão. Vários elementos de código, como propriedades, funções e classes, podem ser anotados. Mais adiante no curso, você vai aprender sobre classes.

O diagrama abaixo é um exemplo de função com anotação:

![Diagrama mostrando a anatomia de uma função combinável, em que o caractere de prefixo de anotação @ é um elemento combinável seguido pela declaração da função.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/a3da8d7133397e49.png?hl=pt-br)

O snippet de código abaixo tem exemplos de propriedades anotadas. Você vai usar esses recursos nos próximos codelabs.

```Kotlin
// Example code, do not copy it over

@Json
val imgSrcUrl: String

@Volatile
private var INSTANCE: AppDatabase? = null
```

### Anotações com parâmetros

Anotações podem usar parâmetros. Elas fornecem mais informações para as ferramentas que fazem o processamento delas. Confira abaixo alguns exemplos de anotação `@Preview` com e sem parâmetros.

![Captura de tela do Android Studio mostrando o código e a prévia](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/5ae0d357533ceb78.png?hl=pt-br)

_Anotação sem parâmetros_

![Captura de tela do Android Studio mostrando o código e a prévia](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/d778b6a999afba93.png?hl=pt-br)

_Plano de fundo da prévia da anotação_

![Captura de tela do Android Studio mostrando o código e a prévia](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/6271a7ef904edfa2.png?hl=pt-br)

_Anotação com um título de prévia_

É possível transmitir vários parâmetros para a anotação, conforme mostrado aqui.

![e59eddb4ea86d214.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-text-composables/img/e59eddb4ea86d214.png?hl=pt-br)

_Anotação com título de visualização e interface do sistema (tela do smartphone)_

O Jetpack Compose inclui uma ampla variedade de anotações integradas. Você já aprendeu sobre as anotações `@Composable` e `@Preview` até agora. Vamos falar mais sobre as anotações e os usos delas mais adiante no curso.

### Exemplo de uma função combinável

A função combinável recebe a anotação [`@Composable`](https://developer.android.com/reference/kotlin/androidx/compose/runtime/Composable?hl=pt-br). Todas as funções desse tipo precisam ter essa anotação. Ela informa ao compilador do Compose que essa função se destina a converter dados em interface. Vale lembrar que um compilador é um programa especial que pega o código que você escreveu, analisa linha por linha e converte em algo que o computador pode entender (linguagem de máquina).

O snippet de código abaixo é um exemplo de função simples de composição que recebe dados (o parâmetro de função `name`) e os usa para renderizar um elemento de texto na tela.

```Kotlin
@Composable
fun Greeting(name: String) {
    Text(text = "Hello $name!")
}
```

Algumas observações sobre a função combinável:

- O Jetpack Compose foi criado com base em funções combináveis. Essas funções permitem definir a interface do app de maneira programática, descrevendo a aparência dele, em vez de se concentrar no processo de construção da interface. Para criar uma função combinável, basta adicionar a anotação `@Composable` ao nome da função.
- As funções combináveis podem aceitar argumentos, que permitem à lógica do app descrever ou modificar a interface. Nesse caso, o elemento da interface aceita uma `String` para que a mensagem use o nome do usuário.

### Observe as funções combináveis no código

1. No Android Studio, abra o arquivo `MainActivity.kt`.
2. Role até a função `GreetingPreview()`. Essa função combinável ajuda a mostrar uma prévia da função `Greeting()`. Como prática recomendada, as funções devem sempre ser nomeadas ou renomeadas para descrever a funcionalidade que elas têm. Mude o nome da função para `BirthdayCardPreview()`.

```Kotlin
@Preview(showBackground = true)
@Composable
fun BirthdayCardPreview() {
   HappyBirthdayTheme {
       Greeting("Android")
   }
}
```

As funções combináveis podem chamar outras funções desse tipo. Neste snippet de código, a função de visualização está chamando a função de composição `Greeting()`.

Observe que a função anterior também tem outra anotação, `@Preview`, com um parâmetro antes da anotação `@Composable`. Você vai saber mais sobre os argumentos transmitidos à anotação `@Preview` mais adiante no curso.

## Nomes de funções combináveis

A função de composição que não retorna nada e carrega a anotação `@Composable` PRECISA ser nomeada usando o padrão Pascal Case. Ele se refere a uma convenção de nomenclatura em que a primeira letra de cada palavra em uma palavra composta é maiúscula. A diferença entre o padrão Pascal e o Camel é que todas as palavras no Pascal têm as iniciais maiúsculas. No padrão Camel, a primeira palavra não tem inicial maiúscula.

A função Compose:

- _PRECISA_ ser um substantivo: `DoneButton()`
- _NÃO_ pode ser um verbo ou frase verbal: `DrawTextField()`
- _NÃO_ pode ser uma preposição nominal: `TextFieldWithLink()`
- _NÃO_ pode ser um adjetivo: `Bright()`
- _NÃO_ pode ser um advérbio: `Outside()`
- Substantivos _PODEM_ ter adjetivos descritivos como prefixos: `RoundIcon()`

Para saber mais, consulte [Como nomear funções combináveis](https://github.com/androidx/androidx/blob/androidx-main/compose/docs/compose-api-guidelines.md#naming-unit-composable-functions-as-entities) (link em inglês).

**Exemplo de código. Não copie**

```Kotlin
// Do: This function is a descriptive PascalCased noun as a visual UI element
@Composable
fun FancyButton(text: String) {}

// Do: This function is a descriptive PascalCased noun as a non-visual element
// with presence in the composition
@Composable
fun BackButtonHandler() {}

// Don't: This function is a noun but is not PascalCased!
@Composable
fun fancyButton(text: String) {}

// Don't: This function is PascalCased but is not a noun!
@Composable
fun RenderFancyButton(text: String) {}

// Don't: This function is neither PascalCased nor a noun!
@Composable
fun drawProfileImage(image: ImageAsset) {}
```