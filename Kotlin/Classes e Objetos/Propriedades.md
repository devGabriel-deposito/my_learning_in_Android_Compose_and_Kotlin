A definição de propriedades no Kotlin possui algumas peculiaridades diferentes de outras linguagens. Por exemplo: ao declarar uma variável no C#, podemos atribuir o seguinte escopo:
```C#
var variavel = { get; set; }
```

Desta forma, não precisaremos criar getters e setters para esta variável. No Kotlin, fica disposto desta forma:
```Kotlin
class Teste {
    var speakerVolume = 2
        get() = field
        set(value) {
            field = value
        }   
}
```

É perceptível que o get() está alinhado a uma tabulação a frente, pois o get e o set fazem parte da variável speakerVolume
![[Pasted image 20230923164926.png]]