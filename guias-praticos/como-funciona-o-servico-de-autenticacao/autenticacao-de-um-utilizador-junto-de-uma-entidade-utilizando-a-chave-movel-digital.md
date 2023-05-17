# Autenticação de um utilizador junto de uma entidade utilizando a Chave Móvel Digital

A autenticação de um utilizador junto de uma entidade através da Chave Móvel Digital CMD), partilha grande parte do fluxo identificado para a autenticação com CC. Desse modo, o fluxo é identificado abaixo:

* O utilizador pretende aceder à área privada do portal de uma entidade, na qual é necessário que comprove a sua identidade;
* O portal da entidade delega a autenticação e redireciona o utilizador para o Serviço de Autenticação, juntamente com um pedido de autenticação assinado digitalmente;
* O Serviço de Autenticação valida o pedido de autenticação recebido e reencaminha o pedido de autenticação para a CMD;
* A CMD efetua as seguintes operações:
  * Solicita a autenticação do utilizador, pedindo a inserção de número de telemóvel ou email e PIN;
  * Valida as credenciais introduzidas e, em caso de validação com sucesso, envia um código de segurança para o telemóvel indicado;
  * O Cidadão introduz o código de segurança recebido;
  * A CMD valida o código de segurança e, em caso de validação com sucesso, retorna ao Serviço de Autenticação os atributos que conseguiu obter do utilizado que se está a autenticar.
* Serviço de Autenticação obtém os restantes atributos solicitados pelo portal da entidade junto dos vários fornecedores de atributos qualificados. Esta operação é efetuada via Plataforma de Interoperabilidade. Este processo pode incluir a obtenção de dados da Federação de Identidades ou de outras Entidades;
* A identificação e atributos do utilizador são autenticadas e assinados digitalmente pelo Serviço de Autenticação, após o que redireciona o utilizador de volta ao portal da entidade original. Cabe à entidade a validação das credenciais do Serviço de Autenticação e utilização dos atributos do cidadão.

&#x20;
