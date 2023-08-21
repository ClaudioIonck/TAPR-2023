# Tópicos Avançados em Programação (TAPR)
## Introdução sobre Microsserviços

### [Link: Definição de Microsserviços](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/microservices-architecture?WT.mc_id=AZ-MVP-5003638)

### Perguntas
- Como se dá a comunicação entre os microsserviços?
  
A comunicação entre microsserviços geralmente é feita por meio de protocolos de rede, como HTTP/HTTPS, gRPC, ou até mesmo mensagens assíncronas, como AMQP (Advanced Message Queuing Protocol). Os microsserviços podem se comunicar de várias maneiras, como chamadas síncronas (requisições HTTP) ou assíncronas (mensagens em fila). APIs bem definidas são usadas para permitir que os microsserviços troquem informações e realizem operações.
- Como é feito o armazenamento dos dados de cada microsserviço?

Cada micro serviço pode ter seu próprio banco de dados ou sistema de armazenamento. Esses bancos de dados podem variar de acordo com as necessidades específicas do microsserviço. Isso pode levar a um cenário de dados distribuídos, onde diferentes microsserviços têm controle sobre diferentes partes dos dados. Também é possível utilizar bancos de dados compartilhados ou sistemas de mensagens para manter a consistência dos dados entre os microsserviços.
- Qual a relação entre o tamanho do microsserviço e seu [acoplamento](https://pt.wikipedia.org/wiki/Acoplamento_fraco)?

Geralmente, há uma relação entre o tamanho de um micro serviço e seu nível de acoplamento com outros microsserviços. Microsserviços menores tendem a ser mais independentes e desacoplados, o que facilita a manutenção e a escalabilidade. Microsserviços maiores podem ter mais interdependências e acoplamento, o que pode tornar as mudanças mais complexas e afetar a escalabilidade. 
- Existe uma relação entre microsserviços e as técnicas de [DEVOPS](https://pt.wikipedia.org/wiki/DevOps)?

DevOps é uma cultura e conjunto de práticas que visa integrar o desenvolvimento de software com as operações de TI. Os microsserviços se beneficiam das práticas DevOps, pois a natureza distribuída e independente dos microsserviços exige uma abordagem ágil para o desenvolvimento, teste, implantação e monitoramento. Automação, integração contínua, entrega contínua e monitoramento são fundamentais para o gerenciamento eficaz de microsserviços.
- Como é feito o deployment de uma aplicação monilítica e de um microsserviço?

Na monolítica: Bild, empacotamento, provisionamento dos recursos, implantação, testes, monitoramento.
No deployment: Empacotamento, orquestração de containers, implantação individual, integração contínua, monitoramento e observabilidade, escalonamento dinâmico.

### [Link: Microsserviços - Martin Fowler](https://www.martinfowler.com/articles/microservices.html)

### Perguntas
- O que significa um microsserviço rodar em seu próprio processo?

Isolamento, escalabilidade, mudanças independentes, resiliência, gerenciamento de recursos.
- Como pode ser feita a escalabilidade horizontal de uma aplicação monolítica?

Divisão funcional, cache, load balancing, stateless design, banco de dados escalável, contêineres e orquestração, escalabilidade elástica, arquitetura em camadas 
- Qual situação que uma mudança no código de um monolito pode ocasionar?

Uma mudança no código de um monolito pode resultar em várias situações, como quebra de funcionalidades, interrupção de serviço, impacto em partes relacionadas do sistema, degradação de desempenho, problemas de escalabilidade e necessidade de migração de dados. Pode ser necessário reverter a mudança, aumentar os testes, treinamento adicional e aprovações extras. Um processo de desenvolvimento sólido, testes rigorosos e planejamento de implantação são essenciais para minimizar esses impactos.
- Em qual situação seria necessário atualizar diversos microsserviços ao mesmo tempo?

A atualização simultânea de vários microsserviços é evitada, mas pode ser necessária em situações como mudanças de interface, correções de segurança, dependências específicas, atualizações de infraestrutura compartilhada, lançamentos estratégicos ou migrações em lote. No entanto, a coordenação deve ser cuidadosamente planejada para minimizar riscos e impactos indesejados. Geralmente, a abordagem preferida é permitir a atualização independente de cada micro serviço.
- Como devem ser organizadas as equipes que vão construir os microsserviços?

As equipes de construção de microsserviços devem ser multidisciplinares, focadas em microsserviços específicos e com comunicação eficiente. Elas devem seguir arquiteturas e padrões compartilhados, ter orientação ao produto, ser escaláveis e buscar feedback constante. A automação é fundamental para agilidade e qualidade.
- Qual a relação de responsabilidade das equipes sobre o ciclo de vida dos microsserviços?

Planejamento e Design: Definição de requisitos, arquitetura e escolha de tecnologias.
Desenvolvimento: Implementação, testes e documentação.
Implantação e Entrega: Configuração de pipelines de implantação e garantia de segurança.
Operações e Monitoramento: Monitoramento de desempenho, resolução de problemas e escalabilidade.
Manutenção e Evolução: Atualizações, melhorias e compatibilidade.
Aposentadoria ou Substituição: Avaliação e gestão da retirada ou substituição do serviço.

- O que são os Enterprise Service Bus e qual sua relação com o padrão SOA?

O Enterprise Service Bus (ESB) é uma parte importante da arquitetura orientada a serviços (SOA). Ele atua como um intermediário que facilita a comunicação e integração entre diferentes sistemas e serviços em uma empresa. O ESB fornece recursos como roteamento, transformação e segurança de mensagens, ajudando a simplificar a complexidade da integração. Ele está intimamente relacionado ao padrão SOA, pois ajuda a implementar os princípios de exposição, reutilização e coordenação de serviços independentes em um ambiente empresarial. Em resumo, o ESB é uma peça-chave para criar, integrar e gerenciar serviços distribuídos de acordo com os princípios da arquitetura orientada a serviços.
- Qual o impacto da mudança entre da técnica de comunicação in-process dos monolitos para o padrão de Remote Procedure Call dos microsserviços?

Desacoplamento: Microsserviços se tornam independentes, permitindo escalabilidade e atualizações independentes.
Escalabilidade: Microsserviços podem ser escalados individualmente, otimizando recursos.
Integração Heterogênea: Diferentes tecnologias podem ser usadas em microsserviços.
Flexibilidade: RPC suporta sistemas distribuídos e integração entre diferentes componentes.

- O que é o conceito de ["paved road"](https://netflixtechblog.com/how-we-build-code-at-netflix-c5d9bd727f15) usado pelo Netflix?

O conceito de "paved road" da Netflix envolve fornecer às equipes de desenvolvimento um caminho pavimentado com ferramentas, padrões e orientações pré-aprovados. Isso promove a padronização, aumenta a produtividade, melhora a qualidade e permite o compartilhamento de conhecimento. Embora pareça contraintuitivo, isso pode realmente aumentar a agilidade, pois as equipes podem focar nas características do serviço em vez de lidar com a infraestrutura básica repetidamente. A abordagem busca equilibrar a consistência com a flexibilidade, melhorando a eficiência e a qualidade em toda a organização.
- O que é o padrão de contratos de comunicação [Tolerant Reader](https://www.martinfowler.com/bliki/TolerantReader.html)?

O padrão Tolerant Reader (Leitor Tolerante) é uma abordagem de design em que um sistema é projetado para ser capaz de lidar com diferentes versões das mensagens ou objetos que ele recebe. Isso significa que, mesmo que as mensagens evoluam ou mudem ao longo do tempo, o sistema ainda pode processar e interpretar essas mensagens sem quebrar. Em resumo, o padrão Tolerant Reader permite que sistemas recebam e processem dados de versões anteriores e futuras de mensagens, tornando a evolução do sistema mais flexível.
- Microsserviços devem compartilhar uma única instância de banco de dados?

Não é recomendado que microsserviços compartilhem uma única instância de banco de dados, pois isso pode causar problemas de desempenho, complexidade e acoplamento indesejado entre os serviços. Em vez disso, cada micro serviço deve ter seu próprio banco de dados isolado para garantir independência, escalabilidade e manutenção mais eficaz.
- O que é Continuous Delivery e Continuous Integration?

Continuous Integration (Integração Contínua): Prática onde os desenvolvedores integram frequentemente seu código em um repositório compartilhado, com testes automatizados para identificar problemas cedo.
- Por que a tolerância a falhas é um requisito fundamental para microsserviços?

A tolerância a falhas é crucial para microsserviços porque esses componentes individuais são executados de forma independente e frequentemente se comunicam através de redes. Falhas em um micro serviço podem ocorrer devido a vários fatores, como problemas de rede, falhas de hardware ou erros de software. Portanto, a tolerância a falhas é um requisito fundamental para garantir que, mesmo quando um ou mais microsserviços falharem, o sistema como um todo continue funcionando de maneira confiável e sem interrupções, mantendo a disponibilidade e a confiabilidade do serviço para os usuários. Isso envolve estratégias como replicação, isolamento, tratamento de erros e projetar microsserviços para lidar com falhas de maneira resiliente.

### Domain-Driven Design e Bounded Contexts

### [Livro BUILDING EVENT-DRIVEN MICROSERVICES](https://www.amazon.com/Building-Event-Driven-Microservices-Leveraging-Organizational/dp/1492057894/ref=sr_1_1?keywords=building+event+driven+microservices&qid=1692051103&sprefix=building+event%2Caps%2C290&sr=8-1&asin=1492057894&revisionId=&format=4&depth=1)

### [Domain-Driven Design](https://blog.xpeducacao.com.br/domain-driven-design-ddd/)

### Perguntas
- Definir, segundo o DDD, Domain, Subdomain, Domain Model e Bounded context?
