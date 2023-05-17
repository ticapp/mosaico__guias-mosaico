# Standards

Nesta secção apresentamos os standards diretamente relacionados com a Arquitetura de Referência aqui presente. O TOGAF e o ArchiMate são referências naturais, embora com uma sobreposição não pacífica em termos de conceitos.

## TOGAF

O [The Open Group Architecture Framework](https://www.opengroup.org/togaf) (TOGAF) tem diferentes elementos que referimos enquanto standard, em particular:

* O [Architecture Development Method](https://pubs.opengroup.org/togaf-standard/adm/chap01.html) (TOGAF ADM). É um standard que propomos para o desenvolvimento da Arquitetura da Solução Aplicacional que suporta os Serviços Digitais.
* Os conceitos de [Building Blocks](https://pubs.opengroup.org/architecture/togaf9-doc/arch/chap33.html). Tal como definidos no TOGAF estão na base do conceito que iremos apresentar no Metamodelo como Plataforma Comum.&#x20;

De notar que nem todo o TOGAF é adotado. De facto, os conceitos expressos no [Content Metamodel](https://pubs.opengroup.org/architecture/togaf9-doc/arch/chap30.html) (TOGAF CMM) não são compatíveis com a lista de conceitos expressos nesta Arquitetura de Referência, na qual optámos por adotar os conceitos do ArchiMate.

## ArchiMate

A arquitetura de referência é apresentada na notação [ArchiMate 3.1](https://pubs.opengroup.org/architecture/archimate3-doc/chap02.html), da qual usámos o menor conjunto de conceitos que permitisse expressar os aspetos arquiteturais relevantes para os [objetivos da Arquitetura de Referência](./).

## Service Oriented Architecture & MSA

A arquitetura presente adota o paradigma SOA, tal como entendido pelo [OpenGroup](https://www.opengroup.org/soa/source-book/soa\_refarch/index.htm), segundo o qual a arquitetura SOA é focada na reutilização de serviços, os quais devem:

* encapsular uma função de negócio;
* ser acessível por interfaces que são totalmente independentes da implementação;
* serem fracamente ligados permitindo autonomia na sua execução e manutenção.

Uma alternativa ao SOA é a Arquitetura de “Micro Serviços” (MSA[^1]), cujo objetivo é reduzir o tempo de operacionalização das correções e evoluções dos serviços. No entanto, esta redução de tempo é conseguida através da autonomia dos serviços, entenda-se a “não partilha dos serviços”, que tem como consequência a redundância funcional dos mesmos. [Ver comparação entre SOA e MSA](https://www.opengroup.org/soa/source-book/msawp/p3.htm).

## Aplication Program Interface

Nesta secção indicamos, apenas para referência, duas tecnologias em uso e que são também usadas na interação com as plataformas comuns: SOAP e REST.

* **SOAP** é um protocolo para troca de informações estruturadas num ambiente descentralizado e distribuído. As APIs projetadas com SOAP usam o XML como formato de mensagem e recebem solicitações por HTTP ou SMTP. O SOAP facilita o compartilhamento de informações por aplicações, executadas em ambientes diferentes ou escritos em linguagens diferentes. Ver a [especificação completa do protocolo SOAP](https://www.w3.org/TR/soap12/), mais atual à data presente.
* **REST** também se denomina de [API RESTful](#user-content-fn-2)[^2] e significa uma interface de programação de aplicações (API) máquina-máquina em conformidade com as restrições de uma arquitetura REST. REST significa “Representational State Transfer" e descreve uma interface uniforme entre os componentes físicos. Habitualmente usa a internet e organiza-se numa solução cliente-servidor.

## Interoperabilidade

Ao nível da interoperabilidade indicamos o conjunto de regulamentos que devem ser conhecidos e aplicados quando a arquitetura de referência for utilizada num determinado contexto:

* O [Regulamento Nacional de Interoperabilidade Digital ](https://files.dre.pt/1s/2018/01/00400/0012100127.pdf)(RNID) que define as especificações técnicas e formatos digitais, abreviadamente designados de especificações técnicas, a adotar pela Administração Pública. O RNID abrange múltiplos domínios e permite ajudar a Administração Pública em todos os processos de implementação, licenciamento ou evolução de sistemas informáticos. Em resumo, os domínios envolvidos são: formatos de dados, formatos de documentos, tecnologias de interface web, protocolos de _streaming_, protocolos de correio eletrónico, sistemas de informação geográfica, especificações técnicas e protocolos de comunicação em redes informáticas, especificações técnicas de segurança para redes e especificações técnicas e protocolos de integração;
* A [Macroestrutura Funcional](https://arquivos.dglab.gov.pt/programas-e-projectos/modernizacao-administrativa/macroestrutura-funcional-mef/) (MEF) é uma representação conceptual de funções desempenhadas por organizações do setor público. Permite definir a estrutura semântica dos documentos de arquivo e a sua gestão, promove a utilização de um esquema de meta informação e promove a sua utilização nas entidades da Administração Pública;
* A [Meta Informação para a Interoperabilidade ](https://arquivos.dglab.gov.pt/wp-content/uploads/sites/16/2013/10/MIP\_v1-0c.pdf)(MIP) promove a interoperabilidade entre organismos ao nível da utilização, gestão e acesso a recursos informativos . Segundo a definição proposta na documentação: “...a interoperabilidade equivale à capacidade de recursos de informação, sejam eles exclusivos de uma organização ou partilhados por várias organizações ao nível da responsabilidade de criação, serem reconhecidos, identificados e manipulados através de atributos que são coletivamente aceites e interpretados. A existência de um conjunto de elementos comuns a todos os recursos permite o reconhecimento imediato, mediante a observação desses elementos, da natureza e tipo de recurso existente...”. Este regulamento é recomendado pelo facto de a AR envolver interoperabilidade entre múltiplas entidades.

## Segurança

Ao nível da segurança indicamos o conjunto de regulamentos que devem ser conhecidos e aplicados quando a arquitetura de referência for utilizada num determinado contexto:

* Os requisitos técnicos definidos pela CNCS no âmbito da [Arquitetura de Segurança das Redes e Sistemas de Informação](https://www.cncs.gov.pt/docs/sama2020-rasrsi-cncs.pdf) (CNCS) apoiam as soluções a desenvolver providenciando um conjunto de requisitos que devem ser considerados na implementação do sistema de informação.

Os anteriores requisitos são subsequentemente referenciados na [Resolução do Conselho de Ministros n.º 41/2018](https://files.dre.pt/1s/2018/03/06200/0142401430.pdf).

[^1]: Bellemare, A. (2020). Building Event-Driven Microservices. " O'Reilly Media, Inc."

[^2]: Fielding, Roy Thomas (2000). "Chapter 5: Representational State Transfer (REST)". Architectural Styles and the Design of Network-based Software Architectures (Ph.D.). University of California, Irvine.
