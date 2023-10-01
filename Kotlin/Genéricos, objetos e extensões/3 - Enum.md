Na seção anterior, você definiu uma propriedade de dificuldade com três valores possíveis: "fácil", "médio" e "difícil". Embora essas classificações funcionem, há alguns problemas.

1. Se você digitar uma das três strings incorretamente, isso pode gerar bugs.
2. Se os valores mudarem, por exemplo, se `"medium"` (médio) for renomeado como `"average"` (intermediário), você vai precisar atualizar todos os usos dessa string.
3. Você ou outro desenvolvedor pode acidentalmente usar uma string diferente, que não seja um dos três valores válidos.
4. Vai ser mais difícil fazer a manutenção do código caso você queira adicionar mais níveis de dificuldade.

O Kotlin ajuda a resolver esses problemas com um tipo de classe especial conhecido como _classe de enumeração_. Essa classe é usada para criar tipos com um conjunto limitado de valores possíveis. Por exemplo, os quatro pontos cardeais (norte, sul, leste e oeste) poderiam ser representadas por uma classe de enumeração. Não é necessário acrescentar nenhuma outra informação, e o código não permite que isso seja feito. A sintaxe de uma classe de tipo enumerado é apresentada abaixo.

![f4bddb215eb52392.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-generics/img/f4bddb215eb52392.png?hl=pt-br)

Cada valor possível de um tipo enumerado é chamado de _constante_. Elas são colocadas dentro das chaves separadas por vírgulas. Por convenção, os nomes de constantes são escritos com todas as letras maiúsculas.

Para se referir a constantes de tipo enumerado, use o operador de ponto.

![f3cfa84c3f34392b.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-generics/img/f3cfa84c3f34392b.png?hl=pt-br)

## Usar uma constante de tipo enumerado

Modifique o código para usar uma constante de enumeração para representar o nível de dificuldade, em vez de uma `String`.

1. Abaixo da classe `Question` (pergunta), defina uma classe de `enum` com o nome `Difficulty` (dificuldade).

```Kotlin
enum class Difficulty {
    EASY, MEDIUM, HARD
}
```

2. Na classe `Question`, mude o tipo de dado da propriedade `difficulty` de `String` para `Difficulty`.

```Kotlin
class Question<T>(
    val questionText: String,
    val answer: T,
    val difficulty: Difficulty
)
```

3. Ao inicializar as três perguntas, transmita a constante de enumeração para a dificuldade.

```Kotlin
val question1 = Question<String>("Quoth the raven ___", "nevermore", Difficulty.MEDIUM)
val question2 = Question<Boolean>("The sky is green. True or false", false, Difficulty.EASY)
val question3 = Question<Int>("How many days are there between full moons?", 28, Difficulty.HARD)
```