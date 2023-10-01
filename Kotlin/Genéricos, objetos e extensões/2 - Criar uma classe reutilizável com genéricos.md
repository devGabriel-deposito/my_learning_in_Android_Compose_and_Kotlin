```Kotlin
class FillInTheBlankQuestion(
    val questionText: String,
    val answer: String,
    val difficulty: String
)

class TrueOrFalseQuestion(
    val questionText: String,
    val answer: Boolean,
    val difficulty: String
)
class NumericQuestion(
    val questionText: String,
    val answer: Int,
    val difficulty: String
)
```

As três classes têm exatamente as mesmas propriedades: `questionText`, `answer` e `difficulty`. A única diferença é o tipo de dado da propriedade `answer`. Você pode pensar que a solução óbvia seria criar uma classe mãe com o `questionText` e a `difficulty`, fazendo com que cada subclasse defina a propriedade `answer`.

No entanto, usar o conceito de herança geraria o mesmo problema acima. Sempre que você adicionar um novo tipo de pergunta, vai precisar adicionar uma propriedade `answer`. A única diferença é o tipo de dado. Também seria estranho ter uma classe `Question` mãe que não tivesse uma propriedade de resposta.

Quando você precisa que uma propriedade tenha diferentes tipos de dados, criar subclasses não é a solução. Em vez disso, o Kotlin oferece um recurso conhecido como _tipos genéricos_ que permite que uma única propriedade tenha diferentes tipos de dados, dependendo do caso de uso específico.

## O que é um dado de tipo genérico?

Os tipos genéricos, ou _genéricos_, permitem que um tipo de dado, por exemplo, uma classe, especifique um marcador de posição para um tipo de dado desconhecido. Esse marcador pode ser usado com propriedades ou métodos. O que isso significa?

No exemplo acima, em vez de definir uma propriedade de resposta para cada tipo de dado possível, você pode criar uma única classe para representar qualquer pergunta e usar um marcador para o tipo de dado da propriedade `answer`. O tipo de dado real, seja `String`, `Int` ou `Boolean`, vai ser especificado quando a classe for instanciada. Sempre que o marcador for usado, o tipo de dado usado será aquele transmitido para a classe. Confira abaixo a sintaxe para definir um tipo genérico para uma classe:

![67367d9308c171da.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-generics/img/67367d9308c171da.png?hl=pt-br)

Como um dado de tipo genérico é fornecido ao instanciar a classe, ele precisa ser definido como parte da assinatura da classe. Depois do nome da classe, inserimos um sinal "menor que" (`<`), seguido por um marcador para o tipo de dado e, finalmente, por um sinal "maior que" (`>`).

O marcador pode ser usado sempre que você usa um tipo de dado real na classe, como uma propriedade.

![81170899b2ca0dc9.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-generics/img/81170899b2ca0dc9.png?hl=pt-br)

Esse processo é idêntico a qualquer outra declaração de propriedade, exceto pelo uso do marcador no lugar do tipo de dados.

E como uma classe sabe qual tipo de dado usar? O tipo de dado usado pelo genérico é transmitido como parâmetro entre os sinais "menor que" e "maior que" ao instanciar a classe.

![9b8fce54cac8d1ea.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-generics/img/9b8fce54cac8d1ea.png?hl=pt-br)

Depois do nome, inserimos um sinal "menor que" (`<`), seguido pelo tipo de dado real (`String`, `Boolean`, `Int` ou outro), seguido por um sinal "maior que" (`>`). O tipo de dado do valor transmitido para a propriedade genérica precisa corresponder ao tipo de dado entre os sinais de "menor que" e "maior que". A propriedade de resposta precisa ser genérica para que seja possível usar uma única classe para representar qualquer tipo de pergunta do teste, independente da resposta ser uma `String`, um `Boolean`, um `Int` ou qualquer outro tipo de dado.

**Observação**: os tipos genéricos transmitidos ao instanciar uma classe também são chamados de "parâmetros", embora façam parte de uma lista de parâmetros diferente dos valores de propriedades colocados entre parênteses.

**Observação**: como no exemplo acima, muitas vezes você vai encontrar um tipo genérico com o nome `T` (abreviatura de "tipo") ou outras letras maiúsculas se a classe tiver vários genéricos. No entanto, não existe uma regra definida, e você pode usar um nome mais descritivo para os genéricos, se preferir.

## Refatorar o código para usar genéricos

Refatore o código para usar uma única classe com o nome `Question` (pergunta) com uma propriedade de resposta genérica.

1. Remova as definições das classes `FillInTheBlankQuestion`, `TrueOrFalseQuestion` e `NumericQuestion`.
2. Crie uma nova classe com o nome `Question`.

```Kotlin
class Question()
```

3. Depois do nome da classe, mas antes dos parênteses, adicione um parâmetro de tipo genérico usando sinais de "menor que" e "maior que". Dê o nome `T` ao tipo genérico.

```Kotlin
class Question<T>()
```

4. Adicione as propriedades `questionText`, `answer` e `difficulty`. O `questionText` precisa ser do tipo `String`. A `answer` precisa ser do tipo `T`, porque o tipo de dado é especificado ao instanciar a classe `Question`. A propriedade `difficulty` precisa ser do tipo `String`.

```Kotlin
class Question<T>(    
	val questionText: String,    
	val answer: T,    
	val difficulty: String
)
```

5. Para conferir como isso funciona com vários tipos de pergunta, seja de preencher lacunas, verdadeiro ou falso ou outra, crie três instâncias da classe `Question` em `main()`, conforme mostrado abaixo.

```Kotlin
fun main() {
    val question1 = Question<String>("Quoth the raven ___", "nevermore", "medium")
    val question2 = Question<Boolean>("The sky is green. True or false", false, "easy")
    val question3 = Question<Int>("How many days are there between full moons?", 28, "hard")
}
```

6. Execute o app para conferir se tudo está funcionando. Agora você tem três instâncias da classe `Question`, cada uma com tipos de dados diferentes para a resposta, ao invés de usar três classes diferentes ou o conceito de herança. Caso queira processar perguntas com um tipo de resposta diferente, você pode reutilizar a mesma classe `Question`.