# Quais os pré-requisitos técnicos de adesão?

## Infraestrutura para integração com a PI

Existem atualmente dois modelos de ligação entre as entidades aderentes e a Plataforma de Integração, de modo a garantir a segurança dos sistemas de informação e da informação que circula entre a Plataforma de Integração e as entidades, são eles:

* Circuito dedicado: modelo de ligação mais oneroso, mas com maior segurança e mais adequado para ligações que requerem elevado volume de tráfego e garantia de qualidade de serviço. Os custos da ligação dedicada são suportados pela entidade aderente;
* VPN sobre Internet: modelo de ligação em que a segurança da informação é garantida através da transmissão por canais cifrados e pela autenticação dos pacotes que circulam garantindo, igualmente, a integridade e privacidade dos dados. Neste modelo de ligação não é possível assegurar o nível de serviço (largura de banda). No entanto, não implica investimento das entidades aderentes.

{% hint style="info" %}
É igualmente necessário existirem regras de redes que permitam a comunicação entre os sistemas de informação na Entidade e os sistemas da Plataforma de Interoperabilidade, utilizando o protocolo HTTP.
{% endhint %}

A utilização de certificado digital para suporte a comunicação segura (HTTPS) é opcional.

## Ligação VPN

Os requisitos necessários para a ligação VPN à Plataforma de Interoperabilidade são:

* Acesso à Internet, com largura de banda disponível suficiente para assegurar a ligação em boas condições de funcionamento;
* Um endereço IP público, com conectividade para qualquer destino da Internet, para assegurar a criação do túnel _Internet Protocol Security_ (IPSec);
* Suporte de protocolos e funcionalidades no equipamento de estabelecimento da VPN de acordo com as definições que serão providenciadas durante o processo de adesão;

O equipamento deverá suportar o envio de _keepalives_ de _Dead Peer Detection_ e deverá ter a capacidade de manter e renegociar automaticamente as _Security Associations_ (SAs) de IPSec, mesmo na ausência de tráfego.

Os equipamentos deverão ainda ter capacidade para resolver os problemas de sobreposição de endereçamento que poderão existir entre os diversos clientes no acesso aos servidores da AMA - funcionalidade _Network Address Translation_ (NAT).

## Plataforma Tecnológica das entidades aderentes à PI



A Plataforma de Integração está baseada no modelo de comunicação assíncrono. As entidades asseguram o presente modelo e os seguintes requisitos na sua arquitetura:

* Representado via [WSDL 1.1](http://www.w3.org/TR/wsdl);&#x20;
  * Binding Soap 1.1 ou 1.2;&#x20;
  * XML document-style;&#x20;
* Implementação assíncrona (one-way);
* Canal de transporte HTTP;
* Utilização opcional de HTTPS;
* Utilização opcional de autenticação http basic auth;
* [WS-Addressing v1.0](http://www.w3.org/TR/ws-addr-core/), como forma de correlacionamento de mensagens em modelo de comunicação assíncrona.

{% hint style="info" %}
Garanta as recomendações WS-Interoperability Basic-Profile 1.1 ([Interoperability Testing Tools 1.1](http://www.ws-i.org/deliverables/workinggroup.aspx?wg=testingtools))
{% endhint %}

## Desenvolvimento do serviço

No âmbito de configuração de serviços e processos a serem integrados com a Plataforma de Integração, e de acordo com as necessidades, será necessário que a entidade aderente disponibilize:

* WSDL do serviço a consumir pela Plataforma de Integração, respeitando as recomendações WS-I BP 1.1;
* Caso a entidade pretenda que o serviço exposto ou consumido utilize um modelo de dados específico, necessitará de proceder à disponibilização desse Modelo de Dados (baseado em XSD), bem como as regras de normalização entre ambos os modelos de dados canónico e o modelo de dados específico.

Estas regras serão baseadas em XSLT.

No caso de um serviço fornecido (serviço novo a disponibilizar pela entidade ou para aceder a um serviço existente) é necessário entregar à equipa da Plataforma de Interoperabilidade da Administração Pública: o modelo de comunicação, análise funcional ou diagrama de sequência do processo ao qual o serviço se encontra associado.

No que diz respeito à integração orientada a serviços são aqui incluídas as normas respeitantes aos Web Services que são suportadas pelas Entidades visadas:

* A norma XML é utilizada na especificação do _Web Service_ que é invocado para executar uma determinada tarefa ou um conjunto de tarefas e assim obter um resultado específico. O XML é usado como linguagem de base para a especificação dos principais padrões que estruturam os web services:
  * WSDL – _Web Service Description Languag_e
  * SOAP – _Simple Object Application Protocol_
* Nesse âmbito, a descrição de um web servisse é efetuada através de uma estrutura WSDL que contém os detalhes de interação que é possível estabelecer com o respetivo serviço. Esta descrição contém o formato das mensagens trocadas e os respetivos protocolos de transporte. A comunicação entre os vários _web services_ e as entidades que os invocam é regrada pelo protocolo SOAP que descreve o seu modo de interação.

A utilização do protocolo SOAP na Plataforma de Integração é suportada sobre transporte em HTTP (ou HTTPS de forma opcional), que é um protocolo independente e compatível com qualquer servidor aplicacional. A utilização de SOAP sobre HTTP possui ainda como vantagens o estabelecimento simplificado a nível de regras de infraestrutura em _proxies_ e _firewall_, para além de ser atualmente considerado um protocolo que é independente do tipo de plataforma ou de linguagem usado nos diferentes sistemas.
