# Quais os pré-requisitos técnicos de adesão?

Aquando da integração de um novo Fornecedor de Atributos, existe um conjunto de requisitos que devem ser tidos em consideração:&#x20;

* Suportar comunicações com a iAP através de VPN;&#x20;
* Implementar o web service de pedido de consulta de atributos (_SCAPAttributeRequestService_.wsdl), e clientes para resposta ao pedido e validação da operação (_SCAPAttributeResponseService_.wsdl), segundo a especificação do W3C. O assincronismo será garantido pela utilização da extensão _WS-Addressing_. O _WS-Addressing_ **é necessário para enviar um** _MessageId_ e um _RelatesTo no SOAP Header_ das mensagens;&#x20;
* Identificar e devolver os atributos profissionais de um cidadão através do identificador do cidadão que é enviado ao Fornecedor de Atributos, na mensagem de pedido de atributos, juntamente com o ficheiro com a password encriptada da conta do Fornecedor de Atributos. Este identificador segue a norma ETSI 319 412-1 para cidadãos estrangeiros. Para cidadãos portugueses, são utilizados os carateres “BI” em vez de “IDC”.&#x20;
* Gerar e devolver um _Time-based One-time Password_ (TOTP) de forma a validar a operação;&#x20;
* Para os casos em que o pedido origina um erro, o Fornecedor de Atributos deverá retornar um código de erro;&#x20;
* Disponibilizar à AMA os contactos técnicos para resolução de problemas de ligação/integração;&#x20;
* Fornecer apoio presencial em todas as cerimónias e processos de inicialização no ambiente de produção.&#x20;
