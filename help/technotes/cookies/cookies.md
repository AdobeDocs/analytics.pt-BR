---
title: Adobe Analytics e cookies do navegador
description: Saiba como as medidas de prevenção de rastreamento afetam cookies de terceiros e primários definidos pelo Adobe Analytics.
source-git-commit: b2f606e74aa0d2ab0f01ab7cbfc795bfd7cda461
workflow-type: tm+mt
source-wordcount: '1985'
ht-degree: 7%

---


# Adobe Analytics e cookies do navegador

Este documento explica como as principais medidas de prevenção de rastreamento de navegadores afetam os cookies de terceiros e primários definidos pelo Adobe Analytics. Ele inclui informações sobre o programa Apple Tracking Prevention (ITP), bem como limitações do Chrome em cookies de terceiros por meio do atributo SameSite.

## Como os navegadores limitaram o uso de cookies?

>[!NOTE]
>[O Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en#cda) e o [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#comparing-cja-to-traditional-adobe-analytics) podem unir cookies usando uma ID de pessoa, como uma ID de logon com hash, se disponível.

### Limitações de cookies de terceiros

Os cookies usados em um contexto de terceiros estão sendo amplamente descontinuados. O Firefox e o Safari começaram a bloquear cookies de terceiros por padrão a partir de 2019 e 2020, respectivamente. O Chrome anunciou planos para parar de suportar cookies de terceiros em 2022. Ao fazer isso, os cookies de terceiros ficam inutilizáveis.

Além disso, no momento, o Chrome permite que os cookies funcionem em um contexto de terceiros se tiverem o atributo &quot;SameSite&quot; definido como Nenhum e se forem rotulados como seguros, o que significa que só podem ser usados em HTTPS. Mais informações estão disponíveis na seção &quot;[O que é o atributo de cookie SameSite e como ele afeta o Analytics?](#samesite-effect)&quot;

#### Quais cookies de terceiros do Adobe são afetados?

O serviço de ID de visitante usa o cookie &quot;[demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)&quot; para fornecer um identificador persistente para visitantes em diferentes domínios de clientes. O serviço herdado da Analytics ID, o cookie &quot;s_vi&quot;, é definido como um cookie de terceiros para implementações que não usam um domínio de coleta CNAME personalizado.

Em navegadores onde cookies de terceiros são bloqueados, o rastreamento entre domínios não está disponível.

### Limitações de cookie primário {#limitations-first-party-cookies}

Cookies próprios são permitidos em todos os principais navegadores. No entanto, a Apple limita a duração de cookies primários definidos pelo Adobe por meio de seu Programa de rastreamento inteligente (ITP). Isso afeta o Safari, bem como todos os navegadores no iOS e iPadOS.

Os cookies próprios do Adobe são limitados a 7 dias de expiração, para click-throughs que a Apple determina que vêm de rastreadores, 24 horas. Com um prazo de 7 dias, se um usuário visitar seu site e retornar dentro de sete dias, a data de expiração do cookie será estendida por mais sete dias. No entanto, se um usuário visitar seu site e retornar em oito dias, ele será tratado como um novo usuário na segunda visita.

Atualmente, as políticas de ITP se aplicam a todos os cookies primários definidos pelo Adobe, independentemente de você estar usando o serviço de ID de visitante ou a ID do Analytics herdada (cookie &quot;s_vi&quot;). Em um ponto, essas políticas foram aplicadas apenas aos cookies definidos pelo cliente e não aos cookies definidos pelo lado do servidor por meio de uma implementação CNAME. No entanto, em novembro de 2020, a ITP foi atualizada para se aplicar também às implementações CNAME.

#### Linha do tempo de grandes alterações na política ITP {#ITP-timeline}

* Fevereiro de 2019 com [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Os cookies do lado do cliente foram limitados a um prazo de sete dias
* Abril de 2019 com [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Os cookies do lado do cliente eram limitados a 24 horas para cliques de anúncio quando o domínio de referência era a) envolvido no rastreamento entre sites e b) o URL final continha uma string de consulta e/ou um identificador de fragmento.
* Novembro de 2020 com [CNAME Cloaking e Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): As limitações de ITP foram estendidas para implementações CNAME.

As políticas da PTI estão frequentemente a evoluir. Para obter as políticas mais recentes, consulte [Rastreamento de prevenção da Apple no Webkit](https://webkit.org/tracking-prevention).

#### Quais cookies próprios do Adobe são afetados?

Todos os cookies próprios definidos pelo Adobe e as bibliotecas JavaScript relacionadas são afetados pelas políticas da ITP:

* [Cookies &quot;AMCV&quot; ](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) definidos pela biblioteca do serviço de ID de visitante da Adobe Experience Cloud (ECID)
* O cookie herdado [&quot;s_vi&quot; do Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) quando configurado com a coleta de dados primários usando um CNAME
* O cookie herdado [&quot;s_fid&quot; do Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html), que é o cookie de fallback usado quando &quot;s_vi&quot; não pode ser definido

#### Qual é o impacto da ITP no Safari para o Analytics?

O impacto das limitações da ITP pode variar significativamente, dependendo do comportamento dos usuários. Somente os visitantes que usam um navegador impactado pela ITP (por exemplo, o Safari) e retornam após uma ausência de sete dias são afetados. Se os visitantes não usarem um navegador ITP ou retornarem dentro de sete dias, eles não serão afetados. É importante revisar seus próprios dados no Analytics para entender a extensão do impacto dessa limitação. Para obter dicas sobre como medir o impacto em seus sites, consulte &quot;[Como posso determinar se as alterações no Safari afetam meu negócio?](#measure-itp-effect)&quot;

Se essas limitações afetarem seus dados, você verá:

1. Aumento das contagens de visitantes como visitantes recorrentes são tratados como novos visitantes porque seus cookies expiraram. Todas as métricas baseadas na métrica Visitante (como Vendas por visitante) também são afetadas.
2. Alterações na atribuição. A atribuição depende de vincular eventos de conversão às atividades anteriores pelo mesmo visitante. Quando um cookie expira, os eventos subsequentes são associados a um novo visitante. As atividades do novo visitante não podem ser vinculadas às atividades do visitante anterior.

>[!NOTE]
>
>Atualmente, as tecnologias ITP não se aplicam a navegadores incorporados em aplicativos móveis.

## Qual é a diferença entre cookies de terceiros e cookies primários?

### Cookies de terceiros

Os cookies de terceiros não são criados pelos sites que os usuários visitam.

Embora os navegadores tratem todos os cookies de terceiros da mesma forma e os armazenem, os cookies de terceiros podem se comportar de maneiras diferentes. Com a implementação de cookies de terceiros do Analytics, os navegadores armazenam a ID Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) como um cookie de terceiros, mas o cliente faz chamadas somente para o Adobe e não para domínios desconhecidos ou suspeitos de terceiros. Esse cookie fornece identificadores persistentes entre domínios e permite conteúdo protegido (HTTPS). Para obter mais informações, consulte [Cookies e o Serviço de identidade da Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

Nas implementações do Analytics, os cookies de terceiros são usados para rastreamento entre domínios e para casos de uso de anúncios, incluindo anúncios de redirecionamento. Cookies de terceiros permitem identificar visitantes conforme eles visitam domínios diferentes de sua propriedade ou como são exibidos como anúncios em sites que você não possui.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookies próprios

Os cookies próprios são específicos do domínio e são criados por sites do cliente e armazenados em navegadores do cliente quando os usuários visitam os sites. Todos os navegadores geralmente aceitam cookies primários, embora o [Safari limite a expiração de alguns tipos de cookies primários](#limitations-first-party-cookies).

Nas implementações do Analytics, os cookies primários são usados para identificar usuários quando eles estão em seu site e, portanto, oferecem suporte a todas as análises da atividade do usuário. Você não precisa de cookies de terceiros para entender a atividade no site.

Para obter mais informações, consulte [Sobre cookies primários](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

![Comparação de cookies](/help/technotes/assets/cookies2.png)

## O que é o atributo de cookie SameSite e como ele afeta os cookies do Analytics? {#samesite-effect}

Com o lançamento do navegador Chrome 80 em fevereiro de 2020 — e versões sucessivas de navegadores Firefox e Edge — o atributo de cookie SameSite impõe a especificação de três valores diferentes que determinam se os cookies podem ser usados em um contexto de terceiros:

* `None`: essa configuração permite o acesso entre sites e permite que os cookies sejam transmitidos em um contexto de terceiros. Para especificar esse atributo, você também deve especificar `Secure` e todas as solicitações do navegador devem seguir HTTPS. Por exemplo, ao definir o cookie, você emparelha os valores do atributo da seguinte maneira: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Se não forem rotulados corretamente, os cookies não poderão ser usados nos navegadores mais recentes e serão rejeitados.

* `Lax`: Permite que solicitações entre sites sejam enviadas com cookies do mesmo site somente para navegação de nível superior com métodos HTTP  *seguros*  (somente leitura, como  `GET`).

* `Strict`: o cookie do mesmo site não é enviado para solicitações de terceiros. O cookie só é enviado se o site do cookie corresponder ao site na barra de URL.

O comportamento padrão nessas versões do navegador é tratar cookies que não têm um atributo `SameSite` especificado igual ao `SameSite=Lax`.

### Como o Analytics gerencia atributos de cookies do SameSite?

Para clientes que usam o Serviço de ID de visitante, os cookies têm as propriedades `SameSite=None` e `secure` definidas por padrão, o que permite que esses cookies sejam compatíveis com casos de uso de terceiros.

Para clientes que usam identificadores herdados do Analytics (&quot;s_vi&quot; e cookies &quot;s_fid&quot;), os cookies também são definidos para permitir casos de uso de terceiros com domínios de coleção padrão: adobedc.net, 2o7.net e omtrdc.net. Para clientes que usam uma implementação CNAME, o Analytics define `SameSite=Lax`.

>[!NOTE]
>
>Se você tiver vários domínios e usar o mesmo CNAME para a coleta de dados em todos, o cookie será tratado como um cookie de terceiros nesses outros domínios. Se estiver usando os identificadores herdados do Analytics, convém atualizar sua configuração para `SameSite=None` para que esses cookies possam ser compartilhados entre seus sites. Consulte &quot;[Alterar o valor do SameSite ao usar um CNAME para vários domínios](#samesite-one-cname)&quot; na próxima seção para obter mais informações.

Em navegadores que o Google identificou como cookies que estão manipulando incorretamente quando `SameSite` está definido como `None`, `SameSite` fica indefinido.

A tabela a seguir resume os atributos SameSite dos cookies do Analytics:

![Tabela de cookies](/help/technotes/assets/cookies1.png)

### Como meu site pode atender aos requisitos para o atributo SameSite?

#### Servir todas as páginas do site com HTTPS

Confirme se a configuração do JavaScript usa HTTPS para todas as chamadas a serviços do Adobe.

Se o site usa o serviço de ID de visitante do Experience Cloud, o serviço redireciona chamadas HTTP de terceiros para o terminal HTTPS, o que pode aumentar a latência, mas significa que você não precisa alterar a configuração.

#### Altere o valor SameSite quando usar um CNAME para vários domínios {#samesite-one-cname}

>[!NOTE]
>
>As informações a seguir se referem apenas a sites que não usam o serviço de ID de visitante do Experience Cloud.

Se você tiver uma implementação CNAME definida no mesmo domínio do site, o cookie será criado em um contexto primário e você não precisará fazer alterações.

No entanto, se você tiver vários domínios e usar o mesmo CNAME para a coleta de dados em todos, o cookie será tratado como um cookie de terceiros nesses outros domínios. Com o Chrome 80 e superior, ele não é mais visível nesses outros domínios. Para tornar o comportamento mais parecido em todos os navegadores, o Analytics definiu explicitamente o valor `SameSite` desse cookie como `Lax`. Se você usar esse cookie em um contexto de terceiros amigável, deverá ter o cookie definido com o valor `SameSite=None` , o que também significa que sempre deverá usar HTTPS. Se ainda não tiver feito isso, entre em contato com o Atendimento ao cliente do Adobe para alterar o valor do SameSite para seus CNAMEs protegidos.

## Como posso determinar se as alterações no Safari afetam meus negócios? {#measure-itp-effect}

A Adobe recomenda que os clientes avaliem o impacto em sua própria empresa antes de alterar a coleta de dados. Você pode usar o Analysis Workspace para medir o impacto da prevenção de rastreamento de ITP em sua empresa individual:

* Meça a porcentagem do seu tráfego de navegadores governados pela ITP:

   1. Crie um segmento para ver quantos visitantes estão usando uma plataforma ITP.

      >[!NOTE]
      >
      >Os navegadores específicos afetados pela ITP dependem se você estava usando uma implementação CNAME. Consulte &quot;[Linha do tempo de alterações importantes na política ITP](#ITP-timeline)&quot; para obter mais detalhes.

      ![Segmento para visitantes da ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Aplique o segmento ao número de visitas para entender o uso relativo do Safari na base do usuário. Isso permite criar uma tabela como a seguinte:

      ![Porcentagem de visitas por visitantes da ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Meça a porcentagem de visitantes que usam navegadores que não são Safari e não retornam dentro de sete dias. Se os visitantes que não são do Safari retornarem repetidamente em sete dias, o tráfego do Safari pode não ser significativamente afetado.

   1. Crie um segmento como o seguinte para tráfego que não seja do Safari.

      ![Segmento para visitantes que retornam após sete dias](/help/technotes/assets/visits-after-seven-days.png)

   2. Aplique o segmento ao número de visitas para entender o uso relativo do Safari na base do usuário. Isso permite criar uma tabela como a seguinte:

      ![Porcentagem de visitantes que retornam após sete dias](/help/technotes/assets/percent-visits-after-seven-days.png)

### Maneiras de ajustar seus dados durante os relatórios

Se sua empresa for afetada pela prevenção de rastreamento de ITP, considere as seguintes medidas para ajustar os dados durante o relatório.

* Crie um segmento para filtrar usuários de ITP.

   ![Segmento para visitantes que não são da ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Crie uma métrica calculada para ajustar a inflação de visitante conhecida.

   ![Métrica calculada a ser ajustada para inflação de visitante](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Opções para atenuar o efeito das limitações de cookies do navegador](cookieless.md)
>[O impacto da nova estrutura de transparência de rastreamento de aplicativos da Apple no Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
