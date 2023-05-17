# Quais os pré-requisitos técnicos de adesão?

Para a adesão, por parte de uma qualquer entidade, terão de ser assegurados os requisitos técnicos necessários, de modo que possam ser garantidos os níveis de segurança e performance requeridos a uma plataforma como a presente.

Para as Entidades aderirem, deverão respeitar a Arquitetura de Referência, o Modelo de Dados Canónico. Para além disso enumeram-se de seguida os requisitos de infraestrutura e ao nível dos web services.

### Requisitos de Infraestrutura

* Estabelecimento de comunicação segura entre os sistemas de informação da Entidade e os sistemas da Plataforma de Interoperabilidade;
* Regras de redes que permitam a comunicação entre os sistemas de informação na Entidade e os sistemas da Plataforma de Interoperabilidade, para comunicação no protocolo http;
*   Utilização (opcional) de certificado digital para suporte a comunicação segura por https;

    Contactos dos elementos responsáveis, a nível de infraestrutura, para operações de configuração e manutenção da infraestrutura de comunicação.

### Requisitos _WebServices_

* Representado via WSDL 1.1 ([http://www.w3.org/TR/wsdl](http://www.w3.org/TR/wsdl))_;_
* Binding Soap 1.1 ou 1.2;
* XML document-style;
* Implementação assíncrona (one-way);
* Canal de transporte HTTP;
* Utilização opcional de HTTPS;
* Utilização opcional de autenticação http basic auth;
* WS-Addressing v1.0 ([http://www.w3.org/TR/ws-addr-core/](http://www.w3.org/TR/ws-addr-core/)), como forma de correlacionamento de mensagens em modelo de comunicação assíncrona;
* Deve respeitar as recomendações WS-Interoperability Basic-Profile 1.1 (Interoperability Testing Tools 1.1 - [http://www.ws-i.org/deliverables/testingtools.html](http://www.ws-i.org/deliverables/testingtools.html).

Para além do indicado, a cópia de ficheiros poderá ser um aspeto muito significativo a considerar num mecanismo como o presente, pelo que neste particular, o desempenho do File Server e a largura de banda disponibilizada deverão ser corretamente dimensionados por parte da entidade aderente ao serviço.
