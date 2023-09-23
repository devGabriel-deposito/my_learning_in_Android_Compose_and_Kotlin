Nulidade é um conceito geralmente encontrado em muitas linguagens de programação. O termo se refere à capacidade de variáveis não terem um valor. No Kotlin, a nulidade é tratada intencionalmente para proteger contra valores `null`.

Por padrão, no Kotlin valores `null` darão um erro logo no intelisense. A menos que eu informe explicitamente que esta variável pode ser anulável.

```Kotlin
var nome: String = "Gabriel"  
  
nome = null
```
- A linha 2 terá o seguinte erro: `"Null can not be a value of a non-null type String"`

Porém, caso eu queria que esta variável possa receber o tipo `null`, eu teria que declarar explicitamente que esta variável pode receber este tipo, desta forma:

```Kotlin
var nome: String? = "Gabriel"  
  
nome = null
```

## Processamento de variáveis nulas

Ao executar alguma rotina com uma variável nula, é normal se deparar com problemas devido a nulidade da variável, uma vez que, para executar alguma rotina a variável deve ter algum valor. 

Digamos que caso eu queira executar o seguinte código:
```Kotlin
fun main() {
    var name: String? = null
    println(name.length)
}
```

Irá ocorrer o seguinte erro no compilador:
- `Kotlin: Only safe (?.) or non-null asserted (!!.) calls are allowed on a nullable receiver of type String?`

Para contornar, devo fazer isso:
```Kotlin
fun main() {
    var name: String? = null
    println(name?.length)
}
```

Desta forma poderei executar o código e, obviamente, o retorno no println será `null`

![[Pasted image 20230922191702.png]]

Porém, mesmo que a variável possua um valor, é obrigatório o uso do operador `?.` ou `!!.`

Em Kotlin, os operadores `?.` e `!!.` são usados para lidar com valores nulos de maneira diferente, mas eles têm funcionalidades distintas:

1. `?.` (Safe Call Operator):
    - O operador `?.` é usado para chamar métodos ou acessar propriedades em um objeto que pode ser nulo.
    - Se o objeto for nulo, a expressão inteira avaliará como nula, e nenhuma exceção será lançada.
    - É uma maneira segura de lidar com valores nulos e evita que o código quebre devido a exceções de `NullPointerException`.

Exemplo:

```Kotlin
val nome: String? = null
val comprimento = nome?.length // comprimento será nulo se nome for nulo
```

2. `!!.` (Non-null Assertion Operator):
    - O operador `!!.` é usado para forçar a chamada de um método ou o acesso a uma propriedade em um objeto, mesmo que o Kotlin saiba que o objeto pode ser nulo.
    - Se o objeto for nulo, uma exceção `NullPointerException` será lançada.
    - É útil quando você tem certeza de que um valor não é nulo em um contexto específico e deseja forçar o Kotlin a aceitar isso, mesmo que o sistema de tipos do Kotlin não possa garantir a não nulidade.

Exemplo:

```Kotlin
val nome: String? = null
val comprimento = nome!!.length // Isso lançará uma exceção se nome for nulo
```

Em resumo, `?.` é usado para tratamento seguro de valores nulos, enquanto `!!.` é usado quando você tem certeza de que um valor não é nulo e deseja forçar sua avaliação, arriscando uma exceção `NullPointerException` se estiver errado. No entanto, é geralmente recomendável evitar o uso excessivo de `!!.` e usar `?.` sempre que possível para escrever código mais seguro e robusto.