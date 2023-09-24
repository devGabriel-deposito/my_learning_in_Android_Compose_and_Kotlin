- `as`: Usado para conversões de tipo.
- `as?`: Usado para conversões de tipo seguras.
- `break`: Termina a execução de um loop.
- `class`: Declara uma classe.
- `continue`: Procede para a próxima etapa do loop mais próximo.
- `do`: Inicia um loop do/while (um loop com uma pós-condição).
- `else`: Define o ramo de uma expressão `if` que é executado quando a condição é falsa.
- `false`: Especifica o valor 'false' do tipo Booleano.
- `for`: Inicia um loop `for`.
- `fun`: Declara uma função.
- `if`: Inicia uma expressão `if`.
- `in`: Especifica o objeto sendo iterado em um loop `for`.
- `is`: Verifica se um valor possui um determinado tipo.
- `null`: Representa uma referência constante que não aponta para nenhum objeto.
- `object`: Declara uma classe e sua instância ao mesmo tempo.
- `package`: Especifica o pacote para o arquivo atual.
- `return`: Retorna da função mais próxima ou função anônima.
- `super`: Refere-se à implementação da superclasse de um método ou propriedade.
- `this`: Refere-se ao receptor atual.
- `throw`: Lança uma exceção.
- `true`: Especifica o valor 'true' do tipo Booleano.
- `try`: Inicia um bloco de tratamento de exceção.
- `typealias`: Declara um tipo alias.
- `typeof`: Reservado para uso futuro.
- `val`: Declara uma propriedade somente leitura ou variável local.
- `var`: Declara uma propriedade mutável ou variável local.
- `when`: Inicia uma expressão `when`.
- `while`: Inicia um loop `while`.

## Palavras-chave Flexíveis

Os seguintes tokens atuam como palavras-chave no contexto em que são aplicáveis, mas podem ser usados como identificadores em outros contextos:

- `by`: Delega a implementação de uma interface para outro objeto.
- `catch`: Inicia um bloco que lida com um tipo específico de exceção.
- `constructor`: Declara um construtor primário ou secundário.
- `delegate`: Usado como um alvo de anotação de uso.
- `dynamic`: Referencia um tipo dinâmico no código Kotlin/JS.
- `field`: Usado como um alvo de anotação de uso.
- `file`: Usado como um alvo de anotação de uso.
- `finally`: Inicia um bloco que é sempre executado quando um bloco `try` é finalizado.
- `get`: Declara o getter de uma propriedade.
- `import`: Importa uma declaração de outro pacote para o arquivo atual.
- `init`: Inicia um bloco de inicialização.
- `param`: Usado como um alvo de anotação de uso.
- `property`: Usado como um alvo de anotação de uso.
- `receiver`: Usado como um alvo de anotação de uso.
- `set`: Declara o setter de uma propriedade.
- `setparam`: Usado como um alvo de anotação de uso.
- `value` com a palavra-chave `class`: Declara uma classe inline.
- `where`: Especifica as restrições para um parâmetro de tipo genérico.

## Palavras-chave Modificadoras

Os seguintes tokens atuam como palavras-chave em listas de modificadores de declarações, mas podem ser usados como identificadores em outros contextos:

- `abstract`: Marca uma classe ou membro como abstrato.
- `actual`: Denota uma implementação específica da plataforma em projetos multiplataforma.
- `annotation`: Declara uma classe de anotação.
- `companion`: Declara um objeto companion.
- `const`: Marca uma propriedade como uma constante em tempo de compilação.
- `crossinline`: Proíbe retornos não locais em uma lambda passada para uma função inline.
- `data`: Instrui o compilador a gerar membros canônicos para uma classe.
- `enum`: Declara uma enumeração.
- `expect`: Marca uma declaração como específica da plataforma, esperando uma implementação em módulos de plataforma.
- `external`: Marca uma declaração como implementada fora do Kotlin (acessível através de JNI ou em JavaScript).
- `final`: Proíbe a sobreposição de um membro.
- `infix`: Permite chamar uma função usando notação infix.
- `inline`: Diz ao compilador para inline uma função e as lambdas passadas para ela no local da chamada.
- `inner`: Permite referenciar uma instância da classe externa de uma classe aninhada.
- `internal`: Marca uma declaração como visível no módulo atual.
- `lateinit`: Permite a inicialização de uma propriedade não nula fora de um construtor.
- `noinline`: Desativa a inline de uma lambda passada para uma função inline.
- `open`: Permite a criação de subclasses de uma classe ou a sobreposição de um membro.
- `operator`: Marca uma função como sobrecarregando um operador ou implementando uma convenção.
- `out`: Marca um parâmetro de tipo como covariante.
- `override`: Marca um membro como uma sobreposição de um membro de uma superclasse.
- `private`: Marca uma declaração como visível na classe ou arquivo atual.
- `protected`: Marca uma declaração como visível na classe atual e em suas subclasses.
- `public`: Marca uma declaração como visível em qualquer lugar.
- `reified`: Marca um parâmetro de tipo de uma função inline como acessível em tempo de execução.
- `sealed`: Declara uma classe selada (uma classe com subclasses restritas).
- `suspend`: Marca uma função ou lambda como suspensiva (usável como uma coroutine).
- `tailrec`: Marca uma função como recursiva de cauda (permitindo ao compilador substituir recursão por iteração).
- `vararg`: Permite passar um número variável de argumentos para um parâmetro.

## Identificadores Especiais

Os seguintes identificadores são definidos pelo compilador em contextos específicos, mas podem ser usados como identificadores regulares em outros contextos:

- `field`: Usado dentro de um acessador de propriedade para se referir ao campo de suporte da propriedade.
- `it`: Usado dentro de uma lambda para se referir implicitamente ao seu parâmetro.

## Operadores e Símbolos Especiais

Kotlin suporta os seguintes operadores e símbolos especiais:

- `+`, `-`, `*`, `/`, `%` - operadores matemáticos.
  - `*` também é usado para passar uma matriz para um parâmetro vararg.
- `=` - operador de atribuição.
  - É usado para especificar valores padrão para parâmetros.
- `+=`, `-=`, `*=`, `/=`, `%=` - operadores de atribuição aumentada.
- `++`, `--` - operadores de incremento e decremento.
- `&&`, `||`, `!` - operadores lógicos 'e', 'ou', 'não' (para operações bitwise, use as funções infixas correspondentes em vez disso).
- `==`, `!=` - operadores de igualdade (traduzidos para chamadas de `equals()` para tipos não primitivos).
- `===`, `!==` - operadores de igualdade referencial.
- `<`, `>`, `<=`, `>=` - operadores de comparação (traduzidos para chamadas de `compareTo()` para tipos não primitivos).
- `[`, `]` - operador de acesso indexado (traduzido para chamadas de `get` e `set`).
- `!!` - afirma que uma expressão é não nula.
- `?.` - realiza uma chamada segura (chama um método ou acessa uma propriedade se o receptor for não nulo).
- `?:` - pega o valor à direita se o valor à esquerda for nulo (operador elvis).
- `::` - cria uma referência de membro ou uma referência de classe.
- `..`, `..<` - cria intervalos.
- `:` - separa um nome de um tipo em uma declaração.
- `?` - marca um tipo como anulável.
- `->` - separa os parâmetros e o corpo de uma expressão lambda.
  - Separa os parâmetros e a declaração de tipo de retorno em um tipo de função.
  - Separa a condição e o corpo de um ramo de uma expressão `when`.
- `@` - introduz uma anotação.
  - Introduz ou faz referência a um rótulo de loop.
  - Introduz ou faz referência a um rótulo de lambda.
  - Faz referência a uma expressão 'this' de um escopo externo.
  - Faz referência a uma superclasse externa.
- `;` - separa várias instruções na mesma linha.
- `$` - faz referência a uma variável ou expressão em um modelo de string.
- `_` - substitui um parâmetro não utilizado em uma expressão lambda.
  - Substitui um parâmetro não utilizado em uma declaração de desestruturação.