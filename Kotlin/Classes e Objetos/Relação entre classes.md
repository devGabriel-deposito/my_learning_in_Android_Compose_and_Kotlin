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