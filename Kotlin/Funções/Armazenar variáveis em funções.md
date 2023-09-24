
## Referência

```Kotlin
fun main() {
    val trickFunction = ::trick

    trickFunction()
}

fun trick() {
    println("No treats!")
}
```

Uma função, pode ser atribuída a alguma variável. Não o valor de retorno, mas a função mesmo em si. O uso do operador `::` fará com que a referência da função seja atribuída a variável `trickFunction`. Desta forma, podemos executar `trickFunction` como uma função.

## Atribuir valor do retorno

```Kotlin
fun main() {  
    val trickOrTreat = trickOrTreat()  
      
    println(trickOrTreat)  
}  
  
fun trickOrTreat(): String {  
    return "No treats!"  
}
```

Neste caso, a string "No treats!" está sendo atribuída a variável `trickOrTreat`

