---
description: Cookies do Analytics
title: Perguntas frequentes sobre cookies do navegador e do Analytics
uuid: null
translation-type: tm+mt
source-git-commit: 38de617d3c77195d2308e14783962f6690b4b3fc

---


# Perguntas frequentes sobre cookies de navegadores e análises

Para oferecer suporte à identificação persistente do usuário nas propriedades e soluções, o Adobe Analytics responde às alterações em como os navegadores lidam com cookies. As Perguntas frequentes a seguir apresentam informações sobre como a identificação persistente do visitante é preservada com as alterações no cookie do navegador.

## Como os navegadores estão alterando a maneira como lidam com cookies?

Em geral, a maioria dos navegadores está se tornando mais restritiva na forma como eles possuem cookies de terceiros. Isso pode afetar o rastreamento se o cookie for excluído ou rejeitado pelo navegador. O navegador Safari também está definindo algumas limitações para alguns cookies primários.

A lista a seguir mostra algumas alterações recentes de acordo com os navegadores:

* Chrome: A partir do Chrome 80, o `SameSite` atributo é tratado de forma diferente para gerenciar cookies de terceiros ou solicitações entre sites. Em última análise, os desenvolvedores do Chrome estão buscando maneiras de [descontinuar completamente os cookies](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) de terceiros.

* Firefox e Edge: Os anúncios de produtos afirmam que as versões sucessivas de seus navegadores devem seguir as mesmas alterações que as feitas no Chrome 80.

* Safari: With [Safari 12.1](https://webkit.org/blog/category/privacy/), first party persistent cookies set through the document.cookie API, often known as “client-side” cookies, have their expiration capped at seven days.

## Qual é a diferença entre cookies de terceiros e cookies primários?

### Cookies próprios

Os cookies primários são criados por sites do cliente (específicos do domínio) e armazenados em navegadores do cliente quando os usuários visitam os sites do cliente. Todos os navegadores geralmente aceitam cookies primários. Em uma implementação de cookie primário do Analytics, o cookie de ID de visitante é criado em um nó da Adobe quando o nome do host é reconciliado com o domínio usando um [CNAME](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html). O cookie é então aceito pelo navegador em um contexto próprio. Para obter mais informações, consulte [Sobre cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)primários.

### Cookies de terceiros

Cookies de terceiros não são criados por sites visitados pelos usuários. Embora os navegadores atualmente tratem todos os cookies de terceiros da mesma forma e os armazenem de acordo, os cookies de terceiros podem se comportar de maneiras diferentes e importantes. Com a implementação de cookies de terceiros do Analytics, o cliente faz chamadas somente para a Adobe e não para domínios desconhecidos ou suspeitos de terceiros. Esse é o método atual para implementar o Analytics para rastreamento seguro (HTTPS) e confiável com identificadores persistentes. Esse método é implementado pela configuração do arquivo AppMeasurement.js. Para obter mais informações, consulte [Cookies e o Serviço](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html)de identificação da plataforma Experience.

![Diferenças de cookie](assets/cookieimage.PNG)

## Como os navegadores atualmente armazenam e gerenciam os cookies do Analytics?

Dependendo da implementação, os cookies do Analytics são armazenados da seguinte forma:

### Implementações de cookies de terceiros

No momento, os navegadores armazenam a Adobe [demdex.net](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/demdex-calls.html) ID como um cookie de terceiros. Este cookie fornece identificadores persistentes entre domínios e permite conteúdo protegido (https).

### Implementações de cookie primário

Ao configurar um CNAME, seu usuário pode receber cookies da Adobe em um contexto de cookie primário para seus navegadores. Essa pode ser uma opção viável se uma implementação de cookie de terceiros não for ideal para seus usuários.

## O que é o atributo de cookie SameSite e como ele afeta o Analytics?

Com o lançamento do navegador Chrome 80 — e versões sucessivas do Firefox e navegadores Edge — o atributo de cookie SameSite impõe a especificação de três valores diferentes para controlar o comportamento da solicitação entre sites, da seguinte forma:

* `None`: Essa configuração permite o acesso entre sites e permite que os cookies sejam transmitidos em um contexto de terceiros. Para especificar esse atributo, você também deve especificar `Secure` e todas as solicitações do navegador devem seguir HTTPS. Por exemplo, ao definir o cookie, você emparelha os valores do atributo da seguinte maneira: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Se não forem rotulados corretamente, os cookies não poderão ser usados nos navegadores mais recentes e serão rejeitados.

* `Lax`: Permite que solicitações entre sites sejam enviadas com cookies do mesmo site somente para navegações de nível superior com métodos HTTP *seguros* (somente leitura, como `GET`).

* `Strict`: O cookie do mesmo site não é enviado para solicitações de terceiros. O cookie só é enviado se o site do cookie corresponder ao site na barra de URL.

O comportamento padrão nessas versões do navegador é tratar cookies que não têm um `SameSite` atributo especificado igual ao `SameSite=Lax`.

## Como o Adobe Analytics está respondendo a essas alterações?

Todas as atualizações de cookies da Adobe são feitas por meio de servidores da Adobe e a Adobe atualizou seus servidores de borda para definir os atributos de cookie apropriados. A Adobe lançou atualizações do lado do servidor para definir seus cookies de terceiros com os atributos apropriados. Não são necessárias atualizações de JavaScript para seus sites.

Essa atualização pelos servidores de borda da Adobe ocorrerá automaticamente quando os usuários visitarem qualquer site onde o cookie for usado. Para a maioria dos produtos da Adobe, os cookies terão os sinalizadores apropriados, à medida que o Chrome 80 for lançado. A exceção são as implementações do Adobe Analytics que usam a coleta de dados de terceiros e não usam o Serviço de identidade da Experience Cloud (ECID). Esses clientes podem experimentar um pequeno aumento temporário em novos visitantes que, de outra forma, teriam sido marcados como visitantes recorrentes.

Para navegadores que o Google identificou como cookies que estão sendo manipulados incorretamente quando `SameSite` está definido como `None`, `SameSite` serão deixados indefinidos.

A tabela a seguir resume os cookies do Analytics:


![Tabela de cookies do Analytics](assets/cookie_table.png)


## Qual é a melhor maneira de preparar meu site para alterações no Chrome, Firefox e Edge?

Os clientes do Analytics devem confirmar que sua configuração JavaScript está usando HTTPS para suas chamadas para os serviços da Adobe. A ECID redireciona chamadas HTTP de terceiros para seu terminal HTTPS, o que pode aumentar a latência, mas significa que você não é obrigado a alterar sua configuração.

A Adobe sugere que você se certifique de que todas as páginas do seu site sejam fornecidas com HTTPS.

### Um CNAME para vários domínios

Se você tiver uma implementação CNAME definida no mesmo domínio do seu site, este será um contexto de cookie primário e você não precisa fazer alterações.

No entanto, se você possuir vários domínios e usar o mesmo CNAME para a coleta de dados em todos os domínios, ele será tratado como um cookie de terceiros nesses outros domínios. Com o Chrome 80, ele não estará mais visível nesses outros domínios. Para tornar o comportamento mais parecido em todos os navegadores, o Analytics está definindo explicitamente o `SameSite` valor desse cookie como `Lax`. Se você usar esse cookie em um contexto amigável de terceiros, precisará ter o cookie definido com o `SameSite=None` valor, o que também significa que você sempre deve usar HTTPS. Entre em contato com o Atendimento ao cliente da Adobe para alterar o valor de SameSite para seus CNAMEs protegidos. Observe que essa ação NÃO é necessária para clientes do Analytics que usam a ECID.

## Qual é o impacto das alterações do Safari (ITP 2.1) no Analytics?

Apesar das alterações no Safari 12.1, os conjuntos de dados dos cookies da Adobe Experience Cloud ainda estão sendo coletados. Embora os cookies sejam limitados a sete dias, os visitantes que retornam à sua propriedade dentro desse período renovam o cookie e evitam que ele expire por mais sete dias. As janelas de pesquisa e as contagens de visitantes recorrentes podem ser reduzidas para o tráfego Safari até que uma atualização da Adobe seja disponibilizada.

Devido à janela de expiração reduzida de sete dias, os clientes podem ver um aumento de visitantes únicos. A contagem de visitas e de exibições de página não deve ser afetada. Se você tiver uma propriedade com tráfego sazonal, como serviços de impostos ou varejo de feriados, poderá observar um impacto maior, pois esse visitante não será conectado entre as estações.

Se você usar um CNAME, o serviço de ID de visitante salvará o ECID em um cookie primário do lado do servidor. Isso permite que o cookie persista por sua duração total.

**Observação: O ITP 2.1 não se aplica a navegadores incorporados em aplicativos móveis.**

### Cookies primários afetados

Os cookies originais criados por meio `document.cookie` são afetados. Se você estiver configurando algum desses cookies por meio da resposta HTTP (servidor) ou usando a certificação CNAME, você não será afetado pelas alterações no ITP 2.1. Os seguintes cookies primários e bibliotecas relacionadas do Adobe JavaScript são afetados:

* Cookies AMCV definidos pela biblioteca do serviço ECID (Experience Cloud ID)
* Cookie de fallback herdado do Analytics `s_fid`

O `s_vi` cookie herdado do Analytics como um cookie de terceiros, incluindo destinos de coleta de 2o7.net ou omtrdc.net, continua sendo bloqueado com base em versões anteriores do ITP.

Resumindo:

* Se você tiver um CNAME e usar o serviço de ID de visitante — sua implementação não será afetada.

* Se você usar um CNAME primário no contexto primário e não usar o serviço de ID de visitante — sua implementação não será afetada.

* Se você usar um domínio de cookie primário no contexto de terceiros, ou com os nomes de domínio padrão de terceiros (por exemplo, 2o7.net, omtrdc.net etc), o Safari continuará bloqueando-o como ele o fez.

* Se você usar uma ID de visitante personalizada — Isso dependerá de como a sua ID de visitante será armazenada. Se você armazenar sua ID em um cookie próprio &quot;do lado do cliente&quot;, você estará sujeito à expiração de sete dias. Se você usar outros meios para armazenar sua ID personalizada, será necessário avaliar se você é afetado.

### Conjuntos de dados menos afetados

Os conjuntos de dados com visitantes ativos que retornam com frequência são os menos afetados pelas alterações. Se o conteúdo do site for tal que os clientes retornem diariamente ou pelo menos algumas vezes por semana, os cookies desses usuários ativos serão renovados antes da expiração. Redes sociais, notícias e outros sites de mídia têm maior probabilidade de ter grandes comunidades de usuários que retornam com frequência.

Os clientes que estiverem usando `s_vi` como sua ID de visitante principal e estiverem configurados com a coleta de dados primária usando um CNAME não serão afetados pelo ITP 2.1. Observe que nos casos em que `s_vi` não é possível definir, o cookie de fallback `s_fid` pode ser usado e terá uma expiração de sete dias.

Além disso, os conjuntos de dados que usam o serviço de ID de visitante e têm um domínio próprio são menos afetados.

## As mudanças no Safari afetarão meus negócios?

A Adobe recomenda que os clientes avaliem o impacto em sua própria empresa antes de fazer qualquer alteração na coleta de dados. Isso pode ser feito por métodos fornecidos abaixo nesta seção.

Para medir o impacto nos relatórios e testes, é importante saber que tipo de visitante e rastreamento de cookie você implementou e quanto tráfego tem de usuários com o Safari. Considere o seguinte para medir o impacto em sua empresa individual:

* Verifique quais tipos de cookies estão sendo definidos pelas bibliotecas da Adobe.

* Abra o console do desenvolvedor no navegador Safari mais recente. Se você vir algum dos cookies listados acima definidos em seu domínio primário, você poderá ser afetado por essas alterações.

* Se vir um `s_vi` cookie, mas não um `AMCV` cookie definido no contexto de um CNAME, você está usando um CNAME para identificação de visitantes e seu uso do Analytics não é afetado por essas alterações. Se você vir um `s_vi` cookie e um `AMCV` cookie definidos no contexto de um CNAME, você está usando recentemente ou no momento o período de carência, e algum do seu tráfego do Analytics pode ser afetado.

* Use o Analytics para medir a porcentagem de visitantes que não retornam dentro de sete dias. Se seus visitantes retornarem repetidamente em sete dias, seu tráfego pode não ser significativamente afetado. Para obter instruções sobre como usar o Analytics para descobrir isso, consulte [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

* Meça a porcentagem de tráfego dos navegadores Safari para determinar se qualquer alteração é justificada o suficiente. Para obter instruções sobre como usar o Analytics para descobrir a porcentagem de tráfego do Safari para seus sites, consulte Impacto do ITP 2.1 do [Safari nos clientes](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)da Adobe Experience Cloud e da plataforma Experience.

## Quais navegadores meus visitantes estão usando mais?

Se você estiver interessado em saber mais sobre os navegadores usados pelos seus visitantes, poderá usar a Dimensão [do](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-browsers.html) navegador do Analytics para determinar quais navegadores são mais usados para seus sites. Você também pode usar as Dimensões do Analytics para ver quais navegadores são mais usados de acordo com as regiões geográficas. For more information, see [GeoSegmentation](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

De acordo com o [comunicado](https://gs.statcounter.com/browser-market-share/all), no final de 2019, a quota de mercado mundial para cada navegador era a seguinte:

* Chrome: ~64%
* Safari: ~17%
* Firefox: ~4%
* Borda: ~2%

À medida que a participação muda, você pode consultar essas [estatísticas](https://gs.statcounter.com/browser-market-share/all) para revisar sua estratégia de implementação.

## Como posso trabalhar melhor com as alterações do ITP 2.1 no Safari a curto prazo?

O CNAME da Adobe e o programa de certificado gerenciado estão sendo usados para lidar com alterações de ITP. O programa Adobe Managed Certificate permite implementar um novo certificado próprio para cookies próprios sem custo adicional. Atualmente, a Adobe tem vários serviços CNAME por solução e pretende aproveitar o programa de certificação do Analytics a curto prazo.

Qualquer cliente atual do Analytics com uma configuração CNAME que também esteja usando os Serviços da Experience Cloud ID para identificação de visitantes poderá aproveitar uma atualização futura da biblioteca ECID. Essa alteração permitirá que os servidores de rastreamento certificados CNAME mantenham o ECID e sejam usados como referência para a identificação do visitante. Estão disponíveis mais informações em versões sucessivas da biblioteca ECID.

A Adobe está ciente de que nem todos os clientes da biblioteca ECID usam CNAMES ou Analytics. Todos os clientes ECID receberão uma configuração CNAME para utilizar o mesmo recurso.

Se você não estiver aproveitando um CNAME para sua implementação, poderá iniciar o processo conversando com o Atendimento ao cliente.

## Quais são os planos futuros da Adobe para a identificação persistente de visitantes?

Os novos recursos e implementações incluem:

* Opções de autoatendimento de certificação CNAME em todas as soluções da Adobe

* Métodos flexíveis de coleta de ID de visitante, BYOI (Traga sua própria identidade) e coleta de dados pela primeira API

* Gráficos de identidade da plataforma Adobe Experience

* Abordagem unificada para a coleta de dados da Adobe

A Adobe está comprometida com a personalização mais precisa para consumidores que desejam uma experiência personalizada. A Adobe se esforça para oferecer aos nossos clientes a funcionalidade de identidade on-line que os ajuda a se alinharem às suas opções de privacidade.

## Mais Informações 

Para obter informações, consulte:

* [Adobe Experience Cloud: Atualizações de cookies para o Google Chrome](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Impacto do Safari ITP 2.1 nos clientes da Adobe Experience Cloud e da Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

