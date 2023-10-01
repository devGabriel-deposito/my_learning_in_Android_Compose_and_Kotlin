- Definição: basicamente, o estado em um app é qualquer valor que pode mudar ao longo do tempo

Existem dois tipos para gerenciamento de estado no Compose: [`State`](https://developer.android.com/reference/kotlin/androidx/compose/runtime/State?hl=pt-br) e [`MutableState`](https://developer.android.com/reference/kotlin/androidx/compose/runtime/MutableState?hl=pt-br) no Compose para tornar o estado no app observável ou monitorado pelo Compose. O tipo `State` é imutável, ou seja, o valor dele só será lido, enquanto o tipo [`MutableState`](https://developer.android.com/reference/kotlin/androidx/compose/runtime/MutableState?hl=pt-br) for mutável. Você pode usar a função [`mutableStateOf()`](https://developer.android.com/reference/kotlin/androidx/compose/runtime/package-summary?hl=pt-br#mutableStateOf(kotlin.Any,androidx.compose.runtime.SnapshotMutationPolicy)) para criar um `MutableState` observável. Ele recebe um valor inicial como um parâmetro envolvido por um objeto `State`, que torna o `value` dele observável.

O valor retornado pela função `mutableStateOf()`:

- mantém o estado, que é o valor da conta;
- é mutável, então o valor pode ser mudado;
- é observável, então o Compose observa as mudanças no valor e aciona uma recomposição para atualizar a interface.

```Kotlin
var amountInput by remember { mutableStateOf("") }
```

Agora, a string vazia é o valor padrão inicial da variável `amountInput`. `by` é uma [delegação de propriedade do Kotlin](https://kotlinlang.org/docs/delegated-properties.html) (link em inglês). As funções getter e setter padrão da propriedade `amountInput` são delegadas às funções getter e setter da classe `remember`, respectivamente.

3. Importe estas funções:

```
import androidx.compose.runtime.rememberimport androidx.compose.runtime.getValueimport androidx.compose.runtime.setValue
```

**Alerta**: esse código pode gerar o erro mostrado nesta imagem quanto à função de extensão `getValue()`:

![29df60323e085a26.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/29df60323e085a26.png?hl=pt-br)

Se isso acontecer, adicione manualmente as importações `getValue` e `setValue` ao bloco de importação no início do arquivo, como nesta imagem:

![a5beae1f620862b3.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/a5beae1f620862b3.png?hl=pt-br)

A adição das importações getter e setter do delegado permite ler e definir `amountInput` sem referenciar a propriedade `value` do `MutableState`

```
**Observação**: durante a composição inicial, o `value` no `TextField` é definido como o valor inicial, que é uma string vazia.

Quando o usuário digita no campo de texto, o callback lambda `onValueChange` é chamado, o lambda é executado e o `amountInput.value` é definido como o valor atualizado.

O `amountInput` é o estado mutável monitorado pelo Compose. A recomposição é programada. A função combinável `EditNumberField()` é recomposta. Como você está usando `remember` `{ },`, a mudança sobrevive à recomposição. Por isso, o estado não é reinicializado como `""`.

O `value` do campo de texto está definido como o valor lembrado de `amountInput`. O campo de texto é recomposto, redesenhado na tela com um novo valor
```
