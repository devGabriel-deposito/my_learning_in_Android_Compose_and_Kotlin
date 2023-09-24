 O programa `trafficLightColor` parece mais complexo com várias condições, também conhecidas como ramificações. Você pode se perguntar se é possível simplificar um programa com um número ainda maior de ramificações.

Em Kotlin, ao lidar com várias ramificações, você pode usar a instrução `when` em vez de `if/else` porque ela melhora a legibilidade, ou seja, as pessoas podem ler o código com mais facilidade. É muito importante considerar a legibilidade ao escrever um programa porque é provável que outros desenvolvedores precisem revisar e modificar o código durante todo o ciclo de vida. Uma boa legibilidade garante que os desenvolvedores entendam corretamente o código e não introduzam bugs nele de forma acidental.

É recomendável usar as instruções `when` quando há mais de duas ramificações a serem consideradas.

![Um diagrama que mostra a anatomia de uma instrução "when". Ela começa com a palavra-chave "when" seguida por um par de chaves com um bloco de parâmetro dentro. Após o bloco, dentro de um par de chaves, há três linhas de casos. Dentro de cada linha, há um bloco de condição seguido por um símbolo de seta e um bloco de corpo. Observação: cada uma das linhas de casos é avaliada sequencialmente.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-conditionals/img/2f7c0a1e312a2581.png?hl=pt-br)

Uma instrução `when` aceita um único valor do parâmetro. O valor é avaliado de acordo com cada uma das condições sequencialmente. Em seguida, o corpo correspondente da primeira condição atendida é executado. Cada condição e corpo são separados por uma seta (`->`). Assim como as instruções `if/else`, cada par de condição e corpo é chamado de ramificação em instruções `when`. Também semelhante à instrução `if/else`, é possível adicionar uma ramificação `else` como condição final em uma instrução `when` que funciona como uma ramificação "pega-tudo".

## Reescrever uma instrução `if/else` com uma instrução `when`

No programa do semáforo, já existem várias ramificações:

- Semáforo vermelho
- Semáforo amarelo
- Semáforo verde
- Outra cor do semáforo

Converta o programa para usar uma instrução `when`:

1. Na função `main()`, remova a instrução `if/else`:
```Kotlin
fun main() {
	val trafficLightColor = "Black"
}
```

2. Adicione uma instrução `when` e transmita a variável `trafficLightColor` como um argumento:
```Kotlin
fun main() {
    val trafficLightColor = "Black"

    when (trafficLightColor) {
    }
}
```

3. No corpo da instrução `when`, adicione a condição `"Red"` seguida por uma seta e um corpo `println("Stop")`:
```Kotlin
fun main() {
    val trafficLightColor = "Black"

    when (trafficLightColor) {
        "Red" -> println("Stop")
    }
}
```

4. Na próxima linha, adicione a condição `"Yellow"` seguida por uma seta e um corpo `println("Slow")`:
```Kotlin
fun main() {
    val trafficLightColor = "Black"

    when (trafficLightColor) {
        "Red" -> println("Stop")
        "Yellow" -> println("Slow")
    }
}
```

5. Na próxima linha, adicione a condição `"Green"` seguida por uma seta e um corpo `println("Go")`:
```Kotlin
fun main() {
    val trafficLightColor = "Black"

    when (trafficLightColor) {
        "Red" -> println("Stop")
        "Yellow" -> println("Slow")
        "Green" -> println("Go")
    }
}
```

6. Na próxima linha, adicione a palavra-chave `else` seguida por uma seta e um corpo `println("Invalid traffic-light color")`:
```Kotlin
fun main() {
    val trafficLightColor = "Black"

    when (trafficLightColor) {
        "Red" -> println("Stop")
        "Yellow" -> println("Slow")
        "Green" -> println("Go")
        else -> println("Invalid traffic-light color")
    }
}
```

7. Reatribua a variável `trafficLightColor` a um valor `"Yellow"`:
```Kotlin
fun main() {
    val trafficLightColor = "Yellow"

    when (trafficLightColor) {
        "Red" -> println("Stop")
        "Yellow" -> println("Slow")
        "Green" -> println("Go")
        else -> println("Invalid traffic-light color")
    }
}
```

Qual vai ser o resultado do programa?

8. Execute o programa e veja o resultado:
```Kotlin
Slow
```

![Um diagrama para anotar a instrução "when". A linha "Red" -> println("Stop") é anotada como caso 1. A linha "Yellow" -> println("Slow") é anotada como caso 2. A linha "Green" -> println("Go") é anotada como caso 3. A linha else -> println("Invalid light-light color") é anotada como caso 4.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-conditionals/img/7112edfc7c7b7918.png)

A saída é uma mensagem `Slow` porque:

- Um valor `"Yellow"` é atribuído à variável `trafficLightColor`.
- O programa avalia cada condição individualmente em sequência.
- O valor `"Yellow"` não é igual ao valor `"Red"`, então o programa pula o primeiro corpo.
- O valor `"Yellow"` é igual ao valor `"Yellow"`, então o programa executa o segundo corpo e mostra uma mensagem `Slow`.
- Um corpo foi executado, então o programa ignora a terceira e a quarta ramificações e sai da instrução `when`.
## Escrever condições mais complexas em uma instrução `when`

Até agora, você aprendeu a escrever condições `when` para uma única condição de igualdade, como quando a variável `trafficLightColor` recebe um valor `"Yellow"`. Em seguida, você vai aprender a usar a vírgula (`,`) e as palavras-chave `in` e `is` para formar condições `when` mais complexas.

Crie um programa que determine se um número entre 1 e 10 é um número primo:

1. Abra o [Playground Kotlin](https://developer.android.com/training/kotlinplayground?hl=pt-br) em outra janela.

Vamos voltar ao programa de semáforo mais tarde.

2. Defina uma variável `x` e atribua a ela um valor `3`:
```Kotlin
fun main() {
    val x = 3
}

```

3. Adicione uma instrução `when` que inclua várias ramificações para as condições `2`, `3`, `5` e `7` e coloque um corpo `println("x is prime number between 1 and 10.")` depois de cada uma:
```Kotlin
fun main() {
    val x = 3

    when (x) {
        2 -> println("x is a prime number between 1 and 10.")
        3 -> println("x is a prime number between 1 and 10.")
        5 -> println("x is a prime number between 1 and 10.")
        7 -> println("x is a prime number between 1 and 10.")
    }
}
```

4. Adicione uma ramificação `else` com um corpo `println("x is not prime number between 1 and 10.")`:
```Kotlin
fun main() {
    val x = 3

    when (x) {
        2 -> println("x is a prime number between 1 and 10.")
        3 -> println("x is a prime number between 1 and 10.")
        5 -> println("x is a prime number between 1 and 10.")
        7 -> println("x is a prime number between 1 and 10.")
        else -> println("x isn't a prime number between 1 and 10.")
    }
}
```

5. Execute o programa e verifique se o resultado está conforme o esperado:
```Kotlin
x is a prime number between 1 and 10.
```

### Usar uma vírgula (`,`**) para várias condições**

O programa de números primos contém muitas repetições de instruções `println()`. Ao escrever uma instrução `when`, use uma vírgula (`,`) para indicar várias condições que correspondem ao mesmo corpo.

![Um diagrama que mostra a anatomia de uma instrução "when". Ele começa com uma palavra-chave "when" seguida por parênteses, com um bloco de parâmetro dentro. Em seguida, dentro de um par de chaves, há duas linhas de casos. Na primeira linha, há um bloco de condição 1 seguido por uma vírgula e um bloco de condição 2 seguido por um símbolo de seta e um bloco de corpo. Na segunda linha, há um bloco de condição seguido por um símbolo de seta e um bloco de corpo.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-conditionals/img/4e778c4c4c044e51.png?hl=pt-br)

No diagrama anterior, se a primeira ou a segunda condição for atendida, o corpo correspondente vai ser executado.

Reescreva o programa de números primos com este conceito:

1. Na ramificação da condição `2`, adicione os números `3`, `5` e `7`, separados por vírgulas (`,`):
```Kotlin
fun main() {
    val x = 3

    when (x) {
        2, 3, 5, 7 -> println("x is a prime number between 1 and 10.")
        3 -> println("x is a prime number between 1 and 10.")
        5 -> println("x is a prime number between 1 and 10.")
        7 -> println("x is a prime number between 1 and 10.")
        else -> println("x isn't a prime number between 1 and 10.")
    }
}
```

2. Remova as ramificações individuais das condições `3`, `5` e `7`:
```Kotlin
fun main() {
    val x = 3

    when (x) {
        2, 3, 5, 7 -> println("x is a prime number between 1 and 10.")
        else -> println("x isn't a prime number between 1 and 10.")
    }
}
```

3. Execute o programa e verifique se o resultado está conforme o esperado:
```Kotlin
x is a prime number between 1 and 10.
```

### Usar a palavra-chave `in` **para várias condições**

Além do símbolo de vírgula (`,`) para indicar várias condições, também é possível usar a palavra-chave `in` e um intervalo de valores em ramificações `when`.

![Um diagrama que mostra a anatomia de uma instrução "when". Ele começa com uma palavra-chave "when" seguida por parênteses, com um bloco de parâmetro dentro. Em seguida, dentro de um par de chaves, há duas linhas de casos. Na primeira linha, há uma palavra-chave seguida por um bloco de início do intervalo, dois pontos, um bloco final do intervalo, um símbolo de seta e um bloco de corpo. Na segunda linha, há um bloco de condição seguido por um símbolo de seta e um bloco de corpo.](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-conditionals/img/400f940f363bd3c4.png?hl=pt-br)

Para usar um intervalo de valores, adicione um número que indique o início do intervalo seguido por dois pontos sem espaços e feche-o com outro número que indique o final do intervalo.

Quando o valor do parâmetro é igual a qualquer valor no intervalo entre o início e o fim, o primeiro corpo é executado.

No programa de números primos, é possível mostrar uma mensagem se o número estiver entre 1 e 10, mas não for um número primo?

Adicione outra ramificação com a palavra-chave `in`:

1. Depois da primeira ramificação da instrução `when`, adicione uma segunda ramificação com a palavra-chave `in`, seguida por um intervalo `1..10` e um corpo `println("x is a number between 1 and 10, but not a prime number.")`:
```Kotlin
fun main() {
    val x = 3

    when (x) {
        2, 3, 5, 7 -> println("x is a prime number between 1 and 10.")
        in 1..10 -> println("x is a number between 1 and 10, but not a prime number.")
        else -> println("x isn't a prime number between 1 and 10.")
    }
}
```
