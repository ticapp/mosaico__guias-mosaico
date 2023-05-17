---
description: Descrição da Arquitetura do Serviço Digital
---

# Adquirir o certificado de registo criminal por telefone

Atualmente, o pedido online do certificado de registo criminal é feito no [Portal Registo Criminal](https://registocriminal.justica.gov.pt/), com recurso a autenticação com o cartão de cidadão (com o código de autenticação e leitor de cartões), ou com a [Chave Móvel Digital](https://www.autenticacao.gov.pt/a-chave-movel-digital) (CMD).

O novo serviço digital “Pedido do certificado de registo criminal de pessoas singulares no canal telefónico” será mais uma opção para adquirir o certificado de registo criminal, disponibilizada ao cidadão, usando o canal telefónico, sendo o processo conduzido por um Operador.

## Partes interessadas

#### AMA

A Agência para Modernização Administrativa é o instituto público responsável pela promoção e desenvolvimento da modernização administrativa em Portugal. A sua atuação divide-se em três eixos: atendimento, transformação digital e inovação e participação, e encontra-se sob superintendência e tutela do [Secretário de Estado da Digitalização e da Modernização Administrativa](https://www.portugal.gov.pt/pt/gc23/primeiro-ministro/secretarios-de-estado?i=digitalizacooedamodernizacooadministrativa).

É responsável pelas Plataformas Comuns utilizadas na solução a desenvolver, descrita neste documento.

O novo Balcão do Condutor será será desenvolvido pela AMA, no portal ePortugal.

#### DGAJ

A Direção-Geral da Administração da Justiça é um serviço do Ministério da Justiça que tem por missão assegurar o apoio ao funcionamento dos tribunais.

Gere atualmente o Portal Registo Criminal que disponibiliza os serviços de Pedido do certificado de registo criminal e Consulta de certificados.

## Visão da arquitetura

Atualmente o certificado de registo criminal pode ser pedido presencialmente, por pessoa de qualquer nacionalidade, com documento de identificação válido (cartão de cidadão, passaporte, título de residência) em qualquer posto de atendimento onde é possível a emissão de certificados; ou online, através do Portal Registo Criminal, apenas disponivel para cidadãos portugueses.

No Portal Registo Criminal, o cidadão escolhe a opção “Pedido de Certificado”, e autentica-se com o cartão de cidadão (com o código de autenticação e leitor de cartões), ou com a Chave Móvel Digital (CMD).  De seguida, o cidadão acede e preenche um formulário para a submissão do pedido. Findo a submissão do pedido, é-lhe exigido o pagamento da taxa devida, que poderá ser efetuado por referência multibanco ou por cartão de crédito. &#x20;

O certificado de registo criminal é disponibilizado no Portal Registo Criminal logo que emitido, através da opção "Os Meus Pedidos", mediante prévia autenticação. É emitido em versão bilingue português/inglês e assinado eletronicamente pelos Serviços de Identificação Criminal. &#x20;

No certificado de registo criminal consta um código de acesso que permite, durante a sua validade, a obtenção eletrónica de um certificado atualizado à data e hora da consulta no Portal Registo Criminal, através da opção “Consulta de Certificado”. A data de validade do código do certificado é de 90 dias a contar da data da emissão (a data de validade consta no próprio certificado emitido).

O novo serviço digital “Pedido do certificado de registo criminal de pessoas singulares no canal telefónico” será mais um canal que permite ao cidadão adquirir o certificado de registo criminal.

O processo será realizado por dois intervenientes. O cidadão, enquanto requerente do serviço, e o operador do contact center, que irá efetuar algumas atividades ao longo do processo em nome do cidadão e guiar o cidadão nas atividades que este tem de fazer, por exemplo, a autenticação.

O cidadão despoleta o processo ao realizar uma chamada telefónica para o Contact Center. É necessário que o cidadão tenha a chave móvel digital (CMD) ativada, e a aplicação Autenticação.Gov instalada no seu telemóvel.

Ao longo da chamada, será pedido ao cidadão que autorize o acesso aos seus dados pessoais. O cidadão receberá um pedido de autorização, na aplicação Autenticação.Gov. Para continuar o processo, e deverá escolher a opção “Autorizar”.

Após a autorização do cidadão, será gerado um código de segurança na aplicação Autenticação.Gov, que deverá ser comunicado ao Operador, de modo a possibilitar-lhe a obtenção dos dados do cidadão.

Após comunicar o código de segurança ao operador, o cidadão valida com este se os seus dados estão corretos, e se sim, o operador efetuará o pedido do certificado no Portal Registo Criminal, em nome do cidadão.

Do lado do Operador, ao aceder à aplicação de Backoffice Multicanal, terá acesso a todos os serviços passíveis de serem realizados por telefone.

No serviço Registo Criminal, deverá inserir o número de telemóvel do cidadão, validar a chave móvel digital deste, e enviar um pedido de autorização de acesso a dados.

Após a autorização do cidadão, o operador deverá validar o código de segurança fornecido pelo cidadão. Com isto, será gerado um Token a ser copiado.

O Operador deverá selecionar a opção “Serviço por Telefone” e inserir o Token previamente copiado. Após devidamente autenticado, o operador é encaminhado para uma página do serviço do registo criminal, onde poderá efetuar o pedido do certificado de registo criminal, em nome do cidadão, sendo os passos seguintes semelhantes aos do processo atual de pedido de certificado. E, por esta razão, neste documento apenas caracterizou-se apenas os as novas atividades necessárias e que antecedem o processo de pedidos de certificado de registo criminal.

Os diagramas de arquitetura apresentados neste documento, foram definidos com base na análise funcional deste serviço digital efetuada e partilhada pela equipa eID. Também, afirmamos que estão de acordo com a representação do metamodelo descrito no Anexo I deste documento, conforme a “Arquitetura de Referência, para a nova geração de serviços públicos digitais”.  Apresenta:

* O processo na vertente de negócio;
* O reflexo do processo de negócio, nas etapas do processo aplicacional da solução a desenvolver;
* A realização de cada etapa do processo aplicacional quer por novos componentes a desenvolver, quer por plataformas comuns reutilizáveis

### Necessidades de negócio

| Necessidade                                                                    | Descrição                                                                                                                                              |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Oferecer ao cidadão um novo canal para pedir o certificado de registo criminal | O pedido do certificado de registo criminal será feito através de uma chamada do cidadão ao Call Center. Este processo será conduzido por um operador. |
| Utilização da CMD                                                              | Durante o processo de pedido do certificado de registo criminal por chamada telefónica, o operador deve validar se o cidadão tem CMD ativada.          |
| Autenticar utilizando plataforma comum autenticação.gov                        | O serviço de pedido de registo criminal por canal telefónico deverá utilizar a plataforma comum autenticação.gov para realizar autenticação.           |
| Garantir a autenticidade da identidade do requerente                           | Durante o processo de pedido do certificado de registo criminal por chamada telefónica, o operador deve validar se os dados do cidadão estão corretos. |
| Disponibilizar ao Operador, uma plataforma Multicanal                          | O operador terá acesso aos serviços passíveis de serem realizados por telefone, através de uma Plataforma Multicanal.                                  |
| Aplicar normas de segurança como por exemplo o 2FA (Two Factor Authentication) | A autorização de acesso a dados, por parte do cidadão, deve ser feita através da aplicação Móvel Autenticação.gov                                      |
| Quaisquer integrações utilizam a Plataforma de Integração (iAP-PI)             | A integração dos serviços da Plataforma Multicanal e do Fornecedor de Autenticação deve ser feita através da Plataforma de Integração (iAP-PI).        |

### Pressupostos

* O cidadão tem a chave móvel digital ativada;
* O cidadão tem a aplicação autenticação.gov instalada;
* O cidadão autoriza o acesso aos seus dados através da aplicação autenticação.gov;
* O operador é responsável por conduzir o processo de pedido do certificado de registo criminal de pessoas singulares no canal telefónico;
* O operador valida a CMD e os dados do cidadão;
* Após a autenticação, o operador é reencaminhado para uma página do serviço federado do registo criminal.

## Arquitetura de negócio

#### Serviço

Pedido do certificado de registo criminal de pessoas singulares

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Vista alto nível do serviço</p></figcaption></figure>

#### Objetos de negócio do serviço

* Certificado do Registo Criminal - O registo criminal contém todos os antecedentes criminais dos cidadãos com mais de 16 anos. O certificado do registo criminal serve para atestar a existência de antecedentes criminais ou para comprovar a sua ausência.

#### Utilizadores do serviço

* Cidadão - Efetua o pedido do certificado de registo criminal, através de uma chamada telefónica ao Call Center;
* Operador - Conduz o processo de pedido do certificado de registo criminal de pessoas singulares no canal telefónico.

### Pedir o certificado de registo criminal de pessoas singulares no canal telefónico – Procedimento do Cidadão

Processo de Negócio: Pedir o certificado de registo criminal de pessoas singulares - Cidadão

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption><p>Vista do Processo de Negócio: Pedir o certificado de registo criminal de pessoas singulares - Cidadão</p></figcaption></figure>

| Atividade                                 | Descrição                                                                                               |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Realizar chamada para Contact Center      | O processo é despoletado por uma chamada do cidadão ao Contact Center.                                  |
| Receber Pedido de Autenticação Telefónica | O cidadão recebe um pedido de autorização de acesso a dados na sua aplicação Autenticação.Gov.          |
| Autorizar Acesso a Dados                  | Para continuar o processo, o cidadão deve escolher a opção “Autorizar”, na aplicação Autenticação.Gov.  |
| Fornecer Código de Segurança Gerado       | A aplicação Autenticação.Gov apresenta um código de segurança, que o cidadão deve fornecer ao operador. |
| Confirmar se os Dados estão corretos      | O cidadão, confirma com o operador se os seus dados estão corretos.                                     |

### Pedir o certificado de registo criminal de pessoas singulares no canal telefónico – Procedimento do Operador

Processo de Negócio: Pedir o certificado de registo criminal de pessoas singulares – Operador

<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption><p>Vista do Processo de Negócio: Pedir o certificado de registo criminal de pessoas singulares - Operador</p></figcaption></figure>

| Atividade                                      | Descrição                                                                                                                                                                         |
| ---------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Acesso à aplicação de Backoffice               | O operador acede ao Portal de Backoffice Autenticação.gov e visualiza os serviços passíveis de serem realizados por telefone.                                                     |
| Aceder Serviço Registo Criminal                | No Portal de Backoffice Autenticação.Gov, o operador seleciona o serviço Registo Criminal.                                                                                        |
| Validar Chave Móvel Digital                    | O operador insere o número de telemóvel e seleciona a opção “Validar Chave Móvel Digital”.                                                                                        |
| Enviar Pedido de Autorização de Acesso a Dados | O Sistema de Autorizações envia um pedido de autorização de acesso a dados à aplicação Autenticação.Gov do cidadão.                                                               |
| Validar Código de Segurança                    | O operador insere o código de segurança fornecido pelo cidadão, após este ter aceitado o pedido de autorização de acesso a dados à aplicação.                                     |
| Obter e Validar Dados                          | O Portal de Backoffice Autenticação.Gov apresenta os dados do cidadão, e o operador valida com o cidadão se estes estão corretos.                                                 |
| Confirmar e Copiar Token                       | O operador seleciona a opção “Confirmar e copiar token”.                                                                                                                          |
| Escolher opção "Serviço por Telefone"          | No Portal de Backoffice Autenticação.Gov, o Operador escolhe a opção “Serviço por Telefone”.                                                                                      |
| Colar Token                                    | O operador insere o token previamente copiado, no campo “Inserir Token”.                                                                                                          |
| Autenticar                                     | <p>O operador seleciona a opção “Autenticar”.</p><p> </p>                                                                                                                         |
| Visualizar página do Serviço Federado          | O Operador autenticado, é encaminhado para a página do serviço federado do registo criminal, onde poderá efetuar o pedido do certificado de registo criminal, em nome do cidadão. |

## Arquitetura aplicacional

### Pedir o certificado de registo criminal de pessoas singulares no canal telefónico - Procedimento aplicacional para o ponto de vista do Cidadão

Processo Aplicacional: Pedir o certificado de registo criminal de pessoas singulares no canal telefónico - Cidadão

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption><p>Vista do Processo Aplicacional do serviço - Pedir o certificado de registo criminal de pessoas singulares no canal telefónico - Cidadão</p></figcaption></figure>

| Atividade                                            | Descrição                                                                                                                                                                                 |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Apresentação de Conteúdos Ap. Móvel Autenticação.Gov | A Plataforma do Serviço de Autenticação apresenta os conteúdos ao cidadão, através da interface Aplicação Móvel Autenticação.gov.                                                         |
| Autorizar Acesso a Dados                             | O Sistema de Autorizações, integrado com a Aplicação Móvel Autenticação.gov. através da Plataforma de Integração (iAP-PI), realiza o serviço de autorização de acesso a dados do cidadão. |

### Pedir o certificado de registo criminal de pessoas singulares no canal telefónico - Procedimento aplicacional para o ponto de vista do Operador

Processo Aplicacional: Pedir o certificado de registo criminal de pessoas singulares no canal telefónico – Operador

<figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption><p>Vista do Processo Aplicacional do serviço - Pedir o certificado de registo criminal de pessoas singulares no canal telefónico - Operador</p></figcaption></figure>

| Atividade                                               | Descrição                                                                                                                            |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Apresentação de Conteúdos do Portal BO Autenticação.gov | A Plataforma do Serviço de Autenticação apresenta os conteúdos ao operador, através da interface Portal Backoffice Autenticação.Gov. |
| Validar CMD                                             | A Plataforma do Serviço de Autenticação, efetua a Validação da CMD.                                                                  |
| Pedido Autorizações                                     | O Sistema de Autorizações, efetua o Pedido de Autorização aos dados do cidadão.                                                      |
| Autenticar                                              | A Plataforma do Serviço de Autenticação realiza o serviço de autenticação, através do Portal Backoffice Autenticação.gov.            |
| Reencaminhar para página do Serviço Federado            | O Portal Backoffice Autenticação.Gov, reencaminha o operador para a página do serviço federado.                                      |

E é suportada pelas Plataformas Comuns:

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption><p>Vista das Plataformas comuns utilizadas no serviço</p></figcaption></figure>

| Plataforma Comum                      | Serviços                                                                                                                                                                                      |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Plataforma de Integração (iAP-PI)     | Realiza a integração da Plataforma do Serviço de Autenticação, que é composta pela Aplicação Móvel Autenticação.gov e pelo Portal Backoffice Autenticação.gov, com o Sistema de Autorizações. |
| Sistema de Autorizações               | Realiza os serviços de autorizações, para permitir o acesso aos dados do cidadão.                                                                                                             |
| Plataforma do Serviço de Autenticação | Realiza os serviços realizados na Aplicação Móvel Autenticação.gov e no Portal Backoffice Autenticação.gov.                                                                                   |

### Arquitetura completa

Arquitetura completa do serviço Pedido do certificado de registo criminal de pessoas singulares

<figure><img src="../../.gitbook/assets/registo criminal 1.png" alt=""><figcaption><p>Vista Global do serviço</p></figcaption></figure>

A representação apresentada tem por base o [metamodelo ](../arquitetura-de-referencia-para-a-nova-geracao-de-servicos-publicos-digitais/metamodelo.md)e os respetivos artefactos, descritos na [Arquitetura de Referência para a nova geração de Serviços Públicos Digitais](../arquitetura-de-referencia-para-a-nova-geracao-de-servicos-publicos-digitais/).
