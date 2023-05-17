# Quais os pré-requisitos técnicos de adesão?

A PPAP funciona através de Webservices numa arquitetura síncrona. Os Webservices podem ser suportados por “Web Services Enhancements” (WSE 3.0) ou Windows Communication Foundation (WCF). Poderão ser igualmente desenvolvidos utilizando a tecnologia Java.

{% hint style="info" %}
**É necessária, tal como para a integração com a Plataforma de Integração a existência de um canal seguro** (Ponto de Troca de Tráfego - PTT ou Virtual Private Network - VPN).
{% endhint %}

A comunicação da informação é efetuada por pedido e com prévia autenticação, através de ligação segura a estabelecer entre os sistemas de informação da Entidade Aderente e a PPAP.  &#x20;

Atualmente existem dois modos de ligação possíveis:  &#x20;

* Preferencial - Acesso via PTT em que as Entidades Aderentes estabelecem uma ligação ao PTT onde a AMA também já possui ligações estabelecidas. Este é o formato preferencial por garantir maior segurança e redundância. Neste caso a Entidade Aderente deverá contactar a entidade gestora do PTT (Entidade de Serviços Partilhados da Administração Pública - eSPap) para o estabelecimento da conetividade; &#x20;
* Alternativo - VPN sobre Internet onde a segurança da informação é garantida via transmissão por canais cifrados e autenticação dos pacotes que circulam, garantindo a integridade e privacidade dos dados;  &#x20;

Deverão também ser fornecidos contactos dos elementos responsáveis, a nível de infraestrutura, para operações de configuração e manutenção da infraestrutura de comunicação.&#x20;
