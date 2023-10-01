Nesta seção, você vai definir um ponto de interrupção e depurar a função de composição `EditNumberField()` para ver como a composição inicial e a recomposição funcionam.

**Observação**: um ponto de interrupção é uma área do código em que você quer pausar a execução normal do app para realizar outras ações. Por exemplo: examinar variáveis, avaliar expressões ou executar o código linha por linha. É possível definir um ponto de interrupção em qualquer linha de código executável.

Defina um ponto de interrupção e depure o app em um emulador ou dispositivo:

1. Na função `EditNumberField()`, ao lado do parâmetro chamado `onValueChange`, defina um ponto de interrupção de linha.
2. No menu de navegação, clique em **Debug 'app'**. O app será iniciado no emulador ou dispositivo. A execução do app é pausada pela primeira vez quando o elemento `TextField` é criado.

![ec4cb7046d06aadf.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/ec4cb7046d06aadf.png?hl=pt-br)

3. No painel **Debug**, clique em ![7bdc150b4ddfdab3.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/7bdc150b4ddfdab3.png?hl=pt-br) **Resume Program**. A caixa de texto será criada.
4. No emulador ou dispositivo, digite uma letra na caixa de texto. A execução do app é pausada novamente quando atinge o ponto de interrupção definido.

Quando você insere o texto, o callback `onValueChange` é chamado. Dentro da lambda, `it` tem o novo valor que você digitou no teclado.

Depois que o valor de "it" é atribuído a `amountInput`, o Compose aciona a recomposição com os novos dados, já que o valor observável mudou.

![987b5951f9f33262.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/987b5951f9f33262.png?hl=pt-br)

5. No painel **Debug**, clique em ![7bdc150b4ddfdab3.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/7bdc150b4ddfdab3.png?hl=pt-br) **Resume Program**. O texto inserido no emulador ou no dispositivo é mostrado ao lado da linha com o ponto de interrupção, conforme mostrado nesta imagem:

![7e7a3c1a4a64e987.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/7e7a3c1a4a64e987.png?hl=pt-br)

Esse é o estado do campo de texto.

6. Clique em ![7bdc150b4ddfdab3.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-using-state/img/7bdc150b4ddfdab3.png?hl=pt-br) **Resume Program**. O valor inserido é exibido no emulador ou no dispositivo.