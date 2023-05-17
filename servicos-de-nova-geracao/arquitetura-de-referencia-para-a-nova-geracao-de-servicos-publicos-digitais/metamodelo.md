# Metamodelo

O Metamodelo é um modelo que permite explicitar que elementos são essenciais na descrição de uma arquitetura.&#x20;

Tendo em conta o âmbito e foco da Arquitetura de Referência aqui descrita, e tendo em vista a apresentação de uma arquitetura tão simples quanto possível, optou-se por apresentar apenas os elementos arquiteturais essenciais ao âmbito e objetivos da presente arquitetura, e que estão ilustrados na figura seguinte.

<figure><img src="../../.gitbook/assets/arq ref metamodelo.PNG" alt=""><figcaption><p>Metamodelo da Arquitetura de Solução</p></figcaption></figure>

Na **camada de Negócio** apresentamos:

* O Serviço Público Digital a criar, a informação necessária e resultante do serviço (Objeto de Negócio) e os papeis de negócio que acedem ao serviço (Utilizador de Serviços Digitais).
* A sequência de atividades necessárias à realização do serviço, expressa num Processo de Negócio, bem como os seus intervenientes, tanto os utilizadores do serviço, como os elementos dos organismos que asseguram a prestação do serviço (Prestador de Serviços Digitais). Podem ser adicionadas etapas que não requerem suporte tecnológico, mas traduzem a jornada de utilizador.

<figure><img src="../../.gitbook/assets/arq ref fase 1.PNG" alt=""><figcaption><p>Processo de Negócio</p></figcaption></figure>

Em síntese, um Serviço Público Digital, serve um utilizador, acede a objetos de negócio, e é realizado por um processo de negócio, que tem como intervenientes o utilizador e o prestador do Serviço Público Digital, estando este a ele assignados.&#x20;

Esta representação do negócio, apesar de ser bastante simplista, permite assegurar o alinhamento da solução aplicacional a desenvolver com o negócio que esta deverá suportar.

Na camada Aplicacional apresentamos os elementos essenciais da solução aplicacional a desenvolver:

* Processos aplicacionais, que desagregam o comportamento (funcionalidades) da solução aplicacional a desenvolver em etapas, para que, em cada etapa, se possa associar aos componentes das Plataformas Comuns a reutilizar (mais especificamente às suas interfaces), ou a novos componentes da solução a desenvolver.

<figure><img src="../../.gitbook/assets/arq ref fase 2.PNG" alt=""><figcaption><p>Processo Aplicacional</p></figcaption></figure>

* Componente aplicacional, que é usado para expressar tanto os novos componentes a desenvolver, como os componentes das plataformas comuns a reutilizar, e que realizam os processos aplicacionais.
* Interface, que se refere às interfaces dos componentes a desenvolver, e/ou dos componentes das Plataformas Comuns a reutilizar, que servem cada etapa do processo aplicacional.
* Serviço aplicacional, que se refere aos serviços realizados pelos componentes a desenvolver, e/ou aos serviços realizados pelos componentes das Plataformas Comuns a reutilizar, consumidos pela solução, através das interfaces que lhe estão assignadas.

Em síntese, a solução aplicacional a desenvolver é descrita por uma sequência de etapas de comportamento (processo aplicacional), associadas tanto a componentes a desenvolver, como a componentes reutilizáveis das Plataformas Comuns, e estas etapas são servidas por interfaces, que por sua vez estão assignadas a serviços, que são realizados pelos componentes descritos.

O relacionamento entre os elementos do metamodelo aqui expresso resultam das regras de abstração ([definição genérica ](https://pubs.opengroup.org/architecture/archimate3-doc/chap03.html#\_Toc10045295)e [definição particular ](https://pubs.opengroup.org/architecture/archimate3-doc/chap12.html#\_Toc10045442)da relação entre a camada aplicacional e camada tecnológica) e derivação de relacionamentos definidos no [Apêndice B da especificação do ArchiMate 3.1](https://pubs.opengroup.org/architecture/archimate3-doc/apdxb.html#\_Toc10045480).

Salientam-se duas características propostas por esta especificação que foram consideradas na formulação do metamodelo e na subsequente instanciação em exemplos concretos: a abstração e a derivação de relacionamentos.&#x20;

A característica de abstração permite que cada modelo represente os aspetos que são pertinentes a cada propósito de modelação. Isto é, cada conceito da linguagem deve ser usado, se e só se contribui para o enriquecimento da expressividade do modelo. Caso contrário deve optar-se por omitir conceitos. Um exemplo desta situação é quando um conceito tem uma representação fraca para a compreensão do modelo ou se conhece pouco sobre o seu papel na arquitetura. Esta característica é especialmente utilizada na presente arquitetura de referência quando se representam as dependências existentes entre a camada aplicacional e a camada tecnológica.&#x20;

O metamodelo identifica também as diversas “preocupações” relacionadas ao ambiente, ou seja, os processos de negócio que utilizam a solução aplicacional, os serviços de negócio realizados por estes processos, e também os atores e respetivos papéis servidos pelo serviço de negócio, além dos objetos de negócio acedidos.&#x20;

A característica da derivação de relacionamentos permite derivar relacionamentos indiretos entre elementos de um modelo, com base nos relacionamentos modelados. Isso permite abstrair elementos intermédios que não são relevantes para mostrar em um determinado modelo ou visão da arquitetura. As regras precisas para fazer tais derivações são especificadas no Apêndice B da especificação do ArchiMate 3.1
