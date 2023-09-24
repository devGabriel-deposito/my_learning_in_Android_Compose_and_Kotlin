O objetivo principal do _construtor_ é especificar como os objetos da classe são criados. Em outras palavras, os construtores inicializam e preparam um objeto para uso. Você fez isso quando instanciou o objeto. O código dentro do construtor é executado quando o objeto da classe é instanciado. Você pode definir um construtor com ou sem parâmetros.

### Construtor padrão

Um construtor padrão não tem parâmetros. Você pode definir um construtor padrão como mostrado neste snippet de código:
```Kotlin
class SmartDevice constructor() {
    ...
}
```

O objetivo do Kotlin é ser conciso, portanto, é possível remover a palavra-chave `constructor` se não houver anotações ou modificadores de visibilidade no construtor. Você vai aprender sobre isso em breve. Também é possível remover os parênteses se o construtor não tiver parâmetros, conforme mostrado neste snippet de código:
```Kotlin
class SmartDevice {
    ...
}
```

O compilador Kotlin gera automaticamente o construtor padrão. O construtor padrão gerado automaticamente não está visível no código porque foi adicionado pelo compilador em segundo plano.

### Definir um construtor parametrizado

Na classe `SmartDevice`, as propriedades `name` e `category` são imutáveis. É preciso garantir que todas as instâncias da classe `SmartDevice` inicializem as propriedades `name` e `category`. Com a implementação atual, os valores das propriedades `name` e `category` estão fixados no código. Isso significa que todos os dispositivos inteligentes são nomeados pela string `"Android` `TV"` e categorizados com a string `"Entertainment"`.

Para manter a imutabilidade, mas evitar valores fixados no código, use um construtor parametrizado para inicializar:

- Na classe `SmartDevice`, mova as propriedades `name` e `category` para o construtor sem atribuir valores padrão:
```Kotlin
class SmartDevice(val name: String, val category: String) {

    var deviceStatus = "online"

    fun turnOn(){
        println("Smart device is turned on.")
    }

    fun turnOff(){
        println("Smart device is turned off.")
    }
}
```

O construtor passa a aceitar parâmetros para configurar as propriedades, e a maneira de instanciar um objeto para essa classe também muda. A sintaxe completa para instanciar um objeto é mostrada neste diagrama:

![46890255031c3fa4.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-classes-and-objects/img/46890255031c3fa4.png?hl=pt-br)

**Observação**: se a classe não tiver um construtor padrão e você tentar instanciar o objeto sem argumentos, o compilador vai mostrar um erro.

Esta é a representação do código:
```Kotlin
SmartDevice("Android TV", "Entertainment")
```

Ambos os argumentos para o construtor são strings. Não está claro a qual parâmetro o valor precisa ser atribuído. Para corrigir isso, da mesma forma que você transmitiu argumentos de função, crie um construtor com argumentos nomeados, como mostrado neste snippet de código:

```Kotlin
SmartDevice(name = "Android TV", category = "Entertainment")
```

Há dois tipos principais de construtores no Kotlin:

- **Construtor principal**: uma classe pode ter apenas um construtor principal, que é definido como parte do cabeçalho da classe. Um construtor principal pode ser um construtor padrão ou parametrizado. O construtor principal não tem corpo. Isso significa que ele não pode conter código.
- **Construtor secundário**: uma classe pode ter vários construtores secundários. Você pode definir o construtor secundário com ou sem parâmetros. O construtor secundário pode inicializar a classe e tem um corpo que pode conter lógica de inicialização. Se a classe tiver um construtor principal, cada construtor secundário precisa inicializar o construtor principal.

É possível usar o construtor principal para inicializar propriedades no cabeçalho da classe. Os argumentos transmitidos ao construtor são atribuídos às propriedades. A sintaxe para definir um construtor principal começa com o nome da classe seguido pela palavra-chave `constructor` e um conjunto de parênteses. Os parênteses contêm os parâmetros do construtor principal. Se houver mais de um parâmetro, use vírgulas para separar as definições de parâmetro. No diagrama abaixo, confira a sintaxe completa para definir um construtor principal:

![fec945b80f81980.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-classes-and-objects/img/fec945b80f81980.png?hl=pt-br)

O construtor secundário está incluído no corpo da classe, e a sintaxe dele inclui três partes:

- **Declaração de construtor secundário**: a definição do construtor secundário começa com a palavra-chave `constructor` seguida por parênteses. Se aplicável, os parênteses podem conter os parâmetros exigidos pelo construtor secundário.
- **Inicialização do construtor principal**: a inicialização começa com dois pontos seguidos da palavra-chave `this` e um conjunto de parênteses. Se aplicável, os parênteses podem conter os parâmetros exigidos pelo construtor principal.
- **Corpo do construtor secundário**: a inicialização do construtor principal é seguida por um conjunto de chaves que contêm o corpo do construtor secundário.

Confira a sintaxe neste diagrama:

![149e1882ccad5e11.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-classes-and-objects/img/149e1882ccad5e11.png?hl=pt-br)

Por exemplo, imagine que você quer integrar uma API desenvolvida por um provedor de dispositivos inteligentes. No entanto, a API retorna o código de status do tipo `Int` para indicar o status inicial do dispositivo. O valor retornado é `0` se o dispositivo estiver _off-line_ e `1` se estiver _on-line_. Para qualquer outro valor inteiro, o status é considerado _desconhecido_. Você pode criar um construtor secundário na classe `SmartDevice` para converter esse parâmetro `statusCode` em uma representação de string, como neste snippet de código:

```Kotlin
class SmartDevice(val name: String, val category: String) {
    var deviceStatus = "online"

    constructor(name: String, category: String, statusCode: Int) : this(name, category) {
        deviceStatus = when (statusCode) {
            0 -> "offline"
            1 -> "online"
            else -> "unknown"
        }
    }
    ...
}
```
