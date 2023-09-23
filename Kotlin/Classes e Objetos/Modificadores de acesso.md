No Kotlin, os modificadores de acesso `public`, `private` e `protected` ainda são usados para definir a visibilidade de membros de classes (métodos, propriedades, etc.), mas eles têm um comportamento padrão diferente do Java. Aqui está uma explicação dos modificadores de acesso no Kotlin:

1. `public` (padrão): Se você não especificar um modificador de acesso, o membro da classe será público por padrão. Isso significa que ele pode ser acessado de qualquer lugar onde a classe seja visível.
    
2. `private`: Um membro com o modificador `private` só pode ser acessado dentro da classe em que ele está definido. Ele não é visível fora dessa classe.
    
3. `protected`: Em contraste com o Java, no Kotlin, membros com o modificador `protected` são visíveis apenas dentro da classe onde são definidos e nas subclasses dessa classe. Eles não são visíveis fora da hierarquia de herança.
    

Em resumo, enquanto os modificadores de acesso `public`, `private` e `protected` são usados no Kotlin, o comportamento padrão de visibilidade é diferente do Java. Isso torna o código Kotlin mais conciso, pois você não precisa usar explicitamente `public` a menos que queira tornar um membro explicitamente público. Além disso, a visibilidade `protected` é restrita apenas às subclasses, o que é uma diferença em relação ao Java, onde a visibilidade `protected` também permite acesso nas classes do mesmo pacote.