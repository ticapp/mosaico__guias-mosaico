# Quais os pré-requisitos técnicos de adesão?

{% hint style="info" %}
O acesso à _Application Programming Interface_ (API) do CES é realizado via _web_ _services_.
{% endhint %}

## Autenticação

O acesso aos _web services_ está protegido através de utilização do perfil da especificação “_Web Services Security UsernameToken Profile 1.1.1_”.&#x20;

A invocação dos serviços da API deverá incluir no _Simple Object Access Protocol_ (SOAP) um _header_ do tipo _WSS UsernameToken_, com o _username_ (email do utilizador portal) e a palavra-passe, em que o campo da palavra-passe é do tipo “_PasswordText_”. O CES API irá cruzar a _username_ e a palavra-passe fornecida com os utilizadores existentes no portal. A invocação do serviço é realizada se:&#x20;

* Utilizador existir como utilizador do portal;
* Palavra-passe no _usernameToken_ for correta para o utilizador em causa.

A aplicação do _UsernameToken_ adiciona também outro conjunto de mecanismos de segurança que podem impedir a invocação dos serviços, tais como:&#x20;

* Expiração do _UsernameToken;_
* Reutilização de _UsernameToken;_
* Não utilização do elemento _nonce_.

Exemplo de um pedido com com _UsernameToken_:

![](<../../.gitbook/assets/CES 1.png>)

{% hint style="info" %}
Consultar a especificação do [“_Web Services Security UsernameToken Profile 1.1.1_”](http://docs.oasis-open.org/wss-m/wss/v1.1.1/os/wss-UsernameTokenProfile-v1.1.1-os.html)
{% endhint %}

## Autorização

Adicionalmente à autenticação do pedido através do perfil _UsernameToken_ a invocação aos serviços da API possui também uma componente de autorização pelo que o utilizador autenticado necessita também de possuir um conjunto de perfis associados que permitam a invocação do serviço.&#x20;

Para que o utilizador consiga realizar com sucesso invocações à API WS necessita de pelo menos um dos seguintes papéis associados ao seu utilizador:&#x20;

·         _Administrator_&#x20;

·         Acesso API WS&#x20;
