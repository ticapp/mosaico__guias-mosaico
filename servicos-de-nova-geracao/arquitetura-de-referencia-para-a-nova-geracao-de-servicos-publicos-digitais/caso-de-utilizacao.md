# Caso de utilização

Nesta secção pretende-se demonstrar a aplicação da Arquitetura de Referência para os novos serviços públicos, na definição da arquitetura de solução para serviço “Troca de Matrícula Estrangeira”.&#x20;

Na construção desta arquitetura de solução, foram utilizadas as etapas do Padrão de Referência descritas na secção [Padrão de Referência da Solução Aplicacional](padrao-de-referencia-de-solucao-aplicacional.md):

* TOGAF ADM – Visão da Arquitetura&#x20;
* TOGAF ADM – Arquitetura de Negócio&#x20;
* TOGAF ADM – Arquitetura de Sistemas de Informação

A arquitetura de infraestrutura está fora do âmbito deste documento. Após a receção da informação por uma das partes interessadas e do resultado de uma pesquisa no portal ePortugal.gov.pt, caraterizou-se a situação atual deste serviço.

## TOGAF ADM – Visão da Arquitetura

Durante esta fase, identificou-se o Serviço Público “Troca de Matrícula Estrangeira”, os seus intervenientes (Utilizadores dos Serviços Digitais) e as necessidades informacionais (Objetos de Negócios) percecionados pelos intervenientes.&#x20;

O serviço de troca de matrícula de um veículo estrangeiro e já registado num país terceiro é atualmente realizado pelo cidadão no IMT, através do preenchimento de um formulário, e obriga à apresentação de comprovativos da habilitação legal para conduzir, obtidos no estrangeiro, bem como de validação de residência legal em Portugal.&#x20;

O serviço é uma evolução da medida Matrícula na hora (#199 do SIMPLEX+2018) e é uma medida do LabAP (Medida 5 – Agilizar o processo de troca de matrículas de veículos), liderada pelo IMT e que conta com a participação da AT e do IRN, estando definido como base do serviço a consulta de dados por mecanismos de interoperabilidade, para confirmar os documentos e características do veículo e para o consumo de dados de identificação do proprietário para posterior emissão dos documentos nacionais – Certificado de Matrícula/Documento Único do Automóvel (DUA).

### Partes interessadas na caracterização deste serviço

* IMT - Instituto da Mobilidade e Transportes, I.P.&#x20;
* AT – Autoridade Tributária e Aduaneira&#x20;
* IRN – Instituto dos Registos e do Notariado, I.P.

### Objetos de negócio

* Matrícula portuguesa
* Matrícula estrangeira
* DUA – Documento Único Automóvel
* DUC – Documento Único de Cobrança
* DAV – Declaração Aduaneira de Veículo
* Documentos originais do veículo

### Papéis de negócio

* Utilizador Anónimo
* Utilizador autenticado
* Requerente

## TOGAF ADM – Arquitetura de Negócio

Nesta fase, o desenho do Serviço Público Digital “Troca de Matrícula Estrangeira” começa com a modelação do seu comportamento em atividades de negócio, tal como percecionadas pelos seus participantes.&#x20;

### Papeis de negócio que interagem com o processo&#x20;

* Utilizadores do serviço:
  * Utilizador Anónimo
  * Utilizador autenticado
  * Requerente
* Prestadores do serviço:
  * Funcionário de Centro de Inspeções
  * Funcionário Público

O resultado desta primeira iteração do desenho da arquitetura é a especificação da sequência de atividades (processos de negócio), necessárias à realização do Serviço Público Digital “Troca de Matrícula Estrangeira”.

### Evento

* Aceder ao ePortugal&#x20;

### Processo

* Trocar Matrícula Estrangeira

### Atividades

* Selecionar Serviço "Troca de Matrícula Estrangeira"
* Autenticar no ePortugal
* Preencher Formulário de Pedido de Troca de Matrícula
* Receber notificações email/área reservada relativas à DAV e ao DUC para pagamento
* Efetuar Pagamento
* Adquirir chapa de matrícula na loja e regularizar seguro
* Efetuar Marcação IMT / Espaços Cidadão
* Entregar documentos originais do veículo no IMT/Espaço Cidadão
* Receber notificação no email/ área reservada para aceder ao DUA eletrónico
* Rececionar cartão físico via postal
* Pagar IUC

<figure><img src="../../.gitbook/assets/arq ref trocar matricula.PNG" alt=""><figcaption><p>Processo de Negócio - Trocar Matrícula Estrangeira</p></figcaption></figure>

### Necessidades e Preocupações de negócio

| ID | Necessidade Identificada                                                   | Preocupações                                                                                                                                                                    | Solução Atual                                                                                                       |
| -- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| N1 | Capacidade de integração do ePortugal com o SIVH do IMT e com o SFA2 da AT | Interoperabilidade entre os vários sistemas de informação que permitam a disponibilização de uma visão global e integrada da informação dos procedimentos de troca de matrícula | Os funcionários do IMT tem acesso ao backoffice das plataformas do IMT e da AT onde registam os pedidos manualmente |
| N2 | Capacidade de Integração do SCCT do IMT com SFA2 da AT                     | Interoperabilidade entre os vários sistemas de informação que permitam a tramitação eficiente dos procedimentos de troca de matrícula                                           | Inexistente                                                                                                         |
| N3 | Organização dos documentos relativos ao procedimento                       | Desmaterialização de documentos que circulam para execução dos procedimentos de troca de matrícula                                                                              | Inexistente                                                                                                         |

### Constrangimentos

| ID | Constrangimento                                                                                                                                                                                                                                                                                            |
| -- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| C1 | Dependência da mudança cultural dos utilizadores nas suas atividades para a nova solução.                                                                                                                                                                                                                  |
| C2 | Os recursos tecnológicos usados pelos utilizadores do serviço sejam compatíveis com os padrões tecnológicos usados.                                                                                                                                                                                        |
| C3 | Os serviços disponibilizados pela solução pressupõem que os seus utilizadores já se encontram registados no ePortugal.GOV. O registo só é necessário para acesso à área reservada. Para executar os serviços tipicamente é apenas solicitada a autenticação pelo Cartão do Cidadão ou Chave Móvel Digital. |
| C4 | Os serviços disponibilizados pelas plataformas comuns para esta solução pressupõem que as partes interessadas procedam à respetiva adesão.                                                                                                                                                                 |

## TOGAF ADM - Arquitetura de Sistemas de Informação

Nesta fase, desenhou-se as etapas comportamentais da solução, em termos de etapas do processo aplicacional, necessárias ao suporte do processo de negócio definido na fase anterior.

Na camada de “Solução Aplicacional a Desenvolver”, podemos ver uma instanciação do processo aplicacional.

### Etapas do processo aplicacional do serviço “Troca de Matrícula Estrangeira”

* Apresentação de Conteúdos
* Chamada da Autenticação com single sign-on
* Recolha de Informação, via Formulário
* Envio de Notificações
* Desencadeamento do Workflow associado
* Integração com outras Aplicações
* Solicitação de Pagamento
* Receção do Pagamento
* Disponibiliza Documentos
* Distribuição da verba paga
* Criação de fatura única AT
* Atribuição de matrícula provisória
* Atribuição de matrícula favorável
* Registo do automóvel
* Emissão do DUA eletrônico
* Adição do DUA no id.go

<figure><img src="../../.gitbook/assets/arq ref trocar matricula processo aplicacional.PNG" alt=""><figcaption><p>Processo Aplicacional - Trocar Matrícula Estrangeira</p></figcaption></figure>

Seguidamente, modelou-se a solução que realiza as etapas do processo aplicacional. Esta solução é composta por interfaces, serviços aplicacionais e componentes aplicacionais, com a utilização dos sistemas operacionais e em produção das entidades envolvidas, onde irão decorrer os desenvolvimentos necessários para responderem às necessidades do negócio.

Podem ser adotadas outras soluções de suporte aos processos aplicacionais acima descritos, mas nesta arquitetura de solução foram contemplados apenas estes elementos.

<figure><img src="../../.gitbook/assets/arq ref trocar matricula processo aplicacional 2.PNG" alt=""><figcaption><p>Solução Aplicacional - Troca de Matrícula Estrangeira</p></figcaption></figure>

### Plataformas Comuns Utilizadas

Identificação e Autenticação

| Plataforma Comum                | Macro Serviço                           |
| ------------------------------- | --------------------------------------- |
| Fornecedor de Autenticação (FA) | Autenticação                            |
| Fornecedor de Autenticação (FA) | Obtenção de atributos cartão de cidadão |

Integração e Interoperabilidade

| Plataforma Comum                        | Macro Serviço     |
| --------------------------------------- | ----------------- |
| iAP-Plataforma de Integração da AP (PI) | Integração        |
| iAP-Plataforma de Integração da AP (PI) | Gestão do serviço |

Pagamentos

| Plataforma Comum                    | Macro Serviço                |
| ----------------------------------- | ---------------------------- |
| iAP-Plataforma de Pagamentos (PPAP) | Geração de meios de cobrança |

Atendimento/Suporte a Canais

| Plataforma Comum    | Macro Serviço                           |
| ------------------- | --------------------------------------- |
| Bolsa de Documentos | Gestão de documentos                    |
| ePortugal.gov       | Acesso eletrónico aos serviços públicos |

Mensagens e Notificações

| Plataforma Comum                                    | Macro Serviço |
| --------------------------------------------------- | ------------- |
| Plataforma de Notificações Eletrónicas da AP (SPNE) | Notificações  |

<figure><img src="../../.gitbook/assets/arq ref plataformas comuns.PNG" alt=""><figcaption><p>Plataformas Comuns Utilizadas - Troca de Matrícula Estrangeira</p></figcaption></figure>

A figura seguinte apresenta o diagrama completo:

<figure><img src="../../.gitbook/assets/arq ref trocar de matricula completo.png" alt=""><figcaption><p>Troca de Matrícula Estrangeira</p></figcaption></figure>
