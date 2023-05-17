# Entidade no papel de fornecedora de atributos

Numa fase do fluxo de autenticação, já posterior à verificação da autenticidade do Cartão de Cidadão, o Serviço de Autenticação irá obter os atributos necessários para responder ao pedido de autenticação da entidade requisitante. Caso os dados solicitados não se encontrem no certificado público do Cartão de Cidadão ou no próprio chip deste, o Serviço de Autenticação irá promover a sua obtenção junto de fornecedores de atributos externos, conforme ilustrado na figura seguinte.

![](<../../.gitbook/assets/MicrosoftTeams-image (1) (1).png>)

O pedido de obtenção de um atributo será gerado pelo Serviço de Autenticação, com o consentimento do utilizador e posteriormente enviado ao correspondente fornecedor de atributos. Este pedido materializa-se na invocação de um serviço eletrónico no respetivo fornecedor de atributos que contem a seguinte informação: &#x20;

* **Número de Pedido** – Identificador unívoco do pedido de atributos. Este dado é interno ao Serviço de Autenticação e é usado como forma de identificação e localização dos vários pedidos de atributos realizados; &#x20;
* **Identificador do Cidadão** – O pedido de atributos é acompanhado pelo respetivo identificador sectorial cifrado, proveniente da Federação de Identidades da Plataforma de Interoperabilidade. Este assegura a identificação unívoca junto do fornecedor de atributos; &#x20;
* **Prestador de Serviços Requerente** – Representa o URL como descrição do prestador de serviços que solicitou originalmente os dados; &#x20;
* **Data e hora** – Identificação temporal da criação do pedido de atributos; &#x20;
* **Nome do Cidadão** – Nome do cidadão sobre a qual os atributos se referem;&#x20;
* **Atributos solicitados** – Lista de atributos que são solicitados pelo prestador de serviços e consentidos pelo cidadão.

Os atributos são autorizados pelo utilizador no decorrer do processo de autenticação junto do Serviço de Autenticação, cujo pedido aos respetivos fornecedores será assinado digitalmente por este. Com base na assinatura digital do pedido, os fornecedores de atributos podem comprovar a sua autenticidade e validade. Após receção e validação digital de um pedido de atributos, o fornecedor do atributo deverá responder a este serviço eletrónico, com a seguinte informação:&#x20;

* **Número de Pedido** – Identificador unívoco do pedido de atributos. Este valor será igual ao número de pedido da mensagem original. Serve como elemento de relação e de apoio à localização dos vários pedidos de atributos realizados; &#x20;
* **Data e hora** – Identificação temporal da criação da resposta ao pedido de atributos; &#x20;
* **Atributos** – Lista de atributos original, com preenchimento dos respetivos valores. A cada atributo encontra-se associado um estado que identifica o resultado da operação de obtenção do valor:&#x20;
  * **Disponível** – O valor do atributo foi encontrado e devolvido. Este valor é obrigatório sempre que um atributo é devolvido com valor;
  * **Não Disponível** – Não foi possível encontrar o valor de atributo para o utilizador em causa;&#x20;
  * **Não Permitido** – O fornecedor de atributos não permitiu ativamente a obtenção de atributos.&#x20;

Devido à utilização de assinatura digital como forma de validação do pedido de atributos, o conjunto de dados validados desta forma não poderá ser alterado ou adulterado. Por esta razão, os elementos que foram alvo de validação por assinatura digital não podem ser alterados, nem mesmo pela Plataforma de Interoperabilidade, o que impossibilita a normalização de dados, vulgo “mapeamentos”.
