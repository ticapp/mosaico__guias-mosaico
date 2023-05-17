# Autenticação de um utilizador junto de uma entidade utilizando o Cartão do Cidadão

A figura seguinte pretende exemplificar, de forma sumária e transversal, a utilização do Serviço de Autenticação com base num caso de uso de autenticação de um utilizador junto de uma entidade utilizando o Cartão de Cidadão.

![](<../../.gitbook/assets/MicrosoftTeams-image (3) (1).png>)

No diagrama acima identificam-se as seguintes interações: &#x20;

**1.** O utilizador pretende aceder à área privada do portal de uma entidade, na qual é necessário que comprove a sua identidade; &#x20;

**2.** O portal da entidade delega a autenticação e redireciona o utilizador para o Serviço de Autenticação, juntamente com um pedido de autenticação assinado digitalmente; &#x20;

**3.** O Serviço de Autenticação valida o pedido de autenticação recebido e solicita a autenticação do utilizador com recurso ao seu Cartão de Cidadão pedindo a inserção do seu PIN de autenticação. Durante este processo, o Serviço de Autenticação efetua as seguintes operações internas:

* Valida as credenciais do utilizador com recurso à PKI do Cartão de Cidadão via OCSP; &#x20;
* Obtém atributos que sejam solicitados pelo portal da entidade junto dos vários fornecedores de atributos qualificados. Esta operação é efetuada via Plataforma de Interoperabilidade. Este processo pode incluir a obtenção de dados da Federação de Identidades ou de outras Entidades.

**4.** A identificação e atributos do utilizador são autenticadas e assinados digitalmente pelo Serviço de Autenticação, após o que redireciona o utilizador de volta ao portal da entidade original. Cabe à entidade a validação das credenciais do Serviço de Autenticação e utilização dos atributos do cidadão

Como referido no processo de autenticação poderão ser solicitados mais dados que os presentes no chip do Cartão de Cidadão ou do certificado digital de autenticação, mostra-se necessário a obtenção destes dados junto de fornecedores de atributos qualificados para o efeito. Define-se como um **Fornecedor de Atributos** uma entidade que possua e disponibilize, de acordo com a identificação e autorização (explícita ou implícita) do utilizador, dados qualificados sobre ele.
