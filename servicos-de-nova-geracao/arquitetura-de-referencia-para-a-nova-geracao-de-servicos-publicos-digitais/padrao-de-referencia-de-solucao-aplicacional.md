# Padrão de referência de solução aplicacional

Ao criar uma arquitetura de solução aplicacional para um Serviço Público Digital, o arquiteto deve selecionar as Plataformas Comuns que permitem responder aos requisitos funcionais, e apresentá-las no desenho da solução aplicacional a desenvolver. O padrão de referência de uma solução aplicacional é ilustrado nas abaixo, tendo como base o [metamodelo](metamodelo.md).&#x20;

Este padrão será apresentado numa aproximação top-down, que corresponde à aproximação sugerida pelo TOGAF ADM no desenho da arquitetura de uma solução. Na descrição seguinte, apenas se referem os artefactos identificados no metamodelo.

## TOGAF ADM – Visão da Arquitetura

Durante a fase de visão, identifica-se o Serviço Público Digital, os seus intervenientes (Utilizadores dos Serviços Digitais) e as necessidades informacionais (Objetos de Negócios) percecionados pelos intervenientes.

## TOGAF ADM – Arquitetura de Negócio

Nesta fase, o desenho do Serviço Público Digital começa com a modelação do seu comportamento em atividades de negócio, tal como percecionadas pelos seus participantes. Sugere-se a adoção de um método de desenho de processos (por exemplo, o “Process Modeling Method” apresentado em “Fundalemtals of Business Process Management”, by Marlon Dumas et al, Second Edition, Springer. Também acessível em [http://fundamentals-of-bpm.org/](http://fundamentals-of-bpm.org/)) e das técnicas de “Process Quality” subjacentes ao método de desenho de processos.

O resultado desta primeira iteração do desenho da arquitetura é a especificação da sequência de atividades (processos de negócio), necessárias à realização do Serviço Público Digital.

<figure><img src="../../.gitbook/assets/arq ref happy flow.png" alt=""><figcaption><p>Figura 1 - Padrão de Utilização das Plataformas Comuns - Happy-flow</p></figcaption></figure>

A Figura 1 corresponde a uma instanciação do Processo de Negócio sem situações de erros, cancelamentos nem repetições, que designamos por “happy-flow” e que traduz a sequência simples e completa do processo. O padrão proposto é uma sequência de atividades genéricas, que em vez de se designarem por A, B, C, optámos por concretizar na seguinte sequência:

* Acesso Eletrónico aos Serviços do Estado e Seleção do Serviço Digital;
* Leitura de Conteúdos;
* Autenticação no Serviço Digital;
* Preenchimento de Dados;
* Receção de Notificação;
* Receção de Documentos;
* Pagamento.

Esta é apenas uma das múltiplas sequências possíveis. No padrão incluímos também a atividade “\[…]” para expressar podem ser incluídas outras atividades, associadas a outras Plataformas Comuns, e não apenas as que estão aqui listadas.

<figure><img src="../../.gitbook/assets/arq ref fluxo etapas.PNG" alt=""><figcaption><p>Figura 2 - Padrão de Utilização das Plataformas Comuns – Fluxo de Etapas</p></figcaption></figure>

A Figura 2 apresenta as sequências possíveis do Processo de Negócio, tanto as mais curtas, por exemplo, apenas como a Leitura de Conteúdo, como as mais complexas, por exemplo com repetições, como ainda a mudança de ordem das atividades do exemplo da Figura 1.

<figure><img src="../../.gitbook/assets/arq ref padrão completo.PNG" alt=""><figcaption><p>Figura 3 - Padrão de Utilização das Plataformas Comuns - Completo</p></figcaption></figure>

A Figura 3 apresenta o padrão completo por uma questão de completude da Arquitetura de Referência. No exemplo apresentado [Caso de Utilização](caso-de-utilizacao.md), podemos ver diferentes instanciações deste processo padrão, cada um implementando um serviço digital diferente.

## TOGAF ADM – Arquitetura de Sistemas de Informação

Nesta fase desenha-se as etapas comportamentais da solução, em termos de etapas do processo aplicacional, necessárias ao suporte do processo de negócio definido na fase anterior.&#x20;

A identificação das etapas do processo aplicacional deverá ser feita de forma que, sempre que tal seja possível, estas sejam inteiramente concretizadas nas Plataformas Comuns. Para as etapas do processo aplicacional sem concretização nas Plataformas Comuns, será necessário concretizar envolvendo, também ou somente, componentes aplicacionais a desenvolver.&#x20;

Na camada de “Solução Aplicacional a Desenvolver”, da Figura 3, observa-se uma instanciação do processo aplicacional correspondente ao processo de negócio, bem como a componente aplicacional que o/os realiza.&#x20;

Nesta etapa do TOGAF ADM, após o desenho do processo aplicacional, o arquiteto deverá explicitar, para cada etapa do processo aplicacional, as interfaces das Plataformas Comuns que as serve, e em alternativa ou em simultâneo, os componentes aplicacionais a desenvolver que lhes estão assignados, tal como apresentado na Figura 3. Neste último caso, e opcionalmente caso já exista mais conhecimento sobre a estrutura dos componentes aplicacionais a desenvolver, o arquiteto poderá explicitar as etapas do processo aplicacional servidas pelas interfaces que compõem os componentes aplicacionais a desenvolver.

A camada de “Plataformas Comuns, Interfaces e Serviços” não é alvo de desenho do arquiteto, que apenas precisa de identificar interfaces. Contudo, optámos por explicitar também os elementos funcionais (serviços) e estruturais (componentes) de cada Plataforma Comum, para maior entendimento do padrão.&#x20;

As Plataformas Comuns que ficaram fora deste Padrão de Referência, podem e devem ser utilizadas no desenvolvimento de Soluções Aplicacionais. Para as incluir na arquitetura, a atividade nomeada “\[…]”, incluída no processo aplicacional, é substituída pela atividade realizada pela Plataforma Comum a adicionar.
