# Get Your Hands Dirty on Clean Architecture

* **Título**: Get Your Hands Dirty on Clean Architecture: A Hands-on Guide to Creating Clean Web Applications with Code Examples in Java
* **Autor**: Tom Hombergs
* **Editora**: Leanpub
* **Ano**: 2020 (edição de 2020/01/30)
* **Páginas**: 109

![](assets/get-your-hands-dirty-on-clean-architecture.png)

## Review

Essa é a segunda review de livro que estou fazendo aqui. A minha ideia continua sendo tentar não seguir nenhum critério rígido sobre a ordem dos livros, mas, meio que por coincidência, o livro desta review é outro curtinho (109 pág.!).

O Get Your Hands Dirty on Clean Architecture (GYHDCA) do [Tom Hombergs](https://twitter.com/tomhombergs) foi um livro que achei através da página do próprio autor ([reflectoring.io](https://reflectoring.io/)). Nela, são apontadas duas opções do livro: uma da Leanpub e outra da Packt. Eu optei pela versão da Leanpub, porque parecia mais prático e tinha um cupom (quem nunca?). A versão da Packt também é encontrada em outros sites como a Amazon. Até onde sei, não há diferenças de conteúdo entre as duas versões.

Acho interessante falar da motivação por trás da compra desse livro antes. Após ler bastante material sobre Arquitetura Hexagonal (AH), e sobre a própria Clean Architecture (CA, do livro homônimo do Uncle Bob), eu estava super animado com as ideias e queria colocar a mão na massa com tudo aquilo. O problema é que poucas fontes apontavam um caminho realmente prático, hands-on, de como fazer isso tudo funcionar. Quase tudo que consegui achar na literatura e na web foi de cunho teórico com exemplos muito simples ou limitados. Apesar de ser essencial ter um entendimento sólido da teoria dessas arquiteturas, só isso não me dava a imagem completa que eu queria ter. O GYHDCA se apresenta exatamente com a proposta de preencher essa lacuna (e por isso seu nome).

(Se você ainda não conhece o que é arquitetura hexagonal e arquitetura limpa, no final desse post tem alguns links que podem te ajudar. Vale a pena conhecer :))

O livro possui 12 capítulos que basicamente cobrem a criação de uma aplicação em Java utilizando arquitetura hexagonal/clean. Ele é estruturado de forma a te dar uma visão completa do processo de adoção da AH desde porque a tradicional arquitetura em camadas pode ser um problema, passando pela organização de um projeto em Java com AH, até a junção de todas as partes resultantes da arquitetura e uma discussão final sobre trade-offs. Como o livro é relativamente curto, é bem fácil seguí-lo sem se perder e principalmente sem perder o fôlego.

Os dois primeiros capítulos fornecem os alicerces teóricos da arquitetura a ser implementada. O primeiro capítulo fica imcumbido de convencer porque a boa e velha arquitetura em camadas - praticamente a escolha padrão dos projetos - pode nos levar naturalmente a alguns problemas e, por isso, nem sempre é uma boa ideia. Assim como o livro anterior ([Migrating Microservies Databases](https://kmyokoyama.github.io/reviews/migrating-microservice-databases/)), não há espaço desperdiçado: as discussões são curtas, porém focadas.

O segundo capítulo introduz os fundamentos das arquiteturas hexagonal e clean. O maior foco é no que elas têm em comum, i.e., o princípio da inversão de dependência (Dependency Inversion Principle - DIP, o D do SOLID). Eu diria que esse é o conceito fundamental dessas arquiteturas e o princípio-mor que nos norteia durante todo processo de concepção e implementação. Enquanto esse capítulo discute sobre o que é o DIP e como a HA e a CA fazem uso dele, os próximos capítulos põem a mão na massa e constroem uma aplicação em cima desses conhecimentos.

O terceiro capitulo é dedicado a demonstrar algumas formas de organização de código, discutindo seus prós e contras e como elas podem ser melhor aproveitadas quando utilizando HA. Os dois principais objetivos aqui são explicitar as interfaces requeridas pela arquitetura e expressar o nosso domínio como sugerido pelo DDD.

Com uma estrutura de projeto no lugar, os capítulos seguintes, do 4 ao 6, implementam partes da aplicação. O quarto capítulo foca no domínio do negócio, implementando um pequeno caso de uso. Aqui acontecem algumas discussões interessantes como: o que devemos usar como modelos de entrada e saída do nosso domínio? O que deve e o que não deve ser validado na entrada? Modelagem anêmica ou rica? Como sempre, os textos são curtos, mas informativos.

O quinto capítulo mostra a implementação de um adaptador web, driver-side. Temos o primeiro exemplo prático da inversão de dependência ao conectarmos esse adaptador ao core da nossa aplicação através de interfaces. Também são levantadas questões sobre quais são as responsabilidades desse adaptador (e o que deveria ser passado as-is para o core da aplicação) e como poderíamos seccioná-lo para melhor refletir as partes do nosso domínio de negócio.

O sexto capítulo é o lado do banco de dados, um adaptador driven-side. As mesmas questões do capítulo anterior são adaptadas para esse caso. Também é discutido o uso da JPA e os seus efeitos na modelagem dos dados da aplicação (como a impedância que a introdução de anotações dependentes de framework causa entre os modelos de dados do adaptador e do core). Apesar da JPA ser particular do Java, as conclusões dessa seção podem ser facilmente extrapoladas para outros cenários.

Um dos grandes ganhos da adoção de HA/CA é na hora de testar. O sétimo capítulo aborda porque temos uma aplicação mais fácil de testar e estratégias para fazê-lo.

O oitavo capítulo, para mim, foi um dos mais interessantes. Ele trata sobre a modelagem de dados entre as partes da aplicação - adaptadores e core. Devemos reaproveitar os mesmos modelos do nosso core nos adaptadores? Quais vantagens em fazer isso e quais problemas podem surgir se decidirmos por esse caminho? Quanto de conversores entre modelos precisamos? Quais são as estratégias? Estes são exemplos de questões levantadas e respondidas nesse capítulo.

O nono capítulo levanta outra questão importante: agora que temos todas essas partes (core, interfaces e adaptadores) em conformidade com a arquitetura, como unimos tudo e levantamos a aplicação? Certamente, alguma violação do DIP precisa acontecer. O capítulo mostra como isso pode ser feito. Na prática, provavelmente utilizaremos alguma forma de injeção de dependências para manter essa violação do DIP mínima e pontual.

As arquiteturas HA, CA e variantes possuem muito fortemente o conceito de fronteiras (boundaries) e é nisso que o décimo capítulo se aprofunda. Nele, são apresentadas algumas estratégias para ressaltar a existência dessas fronteiras, nos ajudando a manter a invariante da inversão de dependência em curso.

O décimo primeiro capítulo fala sobre os trade-offs existentes e sobre como podemos tomar algumas decisões de forma consciente. Esse é um toque a mais no pragmatismo do livro. Afinal, precisamos construir softwares que resolvam problemas reais sem tornar questões teóricas em novos problemas.

O último capítulo é extremamente curto (2 pág.) para tratar do assunto de como decidir uma arquitetura. O autor enfatiza dois pontos: a) o domínio do nosso negócio é absoluto, ele deve estar no centro das nossas decisões arquiteturais sempre, e b) a experiência é uma importante aliada na hora de tomar uma decisão. Ao tentar responder a pergunta "então devo utilizar arquitetura hexagonal?", o livro encerra com um clássico (óbvio, não podia faltar): depende. Acho que a resposta não poderia mesmo ser outra.

No geral, acho que todas as seções do livro parecem ter sua raison d'être e estarem localizadas onde se espera. O livro é curtinho e obviamente não se aprofunda em todos assuntos abordados, mas acho que faz um bom trabalho ao prover insights importantes e esperados dado seu título.

Novamente, espero que essa review ajude alguém que esteja considerando uma nova leitura!

## Links

Apenas algumas referências que podem ajudar quem está conhecendo o assunto:

[Alistair Cockburn - Hexagonal Architecture](https://alistair.cockburn.us/hexagonal-architecture/)  
[Uncle Bob - The Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)  
[Tom Hombergs - Hexagonal Architecture with Java and Spring](https://reflectoring.io/spring-hexagonal/)  
[Ports and Adapters Pattern](https://jmgarridopaz.github.io/content/hexagonalarchitecture.html)  
[Ready for changes with Hexagonal Architecture](https://netflixtechblog.com/ready-for-changes-with-hexagonal-architecture-b315ec967749)  
