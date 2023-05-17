# Arquitetura de Referência para a nova geração de Serviços Públicos Digitais

## O que é?

A Arquitetura de Referência para a nova geração de serviços públicos digitais, adotada e promovida pela AMA enquanto principal organismo promotor da Transformação Digital na Administração Pública, constitui uma ferramenta fundamental para a garantia da consistência e eficácia dos serviços prestados, aproximando o cidadão dos diversos organismos públicos intervenientes, e permitindo uma visão holística do cidadão e das suas relações com a AP.

Uma Arquitetura de Referência é uma arquitetura genérica que fornece diretrizes e opções para a tomada de decisões no desenvolvimento de arquiteturas mais específicas e na implementação de soluções. (TOGAF).

Esta arquitetura de referência constitui uma fonte qualificada de informação, que fornece um vocabulário comum, “desenhos” reutilizáveis e práticas recomendadas, que orientam e restringem a instanciação das diversas arquiteturas de solução.&#x20;

As Arquiteturas de Referência são um elemento relevante da prática da Arquitetura Empresarial, dado que estabelecem um ponto de partida e de comparação no desenho de novas arquiteturas, neste caso, a arquitetura dos novos serviços públicos digitais.&#x20;

Entre os vários aspetos que uma Arquitetura de Referência pode explicitar, no presente documento explicitamos as peças (aqui designadas como Plataformas Comuns) que facilitam a construção dos novos serviços.&#x20;

Foram assim identificadas as Plataformas Comuns, que podem e devem ser utilizados pelos arquitetos, no desenho e desenvolvimento das arquiteturas de solução.&#x20;

Uma Plataforma Comum representa um componente reutilizável, que pode ser combinado com outras Plataformas Comuns para desenhar a arquitetura de soluções.&#x20;

Pretende-se então, que a nova geração de serviços públicos digitais, siga uma estrutura arquitetónica comum, estabelecida na Arquitetura de Referência aqui descrita.

## Como surgiu?

A Estratégia para a Transformação Digital da AP 2021-2026 está alinhada com o calendário de execução do Plano de Recuperação e Resiliência (PRR), mandatando o grupo de projeto denominado «Conselho para as Tecnologias de Informação e Comunicação na Administração Pública» (CTIC) para a implementação da mesma.&#x20;

A visão estratégica de Transformação Digital para a AP 2021-2026 tem como objetivo estratégico:&#x20;

* Dotar a AP de uma Arquitetura Transversal de Referência para os sistemas de informação.&#x20;

O Plano de Ação Transversal para a Transformação Digital da AP 2021-2023, Investimento TDC19-i01: Reformulação do atendimento dos serviços públicos e consulares, com o redesenho do Portal Digital Único nacional, o redesenho de serviços digitais mais utilizados e o desenvolvimento da capacidade de atendimento multicanal:

* Pretende definir a Arquitetura Empresarial, identificando componentes arquiteturais transversais de forma a melhorar a articulação e coerência dos serviços públicos, a interoperabilidade e reutilização de dados, o planeamento, e a otimização dos investimentos em TIC.

A Resolução do Conselho de Ministros n.º 131/2021 vem aprovar a Estratégia para a Transformação Digital da Administração Pública 2021-2026 e consequente Plano de Ação Transversal, em alinhamento com o calendário de execução do Plano de Recuperação e Resiliência (PRR), mandatando o grupo de projeto denominado «Conselho para as Tecnologias de Informação e Comunicação na Administração Pública» (CTIC) para a implementação da mesma.

A Estratégia para a Transformação Digital da Administração Pública 2021-2026 tem como visão uma «Administração Pública mais digital: melhores serviços, maior valor» com o objetivo de tornar a Administração Pública mais responsiva às expectativas dos cidadãos e empresas, prestando serviços mais simples, integrados e inclusivos, funcionando de forma mais eficiente, inteligente e transparente através da exploração do potencial de transformação das tecnologias digitais e da utilização inteligente dos dados. Para mais informações, consulte a [Estratégia para a Transformação Digital da AP 21-26](https://tic.gov.pt/pt/web/tic/-/aprovada-a-estrategia-para-a-transformacao-digital-da-ap-21--3).

## A quem se destina?

* **Arquitetos de Solução** - O arquiteto de solução analisa o ambiente existente, que tecnologias estão disponíveis, assim como que produto de software deve ser desenvolvido, de modo a fornecer a melhor solução para o problema que se pretende resolver.
* **Fornecedores** - Fornecedores são entidade responsáveis por prestar os serviços para desenvolvimento e implementação da Solução.
* **Prestador de Serviços Públicos Digitais** - Os Prestadores de Serviços Públicos Digitais são entidades, responsáveis por desenvolver as suas próprias soluções, que devem ter por base a Arquitetura de Referência, e que disponibilizam estes serviços aos cidadãos e empresas. Exemplo: Instituto da Habitação e da Reabilitação Urbana.
* **Utilizador dos Serviços Públicos Digitais** - Utilizador final dos Serviços Públicos Digitais. Exemplo: Cidadão, Empresa.

## Quais são os principais objetivos?

* Oferecer o ponto de partida para o desenho de arquiteturas de solução, fornecendo orientação e direção às partes interessadas. Uma vez que há um metamodelo de referência, bem como um caso de utilização, o arquiteto de solução pode/deve basear-se nesta informação para definir arquiteturas de solução.
* Apresentar de forma estruturada a descrição da arquitetura, e o seu enquadramento no desenvolvimento e utilização para soluções atuais e futuras. O processo aplicacional, que especifica o comportamento da solução, é descrito de forma que o arquiteto compreenda os componentes que podem ser reaproveitados (Plataformas Comuns), assim como os componentes aplicacionais que terá de desenvolver.
* Promover e simplificar o desenvolvimento de novas soluções, que beneficiem da adoção/reutilização das Plataformas Comuns presentes na Arquitetura de Referência. As soluções beneficiam na redução da complexidade e de recursos para o seu desenvolvimento e implementação, ao reutilizar os serviços e interfaces das plataformas comuns que se encontram em produção.

## Quais os benefícios esperados?

A análise do alinhamento de uma nova solução com as arquiteturas já definidas, possibilita ganhos a vários níveis (tangíveis), proporcionados pela reutilização de Plataformas Comuns já disponíveis:

* Redução da complexidade da solução;
* Redução de recursos necessários para o desenho e implementação;
* Fiabilidade, decorrente da utilização de Plataformas Comuns já previamente validadas;
* Redução de recursos necessários para a manutenção, que não têm de incluir recursos para a manutenção dessas plataformas.

Em termos de ganhos intangíveis, temos entre outros:

* Permitir o uso/reuso de um conjunto de peças estruturadas, numa lógica comum;
* Minimizar a diversidade de arquiteturas para resolução de problemas similares;
* Minimizar a existência de soluções redundantes;
* Aumentar a agilidade na adequação das diferentes soluções, a alterações do contexto envolvente.

{% content-ref url="conceitos.md" %}
[conceitos.md](conceitos.md)
{% endcontent-ref %}

{% content-ref url="principios-orientadores.md" %}
[principios-orientadores.md](principios-orientadores.md)
{% endcontent-ref %}

{% content-ref url="standards.md" %}
[standards.md](standards.md)
{% endcontent-ref %}

{% content-ref url="metamodelo.md" %}
[metamodelo.md](metamodelo.md)
{% endcontent-ref %}

{% content-ref url="plataformas-comuns/" %}
[plataformas-comuns](plataformas-comuns/)
{% endcontent-ref %}

{% content-ref url="padrao-de-referencia-de-solucao-aplicacional.md" %}
[padrao-de-referencia-de-solucao-aplicacional.md](padrao-de-referencia-de-solucao-aplicacional.md)
{% endcontent-ref %}

{% content-ref url="caso-de-utilizacao.md" %}
[caso-de-utilizacao.md](caso-de-utilizacao.md)
{% endcontent-ref %}
