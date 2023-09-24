A herança permite criar uma classe com base nas características e no comportamento de outra classe. Esse é um mecanismo avançado que ajuda você a escrever código reutilizável e a estabelecer relações entre as classes.

Por exemplo, há muitos dispositivos inteligentes no mercado, como smart TVs, iluminação e interruptores inteligentes. Quando você representa dispositivos inteligentes na programação, eles compartilham algumas propriedades comuns, como nome, categoria e status. Além disso, eles têm comportamentos comuns, como estarem ligados ou desligados.

No entanto, a maneira de ligar ou desligar cada dispositivo inteligente é diferente. Por exemplo, para ligar uma TV, talvez seja necessário ligar a tela e, em seguida, configurar o último nível de volume e canal conhecidos. Por outro lado, para acender uma luz, talvez seja necessário apenas aumentar ou diminuir o brilho.

Além disso, todo dispositivo inteligente pode realizar mais funções e ações. Por exemplo, com uma TV, é possível ajustar o volume e mudar o canal. Com a iluminação, é possível ajustar o brilho ou a cor.

Em resumo, todos os dispositivos inteligentes têm recursos diferentes, mas compartilham algumas características comuns. Com a herança, é possível duplicar essas características comuns para cada classe de dispositivo inteligente ou tornar o código reutilizável.

Para fazer isso, você precisa criar uma classe mãe `SmartDevice` e definir as propriedades e os comportamentos comuns. Em seguida, você pode criar classes filhas, como `SmartTvDevice` e `SmartLightDevice`, que herdam as propriedades da classe mãe.

Em termos de programação, dizemos que as classes `SmartTvDevice` e `SmartLightDevice` _estendem_ a classe mãe `SmartDevice`. A classe mãe também é chamada de _superclasse_ e as classes filhas de _subclasses_. Entenda a relação entre elas neste diagrama:

![Diagrama representando a relação de herança entre classes.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-classes-and-objects/img/2ef71833a17da581.png?hl=pt-br)

No Kotlin, todas as classes são finais por padrão, o que significa que não é possível estendê-las. É necessário definir as relações entre elas.

Defina a relação entre a superclasse `SmartDevice` e as subclasses:

1. Na superclasse `SmartDevice`, adicione uma palavra-chave `open` antes da palavra-chave `class`:
```Kotlin
open class SmartDevice(val name: String, val category: String) {
    ...
}
```

**Observação:** a palavra-chave `open` informa ao compilador que essa classe pode ser estendida.

A sintaxe para criar uma subclasse começa com a criação do cabeçalho da classe, como foi feito até agora. O parêntese de fechamento do construtor é seguido por um espaço, dois pontos, outro espaço, o nome da superclasse e um conjunto de parênteses. Se necessário, os parênteses podem incluir os parâmetros exigidos pelo construtor da superclasse. Confira a sintaxe neste diagrama:

![3836f8e2bd95f6da.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-classes-and-objects/img/3836f8e2bd95f6da.png?hl=pt-br)

2. Crie uma subclasse `SmartTvDevice` que estenda a superclasse `SmartDevice`:
```Kotlin
class SmartTvDevice(deviceName: String, deviceCategory: String) :
    SmartDevice(name = deviceName, category = deviceCategory) {
}
```

A definição do `constructor` para `SmartTvDevice` não especifica se as propriedades são mutáveis ou imutáveis. Isso significa que os parâmetros `deviceName` e `deviceCategory` são apenas parâmetros do `constructor` em vez de propriedades de classe. Eles não podem ser usados na classe, só transmitidos ao construtor da superclasse.
