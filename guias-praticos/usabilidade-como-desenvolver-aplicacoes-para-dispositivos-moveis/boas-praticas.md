# Boas Práticas

Os cidadãos, individualmente ou no seio das empresas esperam uma boa experiência na utilização de aplicações para dispositivos móveis dos serviços da Administração Pública Portuguesa. A concretização deste objetivo passa por um bom funcionamento das aplicações e dos serviços nelas disponibilizados, independentemente do dispositivo ou navegador pelo qual acedem. As aplicações para dispositivos móveis apresentam-se como forma de simplificar o acesso aos serviços públicos.

Como boa prática devemos considerar os diversos tipos de aplicações para dispositivos móveis que podem ser criadas, avaliando as suas características e quais as vantagens e as desvantagens para a aplicação concreta que pretendemos desenvolver.

De seguida iremos detalhar quais os tipos de aplicações móveis que devem ser analisados à luz dos requisitos de cada aplicação e serviços a disponibilizar ao cidadão ou empresa.

## **Tipos de aplicação**

&#x20;

### **1) Aplicação Web**

As aplicações _web_ (_Web Apps_) são na realidade _websites_ otimizados para dispositivos móveis e que apresentam uma experiência semelhante às aplicações nativas, mas através do navegador de _internet_ (Chrome, Safari, Edge, etc.).

Consideramos duas técnicas principais para o desenvolvimento deste tipo de aplicação:

* Aplicação _Web_ Responsiva: um _site_ que responde às dimensões do navegador em qualquer ponto. Esta resposta às dimensões do navegador é feita de forma fluída e flexível.
* Aplicação _Web_ Adaptativa: um _site_ que se adapta à largura do navegador em pontos específicos. Este tipo de _site_ só foca em pontos específicos de largura e apenas se adapta nesses pontos à mudança de largura.

Tendo em conta estas duas técnicas, a nossa recomendação é a de que a aplicação _web_ seja desenvolvida como uma aplicação _web_ responsiva. Este desenvolvimento deverá seguir ainda a estratégia de [Progressive Enhancement](https://en.wikipedia.org/wiki/Progressive\_enhancement).

&#x20;

### **2) Progressive Enhancement**

O Progressive Enhancement é uma estratégia para o _design web_ que dá enfâse ao conteúdo principal da página. Esta estratégia passa por adicionar progressivamente mais nuances, camadas de apresentação e recursos sobre o conteúdo principal, de acordo com a velocidade e condições de acesso de dados disponível em cada momento. O benefício desta estratégia é permitir que todos os utilizadores possam ter acesso ao conteúdo e à funcionalidade base de uma página da _web_, usando qualquer navegador ou ligação à _internet_, além de fornecer uma versão mais completa da página para aqueles utilizadores que possuam navegadores de _internet_ mais avançados ou que tenham disponível uma maior largura de banda.

Vantagens:

* O utilizador não precisa de instalar a aplicação no dispositivo móvel;
* Os custos de desenvolvimento são mais baixos do que no desenvolvimento de uma aplicação nativa, porque são utilizadas linguagens de programação comuns de desenvolvimento de aplicações _web_;
* É mais fácil disponibilizar as atualizações porque estas poderão ser automaticamente disponibilizadas e não estão dependentes da loja de aplicações.

Desvantagens:

* Não é possível utilizar todas as funcionalidades avançadas e nativas do dispositivo móvel.

&#x20;

### **3) Aplicação Nativa**

Uma aplicação nativa (_App_ Nativa) é definida como uma aplicação cujo código de programação é específico para o dispositivo móvel. São disso exemplo o uso de _Objective C_ para sistema operativo _iOS_ ou o uso de _Java_ para o sistema operativo _Android_.

Vantagens:

* Desempenho rápido e um nível alto de fiabilidade;
* Disponibiliza uma ligação fácil a muitas das funcionalidades nativas do dispositivo, como a câmara, contactos, calendário e outras características como o giroscópio, _gps_, _touch ID_, etc.
* Algumas aplicações podem ser utilizadas sem ligação à _internet_.

Desvantagens:

* O desenvolvimento destas aplicações apresenta custos de desenvolvimento mais elevados, bem como será necessário mais tempo para o seu desenvolvimento, por causa da sua dependência da linguagem específica do sistema operativo do dispositivo.
* O desenvolvimento destas aplicações obriga a duplicar a aplicação noutras linguagens de programação para conseguir apresentar noutros dispositivos baseados em sistemas operativos distintos.

### **4) Aplicação Híbrida**

Uma aplicação híbrida (_App_ Híbrida) é muito semelhante a uma _App_ Nativa, no sentido em que pode ser encontrada e instalada através da loja de aplicações (_App Store_) do fabricante do sistema operativo do dispositivo (por exemplo: _PlayStore_ da _Google_). A diferença entre as aplicações nativas e as aplicações híbridas encontra-se no processo de desenvolvimento.

Vantagens:

* As aplicações híbridas são desenvolvidas utilizando linguagens de programação comuns ao desenvolvimento de aplicações web como _HTML 5_, _CSS_ e _Javascript_.
* São utilizáveis em todos os tipos de dispositivo, e o código precisa de ser escrito apenas uma vez, em que apenas o contexto de execução é nativo ao sistema operativo do dispositivo.
* Os custos e o tempo necessários ao desenvolvimento deste tipo de aplicações são menores do que no caso das aplicações nativas.

Desvantagens:

* Apesar do desempenho deste tipo de aplicações ser semelhante ao das aplicações nativas, no caso das aplicações com necessidades de gráficos de alta qualidade, ocorre uma degradação do desempenho da aplicação.
* Precisam de um _plugin_ nativo (o contexto de execução) para conseguir aceder às funcionalidades nativas do dispositivo como por exemplo o _touch ID_ e a câmara. Se não existir um _plugin_ nativo, será necessário desenvolvê-lo, o que poderá ser uma tarefa mais complexa.
* Todas as aplicações híbridas estão dependentes de _frameworks_ e bibliotecas _open source_, como o [Ionic](https://ionicframework.com/) ou o [Cordova](https://cordova.apache.org/).

&#x20;

### _**5) Progressive Web Applications**_

Algumas tecnologias emergentes permitem evoluir as aplicações _web_ e torná-las em aplicações _web_ progressivas (_progressive web applications_ - PWA). Estas tecnologias disponibilizam funcionalidades que até agora estavam disponíveis apenas para aplicações nativas ou híbridas.

Exemplos de funcionalidades que poderemos tirar partido com o uso de _PWA_:

* Adicionar ícones ao ecrã principal do telemóvel;
* Enviar notificações _push_ ao utilizador;
* Disponibilizar um serviço quando o utilizador está sem ligação à Internet;
* Integrar um serviço com outras partes do telemóvel, como por exemplo a câmara fotográfica.

A utilização de _PWA_s permite que os utilizadores deixem de estar dependentes da instalação de novas versões das aplicações para terem acesso a novas funcionalidades e correção de bugs.

&#x20;



## **Quando optar por aplicações nativas ou híbridas**

Há situações em que uma aplicação nativa ou híbrida é a única solução como por exemplo:

O utilizador necessita de recolher e guardar dados, mas não lhe é possível ter uma ligação de _internet_ que seja estável, sendo necessário o funcionamento em modo _offline_, e uma _PWA_ não é opção.

O serviço só funciona se tiver uma iteração constante no dispositivo do utilizador, como por exemplo, em aplicações de _fitness_ e saúde.

Outra situação em que poderá fazer sentido utilizar uma aplicação nativa, será quando a mesma só necessita de funcionar num dispositivo. Exemplos práticos:

Todos os utilizadores utilizam o mesmo dispositivo padrão departamental;

Necessidade de usar uma capacidade específica do dispositivo.

Salvo exceções do tipo das acima referidas, é bastante difícil justificar a opção de aplicações híbridas/nativas no desenvolvimento de uma aplicação, para disponibilização de um serviço, para o cidadão comum. Ainda assim, será necessário seguir boas práticas gerais e boas práticas de serviço.

**Se está limitado por funcionalidades do dispositivo**

Se a sua aplicação nativa requer uma funcionalidade que se encontra disponível num pequeno grupo de dispositivos, então terá que apresentar a aplicação como progressive enhancement.

Nesta situação, apresentamos a aplicação apenas aos utilizadores que possuem esses dispositivos, uma vez que é a forma mais fácil de completarem a sua tarefa. Mesmo assim, será necessário, apresentar aos restantes utilizadores que não possuem estes dispositivos, uma forma simples de conseguirem completar as suas tarefas.

## **Quando evitar aplicações nativas ou híbridas**

Como referido anteriormente, as aplicações nativas ou híbridas não são a melhor forma de disponibilizar serviços. É mais simples e menos dispendioso disponibilizar um _website_ responsivo. Um sítio responsivo, desenvolvido utilizando boas práticas _web_, funciona em todos os navegadores e dispositivos móveis.

Ao construir uma aplicação nativa ou híbrida, será necessário suportar todos os sistemas operativos para os dispositivos móveis mais utilizados nas localizações alvo da aplicação. Isto pode tornar-se muito dispendioso quer na construção quer na manutenção das aplicações.

Tipicamente, existem outras abordagens possíveis para ultrapassar algumas das limitações das aplicações _web_, do que desenvolver uma aplicação nativa ou híbrida, como as já referidas aplicações _web_ progressivas.

Deve considerar sempre as alternativas possíveis antes de decidir desenvolver aplicações nativas ou híbridas – que são uma opção apenas quando não existe outra forma de ir ao encontro das necessidades do utilizador.

## **Acessibilidade**

De acordo com o [DL nº 83/2018](https://dre.pt/dre/detalhe/decreto-lei/83-2018-116734769), deve considerar-se acessibilidade como: “os princípios e técnicas a observar na conceção, construção, manutenção e atualização de sítios web e aplicações móveis de forma a tornar os seus conteúdos mais acessíveis aos utilizadores, em especial a pessoas com deficiência”.

Neste sentido, as aplicações para dispositivos móveis a disponibilizar no âmbito dos serviços da Administração Pública Portuguesa deverão cumprir as normas enunciadas no decreto lei acima referido e deverão ainda usar todas as ferramentas e guias de orientação disponibilizados no site [www.acessibilidade.gov.pt](http://www.acessibilidade.gov.pt/).

## **Partilha de Dados e API**

Uma das boas práticas que os serviços públicos devem seguir, é disponibilizar o acesso aos dados e às _Application Programming Interfaces (API)_ dos seus serviços a outras entidades, para que estas possam utilizar os dados e os serviços para construir serviços complementares ou adicionais aos serviços da entidade.

Esta abordagem também pode funcionar se identificar uma necessidade que, por constrangimentos diversos, não possa ser respondida pela sua entidade. Ao disponibilizar o acesso aos dados, pode estar a estimular o mercado a criar um serviço que possa responder a essa necessidade.

Um exemplo desta prática é o _Transport of London_ que abriu o acesso das suas _API_s, de forma a que algumas empresas privadas tivessem a possibilidade de desenvolver aplicações relacionadas com a rede de transportes públicos em Londres, como é o caso da aplicação [_CityMapper_](https://citymapper.com/)_._

