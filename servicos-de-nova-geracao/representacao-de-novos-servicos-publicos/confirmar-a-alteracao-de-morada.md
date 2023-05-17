---
description: Descrição da Arquitetura do Serviço Digital
---

# Confirmar a alteração de morada

No portal [ePortugal](https://eportugal.gov.pt/), o evento de vida “Mudar de Morada é Fácil”, pretende disponibilizar ao cidadão um conjunto de serviços relacionados com a mudança de morada, num ponto de acesso comum. Entre estes serviços, será disponibilizado o novo serviço digital “Confirmar alteração de morada”, de modo a simplificar o atual processo de alteração de morada por parte do cidadão.

## Partes interessadas

#### AMA

A Agência para Modernização Administrativa é o instituto público responsável pela promoção e desenvolvimento da modernização administrativa em Portugal. A sua atuação divide-se em três eixos: atendimento, transformação digital e inovação e participação, e encontra-se sob superintendência e tutela do Secretário de Estado da Digitalização e da Modernização Administrativa.

É responsável pelas Plataformas Comuns utilizadas na solução a desenvolver, descrita neste documento.

#### IRN

O Instituto dos Registos e do Notariado é um instituto público que executa e acompanha as políticas relativas aos serviços de registo, tendo em vista assegurar a prestação de serviços aos cidadãos e às empresas no âmbito da identificação civil e do registo civil, de nacionalidade, predial, comercial, de bens móveis e de pessoas coletivas. O IRN assegura, ainda, a regulamentação, o controlo e a fiscalização da atividade notarial.

No processo de alteração de morada, o IRN assegura operacionalmente a concretização do pedido de efetuado pelo cidadão.

## Visão da Arquitetura

A morada do cidadão é um dos dados guardados no cartão de cidadão. Para alterar a morada online, o cidadão pode utilizar o serviço “Alterar a morada do cartão de cidadão”, disponível no portal ePortugal, ou pode também alterá-la presencialmente, num Balcão de Atendimento.

Após receção da carta de confirmação na nova morada, o cidadão tem de confirmar o processo de alteração de morada, dentro do prazo indicado na carta. Ultrapassado o prazo indicado, não é possível confirmar a nova morada e o cidadão terá de fazer um novo pedido de alteração de morada.

Atualmente, para confirmar a morada online, o cidadão tem de utilizar a aplicação autenticação.gov para computador. Para efetuar a confirmação da morada, precisa também de um leitor de cartões, do cartão de cidadão, dos códigos PIN do cartão de cidadão, e da carta de confirmação que recebeu na nova morada.

Só quando o cidadão efetua o processo de confirmação é que a morada é alterada no chip do cartão de cidadão. É a partir dessa data que a nova morada passa a ser considerada para as entidades públicas: saúde, segurança social, finanças, registos e recenseamento eleitoral (local de voto).

No portal ePortugal, o evento de vida “Mudar de Morada é Fácil”, pretende disponibilizar ao cidadão um conjunto de serviços relacionados com a mudança de morada, num ponto de acesso comum.

Entre estes serviços, será disponibilizado o novo serviço digital “Confirmar alteração de morada”, de modo a simplificar o atual processo de confirmação de alteração de morada, por parte do cidadão.

O conjunto de serviços integrados no evento de vida “Mudar de Morada é Fácil” pretende não só aumentar o alcance destes serviços no meio digital, mas também reduzir o número de comunicações relacionadas à alteração de morada, que o cidadão precisaria de realizar para proceder a esta alteração.

O evento de vida “Mudar de Morada é Fácil”, inclui também os serviços listados na tabela abaixo.

| Serviço Digital                                             | Entidade Responsável                                             |
| ----------------------------------------------------------- | ---------------------------------------------------------------- |
| Inscrição nos serviços municipalizados de água e saneamento | Serviços da Administração local/regional (CIM’s e/ou Municípios) |
| Inscrição na Rede de Bibliotecas Municipais                 | Serviços da Administração local/regional (CIM’s e/ou Municípios) |
| Pedido de título de transporte​                             | Serviços da Administração local/regional (CIM’s e/ou Municípios) |
| Transferir educandos para a nova escola                     | Serviços da Administração Central - Educação (DGEEC)             |
| Confirmar a Alteração da Morada no Cartão de Cidadão.       | Instituto dos Registos e do Notariado, I.P. (IRN)                |

Conforme definido no Programa de Recuperação e Resiliência (PRR), estes serviços devem cumprir um conjunto de requisitos associados ao paradigma de “Serviços Públicos de Nova Geração”, nomeadamente:

* A utilização de plataformas comuns da Administração Pública;
* O reaproveitamento de dados e interoperabilidade, dados abertos;
* Assegurarem usabilidade e acessibilidade uniforme;
* Estarem disponíveis a partir de um ponto único de acesso e de uma forma omnicanal.

Os diagramas de arquitetura apresentados neste documento, foram definidos com base no _blueprint_ ([Diagrama do Serviço – Mudar de Morada é Fácil](https://labx.gov.pt/wp-content/uploads/2022/04/BLUEPRINT-Mudar-de-Morada-e-facil.pdf)) e estão de acordo com a representação do metamodelo descrito no Anexo I deste documento, conforme a “Arquitetura de Referência, para a nova geração de serviços públicos digitais”.&#x20;

Apresenta:

* O processo na vertente de negócio;
* O reflexo do processo de negócio, nas etapas do processo aplicacional da solução a desenvolver;
* A realização de cada etapa do processo aplicacional quer por novos componentes a desenvolver, quer por plataformas comuns reutilizáveis.

### Necessidades de negócio

| Necessidade                                                                            | Descrição                                                                                                                                                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Simplificar o atual processo de mudança de morada                                      | <p>É necessário simplificar o processo atual de mudança de morada do cidadão, que atualmente necessita da aplicação autenticação.gov para computador e de um leitor de cartões, para confirmação da alteração da mesma.</p><p>A confirmação de alteração de morada deverá ser feita no portal ePortugal, através do novo serviço digital “Confirmar alteração de morada”.</p> |
| Disponibilizar ao cidadão um conjunto de serviços relacionados com a mudança de morada | No portal ePortugal, o evento de vida “Mudar de Morada é Fácil”, deverá disponibilizar ao cidadão, numa área comum, um conjunto de serviços relacionados com a mudança de morada.                                                                                                                                                                                             |
| Autenticar utilizando plataforma comum autenticação.gov                                | O novo serviço de confirmação de morada, deverá utilizar a plataforma comum autenticação.gov para o cidadão se autenticar no mesmo.                                                                                                                                                                                                                                           |
| Disponibilizar informação sobre Município da nova morada                               | Após a conclusão do processo de confirmação de morada, o cidadão poderá escolher a opção “conhecer serviços disponíveis” para aceder a uma página, também disponibilizada no portal ePortugal, com os serviços disponíveis para o seu novo município.                                                                                                                         |

### Pressupostos

* A área do evento de vida “Mudar de Morada é Fácil”, no portal ePortugal, disponibilizará serviços relacionados com a mudança de morada;
* O serviço de confirmação de morada será disponibilizado na área do evento de vida “Mudar de Morada é Fácil, no portal ePortugal;
* O serviço de confirmação de morada, requer a autenticação do cidadão;
* O serviço de confirmação de morada, requer o código enviado na carta de confirmação, enviada para a morada registada no pedido de alteração de morada;
* Após conclusão do processo, será disponibilizado ao cidadão uma opção para aceder a uma página com informação sobre serviços municipais.

## Arquitetura de Negócio

### Serviço

Confirmar Alteração de Morada

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption><p>Vista alto nível do serviço</p></figcaption></figure>

### Objetos de negócio do serviço

* Cartão de Cidadão - A morada do cidadão é um dos dados guardados no cartão de cidadão.

### Utilizadores do serviço

* Cidadão - Efetua a confirmação de mudança de morada, após receção da carta de confirmação.

### Processo de negócio: confirmar alteração de morada

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption><p>Vista do Processo de Negócio: Confirmar Alteração de Morada</p></figcaption></figure>

| Atividade                           | Descrição                                                                                                                                                                                                                                                   |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Acesso ePortugal após receber carta | O processo começa com o recebimento, por parte do cidadão, de uma carta de confirmação com um código, enviada para a morada registada no pedido de alteração de morada. Após receber a carta o cidadão acede ao portal ePortugal.                           |
| Aceder Guia Prático Mudar de Casa   | No portal ePortugal, o cidadão acede à página Guia Prático - Mudar de Casa.                                                                                                                                                                                 |
| Selecionar serviço                  | Na página Guia Prático - Mudar de Casa, o cidadão seleciona serviço Confirmação de troca de morada e acede ao mesmo.                                                                                                                                        |
| Visualizar Ficha de Serviço         | O cidadão é redirecionado para a ficha de serviço, com informação sobre o mesmo.                                                                                                                                                                            |
| Autenticar                          | O cidadão efetua o login, utilizando o cartão de cidadão, ou chave móvel digital.                                                                                                                                                                           |
| Visualizar Informação do Serviço    | O cidadão é encaminhado para uma página, onde visualiza informação sobre o serviço. Nesta página, seleciona uma opção para continuar.                                                                                                                       |
| Visualizar Informação do Processo   | O cidadão é encaminhado para uma página, onde visualiza informação sobre o estado do processo de alteração de morada. Nesta página, seleciona uma opção para continuar.                                                                                     |
| Inserir Código de Confirmação       | O cidadão insere o código enviado na carta de confirmação, para a morada registada no pedido de alteração de morada                                                                                                                                         |
| Visualizar página de Conclusão      | O cidadão é encaminhado para a página de conclusão do processo. Nesta, poderá escolher a opção “conhecer serviços disponíveis” para aceder a uma página, também disponibilizada no portal ePortugal, com os serviços disponíveis para o seu novo município. |

## Arquitetura aplicacional

### Processo aplicacional

Confirmar Alteração de Morada

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Vista do Processo Aplicacional: Confirmar Alteração de Morada</p></figcaption></figure>

| Atividade                       | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Apresentação de Conteúdos       | <p>O serviço de alteração de morada é totalmente realizado pela interface do portal ePortugal.</p><p>Ao aceder ao portal ePortugal, o cidadão pode pesquisar pelos serviços disponíveis.</p><p>Ao clicar no serviço que pretende realizar, o cidadão é redirecionado para a página do mesmo.</p><p>A apresentação da página inicial é feita pela interface do ePortugal, com base na informação registada na Ficha do Serviço no CES, onde também consta o destino e o tipo do redireccionamento a realizar.</p>                                                                                                                                                                                                                                  |
| Autenticação com single sign-on | <p>O cidadão seleciona o serviço a que pretende aceder no portal ePortugal. É redirecionado para a página correspondente ao serviço, de acordo com o mapeamento definido na Ficha de Serviço.</p><p>Neste caso, a realização do serviço requer a prévia autenticação do cidadão.</p><p>A recolha dos dados de autenticação é feita pela plataforma comum “FA – Fornecedor de Autenticação”, que:</p><ul><li>informa o cidadão dos dados que serão recolhidos, de acordo com o solicitado pela solução;</li><li>aceita e valida as credenciais de autenticação introduzidas pelo cidadão;</li><li>obtém e transmite à solução, os dados solicitados.</li></ul><p>Após a autenticação com sucesso do cidadão, o controlo é atribuído à solução.</p> |
| Apresentar Formulário           | A página de confirmação disponibilizará um formulário com um campo que recebe o código de confirmação. Este formulário é disponibilizado pela solução SAM.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

A realização das etapas do processo aplicacional, é suportada pela solução:

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption><p>Vista da Solução Aplicacional que suporta o serviço</p></figcaption></figure>

| Solução Aplicacional | Serviços                                                                                            |
| -------------------- | --------------------------------------------------------------------------------------------------- |
| SAM                  | A solução SAM disponibiliza no portal ePortugal os serviços relacionados com a alteração de morada. |

E é suportada também pelas Plataformas Comuns:

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption><p>Vista das Plataformas comuns utilizadas no serviço</p></figcaption></figure>

| Plataforma Comum                       | Serviços                                                                                                                                                                                             |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FA - Fornecedor de Autenticação        | Realiza o serviço de autenticação no portal ePortugal.                                                                                                                                               |
| ePortugal.gov                          | É através da interface do portal ePortugal, da aplicação ePortugal.gov, que o serviço de confirmação de alteração de morada é realizado.                                                             |
| Catálogo de Entidades e Serviços (CES) | A apresentação da página inicial feita pela interface do ePortugal, tem como base a informação registada na Ficha do Serviço no CES, onde consta o destino e o tipo do redireccionamento a realizar. |

### Arquitetura completa do serviço confirmação de alteração de morada

<figure><img src="../../.gitbook/assets/confirmar morada 1 (1).png" alt=""><figcaption><p>Vista Global do serviço</p></figcaption></figure>

A representação apresentada tem por base o [metamodelo ](../arquitetura-de-referencia-para-a-nova-geracao-de-servicos-publicos-digitais/metamodelo.md)e os respetivos artefactos, descritos na [Arquitetura de Referência para a nova geração de Serviços Públicos Digitais](../arquitetura-de-referencia-para-a-nova-geracao-de-servicos-publicos-digitais/).&#x20;
