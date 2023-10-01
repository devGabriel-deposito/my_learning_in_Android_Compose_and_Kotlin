## Mostrar o valor da gorjeta calculado

Você programou a função para calcular o valor da gorjeta. A próxima etapa é exibir o valor calculado:

1. Na função `TipTimeLayout()`, no final do bloco `Column()`, observe o elemento combinável de texto que exibe `$0.00`. Você vai atualizar esse valor para o valor calculado da gorjeta.

```Kotlin
@Composable
fun TipTimeLayout() {
    Column(
        modifier = Modifier.padding(40.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        // ...
        Text(
            text = stringResource(R.string.tip_amount, "$0.00"),
            style = MaterialTheme.typography.displaySmall
        )
        // ...
    }
}
```

Você precisa acessar a variável `amountInput` na função `TipTimeLayout()` para calcular e mostrar o valor da gorjeta. No entanto, a variável `amountInput` é o estado do campo de texto definido na função combinável `EditNumberField()`. Ela ainda não pode ser chamada pela função `TipTimeLayout()`. Esta imagem ilustra a estrutura do código:

![4d8b69d49a90683a.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/4d8b69d49a90683a.png?hl=pt-br)

Essa estrutura não permite que você mostre o valor da gorjeta no novo elemento combinável `Text`, já que o elemento `Text` precisa acessar a variável `amount` calculada com a variável `amountInput`. Você precisa expor a variável `amount` à função `TipTimeLayout()`. Esta imagem ilustra a estrutura de código desejada, que faz com que o elemento combinável `EditNumberField()` não tenha estado:

![38bd92a2346a910b.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/38bd92a2346a910b.png?hl=pt-br)

Esse padrão é chamado de _elevação de estado_. Na próxima seção, você vai _elevar_ o estado de um elemento combinável para que ele fique sem estado.

**Observação**: um elemento combinável sem estado é aquele que não armazena o próprio estado. Ele mostra o estado fornecido como argumentos de entrada.