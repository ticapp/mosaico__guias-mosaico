# Como está estruturada a plataforma?

A plataforma não possui um front end próprio, existe apenas um widget de integração que a Entidade Aderente pode utilizar. O frontend **é sempre a Aplicação do Cliente/Entidade Aderente** (site/portal/aplicação financeira, etc.), podendo ou não ser este _widget_. O widget pode ser totalmente controlada pela própria API, reforçando a capacidade de integração com os sistemas operacionais da entidade aderente.&#x20;

O produto é “invisível” ao utilizador final, oferecendo um conjunto de operações facilmente integráveis na Aplicação do Cliente/Entidade Aderente. &#x20;

O back office Web do produto possibilita uma gestão operacional dos pagamentos, sem que sejam requeridos ao operador quaisquer conhecimentos técnicos. A monitorização, gestão e controlo de todas as transações é efetuada de uma forma simples e segura. É possível realizar as diversas operações via Web Services.&#x20;

Abaixo o diagrama de alto nível da PPAP, demonstrando na Camada de Negócio os atores e papéis envolvidos, os serviços de negócio e os processos, e na Camada Aplicacional os serviços aplicacionais que realizam os seus processos.&#x20;

<div align="center">

<img src="../../.gitbook/assets/MicrosoftTeams-image (1).png" alt="Arquitetura de alto nível da PPAP">

</div>

{% hint style="info" %}
**Pagamentos Digitais** significa Pagamentos por Referência Multibanco, MB Way, DUC ou PayPal.
{% endhint %}
