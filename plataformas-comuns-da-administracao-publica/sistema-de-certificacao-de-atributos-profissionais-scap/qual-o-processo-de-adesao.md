# Qual o processo de adesão?

No âmbito do SCAP, os Fornecedores de Atributos representam as entidades certificadoras com competência para associar determinados atributos profissionais a cidadãos.  &#x20;

A integração de novos Fornecedores de Atributos no SCAP é da responsabilidade da AMA, mediante pedido direto a esta por parte dos Fornecedores de Atributos.&#x20;

Para a adesão ao SCAP seguir os procedimentos:

![Processo de adesão ao SCAP](<../../.gitbook/assets/MicrosoftTeams-image (8) (1).png>)

| Passo                                 | Entidade Responsável           | Descrição                                                                                                                                                        |
| ------------------------------------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1.** Comunicar interesse de adesão  | Fornecedor de Atributos        | Enviar email para eid@ama.pt a formalizar a intenção de integrar com o SCAP enquanto Fornecedor de Atributos.                                                    |
| **2.** Celebrar Protocolo             | AMA e Fornecedor de Atributos  | Celebrar o Protocolo.                                                                                                                                            |
| **3.** Preencher Template             | Fornecedor de Atributos        | Preenchimento do template partilhado pelo Fornecedor de Atributos e submissão à AMA (mantendo formato word e sem qualquer assinatura).                           |
| **4.** Validar e Assinar (AMA)        | AMA                            | Validação, numeração, aceitação e assinatura pelo Conselho Diretivo da AMA.                                                                                      |
| **5.** Validar e Assinar (Fornecedor) | Fornecedor de Atributos        | Validação e assinatura do representante legal (ou representantes legais aplicáveis, de acordo com o descrito na Certidão Permanente) do Fornecedor de Atributos. |
| **6.** Entrada em Pré-Produção        | AMA e Fornecedor de Atributos  | Entrada em Ambiente de pré-produção (Ver Ambiente de pré-produção).                                                                                              |
| **7.** Entrada em Produção            | AMA e Fornecedor de Atributos  | Entrada em Produção do serviço de autenticação e assinatura com SCAP (Ver Ambiente de produção).                                                                 |

## Ambiente de Pré-produção 

| Passo                               | Entidade Responsável           | Documentos de Suporte          | Descrição                                                                                          |
| ----------------------------------- | ------------------------------ | ------------------------------ | -------------------------------------------------------------------------------------------------- |
| **1.** Enviar informação            | Fornecedor de Atributos        | Ver Informação de Suporte \*1  | Envio de informação para configuração aplicacional da entidade.                                    |
| **2.** Configurar VPN               | AMA e Fornecedor de Atributos  |                                | Configuração de VPN para comunicação entre Fornecedor e iAP.                                       |
| **3.** Configuração Aplicacional    | AMA                            | Ver Informação de Suporte \*2  | Configuração aplicacional da entidade, e envio dos ficheiros definidos no ponto \*2 ao Fornecedor. |
| **4.** Testar                       | Fornecedor de Atributos        |                                | Desenvolvimento e configuração de atributos de testes pedidos pela AMA.                            |
| **5.** Validar desenvolvimento      | AMA                            |                                | Validação do desenvolvimento.                                                                      |

## Ambiente de Produção 

| Passo                                                       | Entidade Responsável           | Documentos de Suporte                                                                                                               |
| ----------------------------------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| **1.** Relatório de cumprimento de Guidelines               | Fornecedor de Atributos        | Produção de relatório assinado com evidências de cumprimento de _Guidelines_ de Integração do SCAP (Ver Informação de Suporte \*1). |
| **2.** Enviar Informação                                    | Fornecedor de Atributos        | Envio de informação para configuração aplicacional da entidade.                                                                     |
| **3.** Configurar VPN                                       | AMA e Fornecedor de Atributos  | Configuração de VPN para comunicação entre Fornecedor e iAP.                                                                        |
| **4.** Configuração Aplicacional                            | AMA                            | Configuração aplicacional da entidade, e envio dos ficheiros definidos no ponto \*3 ao fornecedor (Ver Informação de Suporte \*3).  |
| **5.** Adquirir certificado                                 | Fornecedor de Atributos        | Aquisição de certificado qualificado de selo eletrónico com base no CSR gerado no passo anterior, e envio do certificado adquirido. |
| **6.** Atualizar Configuração Aplicacional com Certificado  | AMA                            | Atualização da configuração aplicacional da entidade, com o certificado adquirido pelo fornecedor.                                  |
| **7.** Testar                                               | Fornecedor de Atributos        | Configuração de atributos de testes pedidos pela AMA.                                                                               |
| **8.** Validar desenvolvimento                              | AMA                            | Validação do desenvolvimento.                                                                                                       |

Para a configuração em ambiente de produção os Fornecedores de Atributos têm que efetuar a aquisição de um Certificado Qualificado Selo Eletrónico com o _Certificate Signing Request_ (CSR) emitido aquando da criação da conta desse fornecedor no SCAP. Para além desse CSR, **é também disponibilizado um ficheiro com a password encriptada da conta do Fornecedor de Atributos e uma** _secret key_ que será utilizada na validação das operações. 

## Informação de suporte

| Pontos    | Informação de suporte                | Informação de suporte                                                      |
| --------- | ------------------------------------ | -------------------------------------------------------------------------- |
| \*1       | Nome completo da entidade            | —                                                                          |
| \*1       | NIPC/NIF                             | —                                                                          |
| \*1       | CAE                                  | Código da Classificação Portuguesa de Atividades Económicas, se aplicável  |
| \*1       | Contacto telefónico                  | —                                                                          |
| \*1       | Email                                | —                                                                          |
| \*1       | CommonName                           | Ficará associado ao certificado - e.g. iniciais da entidade                |
| \*1       | Localidade                           | Ficará associada ao certificado                                            |
| \*2 e \*3 | SCAP\_\<Fornecedor>\_UriId           | Contém identificador da entidade perante o SCAP                            |
| \*2 e \*3 | SCAP\_\<Fornecedor>\_TotpSecreyKey   | Contém secretKey para geração de TOTPs                                     |
| \*2 e \*3 | SCAP\_\<Fornecedor>\_InfoFile        | Contém informação da conta do Fornecedor de Atributos                      |
| \*3       | SCAP\_\<Fornecedor>\_CSR             | Contém CSR para pedir emissão de certificado                               |
