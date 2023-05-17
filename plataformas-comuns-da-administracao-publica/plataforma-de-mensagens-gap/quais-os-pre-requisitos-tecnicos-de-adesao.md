# Quais os pré-requisitos técnicos de adesão?

O equipamento deverá suportar o envio de _keepalives_ de _Dead Peer Detection_ e deverá ter a capacidade de manter e renegociar automaticamente as SA’s de IPSec, mesmo na ausência de tráfego.

Os equipamentos deverão ainda ter capacidade para resolver os problemas de sobreposição de endereçamento que poderão existir entre os diversos clientes no acesso aos servidores da AMA (funcionalidade NAT – _Network Address Translation_).

&#x20;É ainda necessária, tal como para a integração com a Plataforma de Integração, a existência de um canal seguro (PTT  ou VPN).

## Requisitos de Infraestrutura

De modo a garantir a segurança dos sistemas de informação aderentes e da informação que circula entre entidades, atualmente, existem dois modos de ligação:

* **Circuito dedicado**: maior segurança, mais onerosa e mais adequadas para ligações que requerem elevado volume de tráfego e garantia de qualidade de serviço. Se uma entidade aderente pretender uma ligação dedicada terá que suportar os seus custos;
* **VPN sobre Internet**: neste caso a segurança da informação é garantida via transmissão por canais cifrados e autenticação dos pacotes que circulam, garantindo igualmente a integridade e privacidade dos dados. Nesta ligação não é possível assegurar o nível de serviço (largura de banda), no entanto, não implica investimento das entidades aderentes.

É igualmente necessário existirem regras de redes que permitam a comunicação entre os sistemas de informação na Entidade e os sistemas da Plataforma de Interoperabilidade, utilizando o protocolo HTTP.

A utilização de certificado digital para suporte a comunicação segura (HTTPS) é opcional.

## Requisitos para ligação VPN

Os requisitos necessários para a ligação VPN à Plataforma de Interoperabilidade são:

* **Acesso à Internet**, com largura de banda disponível suficiente para assegurar a ligação em boas condições de funcionamento;
* **Um endereço IP público**, com conectividade para qualquer destino da Internet, para assegurar a criação do túnel IPSec;
* **Suporte de protocolos e funcionalidades no equipamento de estabelecimento da VPN** de acordo com as definições que serão providenciadas durante o processo de adesão;
