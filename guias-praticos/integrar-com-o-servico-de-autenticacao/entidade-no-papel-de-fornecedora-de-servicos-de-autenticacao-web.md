---
description: >-
  A integração das entidades enquanto fornecedoras de serviços de autenticação
  pode ser feita de acordo com o protocolo SAML v2.0 ou OAuth2.
---

# Entidade no papel de fornecedora de serviços de autenticação web

## **Autenticação baseada em SAML v2.0 (**_**Security Assertion Markup Language**_**)**

O formato de dados trocados entre o Serviço de Autenticação e as entidades é baseado em SAML v2.0 (Security Assertion Markup Language), de forma a assegurar a autenticidade e integridade de todas as transações. A utilização do SAML HTTP Post Binding associado ao SAML Web Browser SSO Profile permite que a autenticação seja efetuada tecnicamente pelo browser do utilizador, sem necessidade de ligação física entre as entidades e o Serviço de Autenticação. As comunicações entre o Serviço de Autenticação e as entidades são efetuadas sobre HTTP em canal cifrado – Secure Socket Layer (SSL) ou Transport Layer Security(TLS). Esta comunicação é realizada sobre Internet.&#x20;

O Serviço de Autenticação responde à entidade com informação autorizada pelo utilizador. A resposta inclui os atributos solicitados no pedido de autenticação. Esta ligação é também efetuada sobre HTTP em canal cifrado – SSL ou TLS. A utilização de canais cifrados, associado ao formato específico SAML garante que a troca de dados seguir as seguintes considerações:&#x20;

* Privacidade de dados – a utilização de canais cifrados garante que os dados do utilizador se mantêm privados, impedindo a sua visualização por terceiros (ex. visualização de dados por sniffer de rede);&#x20;
* Integridade de dados – o protocolo SAML, através de assinatura digital nos pedidos e respostas de autenticação SAML, garante a integridade de dados de modificações não autorizadas (ex. ataque por Man-in-the Middle). De acordo com o anteriormente descrito, a utilização do Serviço de Autenticação é efetuada apenas através do ambiente Web e sobre Internet.

![](<../../.gitbook/assets/MicrosoftTeams-image (2).png>)

A imagem acima descreve as interações entre o portal da entidade e o Serviço de Autenticação, usando o browser do utilizador como intermediário. As adaptações a realizar pela entidade recaem nos pontos 2 e 4, que correspondem respetivamente à criação do pedido de autenticação SAML e no consumo da resposta proveniente do Serviço de Autenticação: &#x20;

• Pedido de autenticação – Corresponde ao pedido de identificação por parte da entidade. Permite reconhecer a origem do pedido, através da assinatura digital por um certificado digital x.509v3 associado à entidade. O pedido contém quais os atributos que devem ser obtidos (ex. NIF); &#x20;

• Resposta de autenticação – contém o resultado da autenticação efetuada pelo Serviço de Autenticação. Encontra-se na resposta os atributos solicitados previamente pela entidade. Esta mensagem é assinada digitalmente pelo Serviço de Autenticação de forma a garantir a integridade da informação.

## **Autenticação baseada em OAuth**

O FA também utiliza a autenticação Implicit Grant do OAuth2 para fazer a autenticação e devolver os atributos pedidos em três passos. Primeiro é necessário obter um token de autenticação, sendo que o processo de autenticação é semelhante ao fluxo de autenticação via SAML (inclusivamente as mensagens trocadas entre os subsistemas do FA e a CMD são feitos via SAML). De seguida é necessário fazer um pedido REST com esse token de forma a iniciar o processo de obtenção de dados, e o FA retorna um identificador do processo de autenticação que o sistema requerente deve depois utilizar para realizar um ou mais pedidos de obtenção de dados. Este fluxo assíncrono pode ser representado de forma simplificada pelo seguinte esquema:

<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption><p>Autenticação baseada em OAuth</p></figcaption></figure>

1.  É feito um pedido GET ao site do FA com os seguintes parâmetros de entrada (devem ser incluídos como query strings):

    a.      _response\_type_ - valor token;

    b.      _client\_id_ - identificador do sistema requerente, acordado previamente;

    c.       _redirect\_uri_ - url de redireccionamento para voltar para o sistema requerente. Este parâmetro é opcional e caso não seja enviado será devolvido para uma página estática do FA;

    d.      _scope_ - uma lista de atributos delimitada com um espaço entre cada um (nota: solicitar, no mínimo, o atributo [http://interop.gov.pt/MDC/Cidadao/NIC](http://interop.gov.pt/MDC/Cidadao/NIC) no caso de cidadãos que possuam nº de identificação civil, ou [http://interop.gov.pt/MDC/Cidadao/DocNumber](http://interop.gov.pt/MDC/Cidadao/DocNumber) para cidadãos estrangeiros que ainda não o tenham);

    e.       _state_ - é um parâmetro que não é utilizado de momento;

    f.         _authentication\_level_ - nível de autenticação pretendido (OPCIONAL);

    g.      _default\_selected\_tab_ - aba que aparece selecionada por defeito (OPCIONAL);

    h.      _hidden\_tabs_ - permite esconder abas. Pode ter vários valores. (OPCIONAL).
2. É pedido ao utilizador que autorize a leitura dos atributos por parte do sistema requerente. O utilizador depois pode utilizar o cartão de cidadão ou a Chave Móvel Digital para se autenticar.
3.  Assim que é validada a autenticação com sucesso, é devolvido ao sistema requerente através de parâmetros na query string:

    a.       _token\_type_ - valor Bearer;

    b.      _expires\_in_ - long representando o tempo de vida do access token;

    c.       _access\_token_ - token gerado pelo FA para se utilizar no segundo passo de obtenção dos atributos;

    d.      _refresh\_token_ - token gerado pelo FA para obter novos access\_token sem              &#x20;

    &#x20;              necessitar de efetuar nova autenticação
4.  O sistema requerente após obtenção do access token no fluxo anterior, envia-o para a API do FA através de um método POST passando um objecto JSON do tipo:

    a.      _token_ - valor do token obtido no passo anterior;

    b.      _attributesName_ - uma lista de strings dos atributos a filtrar. Este parâmetro é opcional e &#x20;

    &#x20;        caso não seja preenchido irá retornar todos os atributos relacionados com o token.

    c.      A API do FA retorna um objecto JSON com os seguintes atributos:

    &#x20;       i.       _token_ - token obtido no passo anterior;

    &#x20;       ii.      _authenticationContextId_ – Identificador do processo de autenticação.
5. O sistema requerente deve depois utilizar o token e authenticationContextId como valores query string num pedido GET para obter os valores dos atributos pedidos.
   1.  Formato do pedido GET:

       _\<autenticacao.gov.pt>?token=\<token>\&authenticationContextId=\<authenticationContextId>_
   2.  Após o FA validar o token com sucesso é devolvida a lista em JSON  de atributos com o respetivo estado e valor (se já obtido). Os atributos que ainda não tenham sido obtidos são devolvidos com o valor _null_. Como a obtenção de atributos poderá demorar algum tempo dependendo dos atributos pedidos e de sistemas externos, os atributos pedidos poderão não estar disponíveis na altura em que é feito o pedido ao sistema FA. Cabe ao sistema requerente decidir como agir nestas situações. A única restrição é que não seja efetuado mais que um pedido por segundo à API do FA. Cada atributo poderá estar num dos seguintes estados:

       **Available** – A entidade responsável pelo envio do atributo já enviou o valor;

       **NotAvailable** – A entidade responsável pelo envio do atributo não conseguiu encontrar e responder com o valor do atributo;

       **Pending** – A entidade responsável pelo envio do atributo ainda não retornou o valor.
