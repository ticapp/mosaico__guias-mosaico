---
description: Descrição da Arquitetura do Serviço Digital
---

# Consultar Estado da carta de condução

Este serviço digital possibilita ao cidadão consultar o estado da carta de condução, na nova área dedicada ao condutor, no Portal Digital Único Nacional.

## Partes Interessadas

#### AMA

A **Agência para Modernização Administrativa** é o instituto público responsável pela promoção e desenvolvimento da modernização administrativa em Portugal. A sua atuação divide-se em três eixos: atendimento, transformação digital e inovação e participação, e encontra-se sob superintendência e tutela do [Secretário de Estado da Digitalização e da Modernização Administrativa](https://www.portugal.gov.pt/pt/gc23/primeiro-ministro/secretarios-de-estado?i=digitalizacooedamodernizacooadministrativa).

É responsavel pelo desenvolvimento e manutenção da nova área do condutor designada por Balcão do Condutor, no Portal Digital Único Nacional.

#### IMT

O **Instituto da Mobilidade e dos Transportes**, instituto público integrado na administração indireta do Estado, dotado de autonomia administrativa e financeira e património próprio. O IMT, I.P. sucede nas atribuições: do Instituto de Infraestruturas Rodoviárias, I.P.; do Instituto Portuário e dos Transportes Marítimos, I.P.; da Comissão de Planeamento de Emergência dos Transportes Terrestres

Disponibilizará o serviço de Consulta de Estado da carta de condução no Balcão do Condutor, proveniente do seu sistema SICC (Sistema de Informação do Condutor e da Emissão de Títulos de Condução.

## Visão da arquitetura

O Balcão do Condutor será disponibilizado no Portal Digital Único Nacional (PDUN), e nele será possivel consultar o estado da carta de condução.

O diagrama de arquitetura apresentado aqui foram definidos com base no service blueprint criado em conjunto com as partes interessadas e estão de acordo com a representação do [metamodelo](../arquitetura-de-referencia-para-a-nova-geracao-de-servicos-publicos-digitais/metamodelo.md) definido na Arquitetura de Referência para a nova geração de serviços públicos digitais. &#x20;

Apresenta:

* O processo na vertente de negócio;
* O reflexo do processo de negócio, nas etapas do processo aplicacional da solução a desenvolver.
* A realização de cada etapa do processo aplicacional quer por novos componentes a desenvolver, quer por plataformas comuns reutilizáveis.

### Necessidades de negócio

| Necessidade                                                                                                                                                 | Descrição                                                                                                                                                                                                                                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Criar o Balcão do Condutor                                                                                                                                  | <p>É necessário um ponto único de acesso, para os serviços associados ao evento conduzir um veículo em Portugal.</p><p>A criação do novo Balcão do Condutor, no PDUN, permitirá centralizar estes serviços e facilitar o seu acesso.</p>                                                                                |
| A informação resultante do serviço de consulta de estado da carta de condução é disponibilizada pelo IMT                                                    | <p>Os serviços serão apresentados na página do Balcão do Condutor, no PDUN.  </p><p>Quando o cidadão selecionar o serviço “Consulta de Estado da Carta de Condução” , o Sistema do IMT disponibilizará os resultados ao Balcão do Condutor, através de uma integração realizada pela componente *API Gateway * do PDUN. |
| Quaisquer integrações utilizam a API Gateway disponibilizada pelo PDUN                                                                                      | As integrações necessárias para realizar os serviços e apresentar os resultados ao cidadão, deverão utilizar a API Gateway.                                                                                                                                                                                             |
| Autenticar utilizando plataforma comum: plataforma do [Serviço de Autenticação](../../plataformas-comuns-da-administracao-publica/servico-de-autenticacao/) | O Balcão do Condutor deverá utilizar a plataforma comum plataforma do [Serviço de Autenticação](../../plataformas-comuns-da-administracao-publica/servico-de-autenticacao/) para o cidadão se autenticar no mesmo.                                                                                                      |

### Pressupostos

* Os serviços serão disponibilizados no Balcão do Condutor, que será acedido através do PDUN;
* 
* O Balcão do Condutor estará integrado com o Sistema SICC do IMT, responsável por disponibilizar informação sobre a carta de condução do cidadão;
* No Balcão do Condutor será apresentada uma lista de serviços relacionados ao evento de conduzir um veículo em Portugal;
* Os serviços requerem a autenticação do cidadão para serem utilizados;
* A apresentação da informação que consta no Balcão carece de consentimento/ autorização prévia do cidadão aos dados ali apresentados, aquando da primeira vez que acede à aplicação.

## Arquiterura de negócio

### Consulta de estado da carta de condução

#### **Serviço**

Consulta de Estado da carta de condução.

<figure><img src="../../.gitbook/assets/serviço-consulta-estado-cc.png" alt=""><center><p>Vista alto nível do serviço Consulta de Estado da Carta de Condução</p></center></figure>

#### **Objetos de negócio do serviço**

* Carta de condução - Documento pelo qual a habilitação de conduzir um veículo é válida.

#### **Utilizadores do serviço**

* Condutor - Acede ao Balcão do Condutor no PDUN e autentica-se com o Cartão de Cidadão ou Chave Móvel Digital. Consulta o serviço consulta de estado da carta de condução.

#### Processo de negócio

Consultar estado da carta de condução.

<figure><img src="../../.gitbook/assets/Consulta de Estado da carta de condução.png" alt=""><figcaption><p>Vista do Processo de Negócio do serviço Consultar estado da carta de condução</p></figcaption></figure>

| Atividade                                | Descrição                                                                                                                                       |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Acesso via redes sociais                 | O processo começa com o acesso do cidadão à página de Enquadramento do Balcão do Condutor, via redireccionamento de rede social.                |
| Acesso via PDUN                          | O processo começa com o acesso do cidadão ao portal digital único nacional.                                                                     |
| Acesso via motor de pesquisa             | O processo começa com o acesso do cidadão à página da ficha do serviço, via resultado de uma pesquisa na internet.                              |
| Visualizar página de enquadramento       | Na página de enquadramento do Balcão do Condutor, o cidadão seleciona o serviço, sendo encaminhado para a página da ficha do serviço do mesmo.  |
| Selecionar destaque Balcão do Condutor   | No PDUN, o cidadão seleciona o destaque do Balcão do Condutor e é encaminhado para a página de enquadramento do Balcão do Condutor.             |
| Selecionar serviço no quadro de serviços | No PDUN, o cidadão seleciona o serviço no quadro de serviços e é encaminhado para a página da ficha de serviço.                                 |
| Pesquisar e selecionar serviço           | No PDUN, o cidadão pesquisa pelo serviço e ao selecioná-lo é encaminhado para a página da ficha de serviço.                                     |
| Visualizar ficha de serviço              | Na página da ficha de serviço, é apresentada a informação sobre o serviço.                                                                      |
| Autenticar                               | O cidadão efetua o login, utilizando o cartão de cidadão, ou chave móvel digital.                                                               |
| Visualizar área Balcão do Condutor       | Após o login, o cidadão é encaminhado para a página inicial do Balcão do Condutor.                                                              |
| Consultar Estado                         | Na página inicial do Balcão do Condutor, o cidadão pode visualizar a informação referente ao estado da sua carta de condução.                   |  


## Arquitetura aplicacional

### Consulta de Estado da carta de condução

#### Processo aplicacional

Consultar Estado da carta de condução.

<figure><img src="../../.gitbook/assets/proc-app-Consulta de Estado da carta de condução.png" alt=""><figcaption><p>Vista do Processo Aplicacional do serviço Consultar Estado da Carta de Condução</p></figcaption></figure>

| Atividade                                            | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Apresentação de Conteúdos do Portal Digital Único Nacional | Apresentação de Conteúdos do Portal Digital Único Nacional                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Autenticação com single sign-on                      | <p>O cidadão seleciona o serviço a que pretende aceder no PDUN. É redirecionado para a página correspondente ao serviço, de acordo com o mapeamento definido na ficha de serviço.</p><p>Neste caso, a realização do serviço requer a prévia autenticação do cidadão.</p><p>A recolha dos dados de autenticação é feita pela Autenticação.GOV, que:</p><ul><li>informa o cidadão dos dados que serão recolhidos, de acordo com o solicitado pela solução;</li><li>aceita e valida as credenciais de autenticação introduzidas pelo cidadão;</li><li>obtém e transmite à solução, os dados solicitados.</li></ul><p>Após a autenticação com sucesso do cidadão, o controlo é atribuído à solução.</p> |
| Apresentação de conteúdos da área Balcão do Condutor | A apresentação dos conteúdos do Balcão do Condutor é gerida pela solução aplicacional Balcão do Condutor e apresentada através do PDUN. A página inicial do Balcão do Condutor apresenta informação relativa estado da carta de condução, que é disponibilizada pelo sistema SICC do IMT. Este sistema está integrado com o Balcão do Condutor através da API Gateway.                                                                                                                                                                                                                                             |
| Apresentação de Conteúdos da Área Balcão do Condutor | O Sistema SICC do IMT realiza o serviço responsável por apresentar a informação sobre o estado da carta de condução do cidadão, no Balcão do Condutor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Apresentar Estado da Carta de Condução                      | A API Gateway transmite o pedido de consulta do componente de backoffice do Sistema SICC da IMT, e este retorna a informação referente ao estado da carta de condução do cidadão, que é apresentado na página do Balcão do Condutor.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

A realização das etapas do processo aplicacional, é suportada pelo seguinte serviço público:

<figure><img src="../../.gitbook/assets/solucao-desenvolverConsulta de Estado da carta de condução.png" alt=""><figcaption><p>Vista das Solução Aplicacionais que suportam o serviço Consulta de Estado da carta de condução</p></figcaption></figure>

| Solução Aplicacional a desenvolver | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Balcão do Condutor   | <p>Aplicando uma tipologia de federação de serviços públicos, o Balcão do Condutor é acedido através do PDUN, e disponibiliza ao cidadão um “balcão” com diversos serviços relacionados ao evento conduzir em Portugal. E, toda a informação apresentada é proveniente dos sistemas das entidades através API Gateway.</p> |


E é suportada também pelas Plataformas Comuns:

<figure><img src="../../.gitbook/assets/plataformas-pdun-Consulta de Estado da carta de condução.png" alt=""><figcaption><p>Vista das Plataformas comuns utilizadas no serviço Consulta de Estado da carta de condução</p></figcaption></figure>

| Plataforma Comum                       | Serviços                                                                                                                                                                                                                                                                                             |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Portal Digital Único Nacional                       | Realiza os serviços necessários para os cidadãos descobrirem e acederem aos serviços públicos.                                                                                                                                                                                                                                        |
| Autenticação.GOV  | Realiza o serviço de autenticação no PDUN.                                                                                                                                                                                                                                               |
| Omnicanal    | Realiza os serviços relativamente ao Assistente Virtual e às APIs da gestão da informação do cidadão.                                                                                                                                                              | 

#### Arquitetura completa do serviço

<figure><img src="../../.gitbook/assets/arq-Consulta de Estado da carta de condução.png" alt=""><figcaption><p>Vista Global do serviço Consulta de Estado da carta de condução</p></figcaption></figure>

###### Definição da API "Consulta de Estado da Carta de Condução"
Pode ser consultada [aqui](https://dev-apigw-3-pdun.northeurope.cloudapp.azure.com/catalog/api/4cb63ae4-0654-4606-b63a-e406541606d9/doc?page=2615f732-ecea-4f7a-95f7-32eceaef7aee) 

