Teste, no software, é um método estruturado de verificação do seu software para garantir que ele funcione conforme o esperado. Os testes automatizados são códigos que garantem que outro código que você escreveu funciona corretamente.

Os testes são uma parte importante do processo de desenvolvimento de apps. Executando testes no app de forma consistente, você pode verificar a precisão, o comportamento funcional e a usabilidade dele antes de o lançar publicamente.

Eles também oferecem uma maneira de verificar de forma contínua o código já existente à medida que as mudanças são introduzidas.

Embora os testes manuais quase sempre tenham um lugar garantido, no Android eles podem ser automatizados com frequência. No restante do curso, vamos focar nos testes automatizados para testar o código do app e os requisitos funcionais do app em si. Neste codelab, você vai aprender as noções básicas de testes no Android. Nos próximos, vai aprender práticas mais avançadas de teste de apps Android.

Enquanto você se familiariza com o desenvolvimento e os testes de apps Android, acostume-se a programar os testes junto com o código do app. Criar um teste sempre que um novo recurso for adicionado reduz a carga de trabalho à medida que o app crescer. Essa também é uma maneira conveniente de garantir que o app funcione bem sem gastar muito tempo com testes manuais.

Os testes automatizados são uma parte essencial de todo o desenvolvimento de softwares, e o desenvolvimento para Android não é exceção. Por isso, este é o melhor momento para falar desse assunto.

## **Por que os testes automatizados são importantes**

A princípio, pode parecer que você não precisa fazer testes no seu app, mas isso é necessário para apps de todos os tamanhos e complexidades.

Para aumentar a base de código, é necessário testar a funcionalidade existente conforme você adiciona novas partes. Isso só é possível se você já tiver testes. À medida que seu app cresce, a realização de testes manuais passa a exigir mais esforços do que os testes automatizados. Além disso, ao trabalhar em apps em fase de produção, os testes passam a ser essenciais quando se tem uma grande base de usuários. Por exemplo, é preciso considerar diversos tipos de dispositivos com diferentes versões do Android.

Por fim, chega um momento em que os testes automatizados conseguem dar conta da maioria dos casos de uso de forma significativamente mais rápida do que os testes manuais. Quando você executa testes antes de lançar um código novo, é possível fazer modificações no código para evitar lançar um app com comportamentos inesperados.

Os testes automatizados são executados por software, diferente dos manuais, que são realizados por uma pessoa que interage diretamente com um dispositivo. Os testes automatizados e manuais têm um papel essencial para garantir uma experiência agradável aos usuários do produto. No entanto, os testes automatizados podem ser mais precisos. Eles também otimizam a produtividade da equipe, porque não precisam de uma pessoa para serem feitos e porque podem ser executados de forma muito mais rápida do que um teste manual.

## **Tipos de testes automatizados**

### Testes locais

Os testes locais são um tipo de teste automatizado que verifica diretamente uma pequena parte do código para garantir o funcionamento correto. Com testes locais, é possível testar funções, classes e propriedades. Os testes locais são executados na estação de trabalho, o que significa que eles são executados em um ambiente de desenvolvimento sem a necessidade de um dispositivo ou emulador. Essa é uma maneira sofisticada de dizer que os testes locais são executados no seu computador. Como eles também têm uma sobrecarga muito baixa para recursos de computador, podem ser executados rapidamente mesmo com recursos limitados. O Android Studio já vem pronto para executar testes locais automaticamente.

### **Testes de instrumentação**

No desenvolvimento para Android, um teste de instrumentação é um teste de interface. Com os testes de instrumentação, é possível testar partes de um app que dependem da API do Android, além de serviços e APIs da plataforma.

Ao contrário dos testes locais, os de interface iniciam um app ou parte dele, simulam interações do usuário e verificam se o app reagiu corretamente. Neste curso, os testes de IU serão executados em um dispositivo físico ou um emulador.

Quando você executa um teste de instrumentação no Android, o código do teste é integrado ao próprio pacote de aplicativo Android (APK), como um app Android normal. Um APK é um arquivo compactado que contém todo o código e os arquivos necessários para executar o app em um dispositivo ou emulador. O APK de teste é instalado no dispositivo ou emulador junto ao APK normal do app. Em seguida, o APK de teste executa os testes no APK do app.