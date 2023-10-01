## O que é uma matriz?

Uma matriz é a maneira mais simples de agrupar uma quantidade arbitrária de valores nos seus programas.

Assim como um agrupamento de painéis solares é chamado de matriz solar, uma `Array` (matriz) representa **mais de um valor**. Uma matriz é uma sequência de valores que têm o mesmo tipo de dado.

![33986e4256650b8b.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-collections/img/33986e4256650b8b.png?hl=pt-br)

- Uma matriz contém diversos valores chamados de _elementos_ ou, às vezes, _itens_.
- Os elementos de uma matriz são ordenados e acessados com um índice.

O que é um índice? É um número inteiro que corresponde a um elemento na matriz. O índice informa a distância de um item em relação ao elemento inicial de uma matriz. Isso é chamado de indexação zero. O primeiro elemento da matriz está no índice 0, já o segundo está no índice 1, porque está a uma posição do primeiro, e assim por diante.

![bb77ec7506ac1a26.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-collections/img/bb77ec7506ac1a26.png?hl=pt-br)

Na memória do dispositivo, os elementos na matriz são armazenados próximos uns aos outros. Os detalhes estão além do escopo deste codelab, mas há duas implicações importantes:

- O acesso a um elemento de matriz pelo índice é rápido. É possível acessar qualquer elemento aleatório de uma matriz pelo índice e esperar que leve o mesmo tempo para acessar qualquer outro elemento aleatório. É por isso que matrizes são conhecidas por terem _acesso aleatório_.
- Uma matriz tem um tamanho fixo. Isso significa que não é possível adicionar elementos a uma matriz que excedam esse tamanho. Tentar acessar o elemento no índice 100 em uma matriz de 100 elementos gera uma exceção, porque o índice mais alto é 99. Lembre-se de que o primeiro índice é 0, não 1. No entanto, é possível modificar os valores nos índices da matriz.

**Observação**: neste codelab, "memória" se refere à memória de acesso aleatório (RAM) de curto prazo do dispositivo, não ao armazenamento permanente de longo prazo. Ela é chamada de "acesso aleatório" porque permite acesso rápido a qualquer local arbitrário na memória.

Para declarar uma matriz no código, use a função `arrayOf()`.

![69e283b32d35f799.png](https://developer.android.com/static/codelabs/basic-android-kotlin-compose-collections/img/69e283b32d35f799.png?hl=pt-br)

A função `arrayOf()` usa os elementos da matriz como parâmetros e retorna uma matriz do tipo correspondente aos parâmetros transmitidos. Isso pode ser um pouco diferente das outras funções que mostramos, porque `arrayOf()` tem um número variável de parâmetros. Se você transmitir dois argumentos para `arrayOf()`, a matriz resultante vai conter dois elementos, indexados em 0 e 1. Se você transmitir três argumentos, a matriz resultante vai ter três elementos, indexados de 0 a 2.

Vamos explorar um pouco o sistema solar para observar as matrizes em ação.

1. Acesse o [Playground Kotlin](https://developer.android.com/training/kotlinplayground?hl=pt-br).
2. Em `main()`, crie uma variável `rockPlanets`. Chame `arrayOf()`, transmitindo o tipo `String` com quatro strings, uma para cada um dos planetas rochosos do sistema solar.

