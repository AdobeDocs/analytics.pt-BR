---
title: Mapeamento de variável do Analytics na Adobe Experience Edge
description: Visualize quais campos XDM a borda mapeia automaticamente para variáveis do Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: e42c125da0c48ff01267e3a18aaec8374652809e
workflow-type: tm+mt
source-wordcount: '1386'
ht-degree: 99%

---

# Mapeamento de variável do Analytics na Adobe Experience Edge

A tabela a seguir mostra as variáveis que a Rede de borda da Adobe Experience Platform mapeia automaticamente para o Adobe Analytics. Se você usar esses Caminhos de campo XDM, nenhuma configuração adicional será necessária para enviar dados para o Adobe Analytics.

| Caminho do campo XDM | Dimensão e descrição do Analytics |
| --- | --- |
| `application.isClose` | Ajuda a definir a métrica móvel [Falhas](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=pt-BR#metrics). |
| `application.isInstall` | Ajuda a determinar quando aumentar a métrica móvel [Primeiras inicializações](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Ajuda a determinar quando aumentar a métrica móvel [Primeiras inicializações](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Determina se um evento de encerramento é uma falha ou não. Os valores válidos incluem `close` (Uma sessão de ciclo de vida termina e um evento de pausa foi recebido para a sessão anterior) e `unknown` (Uma sessão do ciclo de vida termina sem um evento de pausa). Ajuda a definir a métrica [Falhas](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isInstall` | A métrica móvel [Instalações](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | A métrica móvel [Inicializações](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Ajuda a definir a dimensão móvel [ID do aplicativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=pt-BR#dimensions). |
| `application.isUpgrade` | A métrica móvel [Atualizações](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Ajuda a definir a dimensão móvel [ID do aplicativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | A métrica móvel [Duração da sessão anterior](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) para a métrica [Check-outs](../../components/metrics/checkouts.md). |
| `commerce.checkouts.value` | Aumenta a métrica [Check-outs](../../components/metrics/checkouts.md) pela quantidade desejada. |
| `commerce.order.currencyCode` | Define a variável da configuração [currencyCode](../vars/config-vars/currencycode.md). |
| `commerce.order.purchaseID` | Define a variável da página [purchaseID](../vars/page-vars/purchaseid.md). |
| `commerce.order.transactionID` | Define a variável [transactionID](../vars/page-vars/transactionid.md) variável de página. |
| `commerce.productListAdds.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Adições ao carrinho](../../components/metrics/cart-additions.md). |
| `commerce.productListAdds.value` | Incrementa a métrica [Adições ao carrinho](../../components/metrics/cart-additions.md). |
| `commerce.productListOpens.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Carrinhos](../../components/metrics/carts.md). |
| `commerce.productListOpens.value` | Incrementa a métrica [Carrinhos](../../components/metrics/carts.md). |
| `commerce.productListRemovals.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Remoções do carrinho](../../components/metrics/cart-removals.md). |
| `commerce.productListRemovals.value` | Incrementa a métrica [Remoções do carrinho](../../components/metrics/cart-removals.md). |
| `commerce.productListViews.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Visualizações do carrinho](../../components/metrics/cart-views.md). |
| `commerce.productListViews.value` | Incrementa a métrica [Visualizações do carrinho](../../components/metrics/cart-views.md). |
| `commerce.productViews.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Visualizações do produto](../../components/metrics/product-views.md). |
| `commerce.productViews.value` | Incrementa a métrica [Visualizações de produto](../../components/metrics/product-views.md). |
| `commerce.purchases.value` | Incrementa a métrica [Pedidos](../../components/metrics/orders.md). |
| `device.model` | A dimensão móvel [Nome do dispositivo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.colorDepth` | Ajuda a definir a dimensão [Intensidade de cor](../../components/dimensions/color-depth.md). |
| `device.screenHeight` | Ajuda a definir a dimensão [Resolução do monitor.](../../components/dimensions/monitor-resolution.md) |
| `device.screenWidth` | Ajuda a definir a dimensão [Resolução do monitor.](../../components/dimensions/monitor-resolution.md) |
| `device.type` | O tipo de dispositivo móvel. |
| `environment.browserDetails.acceptLanguage` | Ajuda a definir a dimensão [Idioma](../../components/dimensions/language.md). |
| `environment.browserDetails.cookiesEnabled` | Define a dimensão [Suporte a cookies](../../components/dimensions/cookie-support.md). Os valores válidos incluem `Y` (o navegador aceita cookies) e `N` (o navegador rejeita cookies). |
| `environment.browserDetails.javaEnabled` | Define a dimensão [Java ativado](../../components/dimensions/java-enabled.md). Os valores válidos incluem `Y` (O Java está ativado) e `N` (O Java está desativado). |
| `environment.browserDetails.userAgent` | Usado como um método de identificação [visitante único](../../components/metrics/unique-visitors.md) de fallback. Normalmente preenchida com o uso do cabeçalho da solicitação HTTP do `User-Agent`. Você pode mapear esse campo para uma eVar se quiser usá-la nos relatórios. |
| `environment.browserDetails.viewportHeight` | Define a dimensão [Altura da janela do navegador](../../components/dimensions/browser-height.md). |
| `environment.browserDetails.viewportWidth` | Define a dimensão [Largura do navegador](../../components/dimensions/browser-width.md). |
| `environment.carrier` | A dimensão móvel [Nome da operadora](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Ajuda a definir a dimensão [Tipo de conexão](../../components/dimensions/connection-type.md). |
| `environment.ipV4` | Usado como um método de identificação [visitante único](../../components/metrics/unique-visitors.md) de fallback. Normalmente preenchida com o uso do cabeçalho HTTP do `X-Forwarded-For`. |
| `environment.language` | A localidade da dimensão móvel. |
| `environment.operatingSystem` | A dimensão móvel [Sistema operacional](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | Ajuda a definir a dimensão [Versão do sistema operacional](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Define a respectiva dimensão da [eVar](../../components/dimensions/evar.md). |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | O delimitador usado para uma determinada [Propriedade de lista](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Uma matriz de sequência de caracteres que contém os respectivos valores da [Propriedade de lista](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena todas as strings `value` em cada matriz `list[]` à sua respectiva [variável de lista](../vars/page-vars/list.md) usando vírgulas como delimitadores. |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | Define a respectiva dimensão de [Propriedade](../../components/dimensions/prop.md). |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | Aplica a [serialização de eventos](../vars/page-vars/events/event-serialization.md) à respectiva métrica de [Eventos personalizados](../../components/metrics/custom-events.md). |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | Aumenta a respectiva métrica de [Eventos personalizados](../../components/metrics/custom-events.md) na quantidade desejada. |
| `identityMap.ECID[0].id` | A [ID do serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). |
| `marketing.trackingCode` | Define a dimensão [Código de rastreamento](../../components/dimensions/tracking-code.md). |
| `media.mediaTimed.completes.value` | A métrica [Conteúdo concluído](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-complete) do Media Analytics. |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | A métrica [Dados federados](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#federated-data) do Media Analytics. |
| `media.mediaTimed.firstQuartiles.value` | A métrica [Marcador de progresso de 25%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#twenty-five-progress-marker) do Media Analytics. |
| `media.mediaTimed.mediaSegmentView.value` | A métrica [Visualizações do segmento de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-segment-views) do Media Analytics. |
| `media.mediaTimed.midpoints.value` | A métrica [Marcador de progresso de 50%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#fifty-progress-marker) do Media Analytics. |
| `media.mediaTimed.pauseTime.value` | A métrica [Duração total da pausa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#total-pause-duration) do Media Analytics. |
| `media.mediaTimed.pauses.value` | A métrica [Pausar eventos](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#pause-events) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | A dimensão [ID do ativo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#asset-id) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | A dimensão [Nome do vídeo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#video-name) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | A dimensão [Originador](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#originator) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | A dimensão [Episódio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#episode) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | A dimensão [Gênero](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#genre) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | A dimensão [Classificação de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-rating) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | A dimensão [Temporada](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#season) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | A dimensão [ID de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-id) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | A dimensão [Programa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#show) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | A dimensão [Tipo de programa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#show-type) do Media Analytics. |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | A dimensão [Duração do vídeo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#video-length) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | A dimensão [ID da sessão de mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#media-session-id) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | A dimensão [Canal de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-channel) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | A dimensão [Tipo de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-type) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | A dimensão [Rede](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#network) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | A dimensão [Segmento de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-segment) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | A dimensão [Nome do reprodutor de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-player-name) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | A dimensão [Versão do SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#sdk-version) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | A dimensão [Tipo de feed de mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#media-feed-type) do Media Analytics. |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | A dimensão [Formato de transmissão](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#stream-format) do Media Analytics. |
| `media.mediaTimed.progress10.value` | A métrica [Marcador de progresso de 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#ten-progress-marker) do Media Analytics. |
| `media.mediaTimed.progress95.value` | A métrica [Marcador de progresso de 95%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#ninety-five-progress-marker) do Media Analytics. |
| `media.mediaTimed.resumes.value` | A métrica [Resumo do conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-resumes) do Media Analytics. |
| `media.mediaTimed.starts.value` | A métrica [Inícios da mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#media-starts) do Media Analytics. |
| `media.mediaTimed.thirdQuartiles.value` | A métrica [Marcador de progresso de 75%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#seventy-five-progress-marker) do Media Analytics. |
| `media.mediaTimed.timePlayed.value` | A métrica [Tempo gasto com conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#content-time-spent) do Media Analytics. |
| `media.mediaTimed.totalTimePlayed.value` | A métrica [Tempo gasto com a mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=pt-BR#media-time-spent) do Media Analytics. |
| `placeContext.geo.latitude` | A latitude da dimensão móvel. |
| `placeContext.geo.longitude` | A longitude da dimensão móvel. |
| `placeContext.geo.postalCode` | A dimensão [Código postal](../../components/dimensions/zip-code.md). |
| `placeContext.geo.stateProvince` | A dimensão [Estados dos Estados Unidos](../../components/dimensions/us-states.md). |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Aplica um merchandising de [sintaxe do produto](../vars/page-vars/products.md) para eVars. |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Aplica um merchandising de [sintaxe do produto](../vars/page-vars/products.md) para eventos. |
| `productListItems[].lineItemId` | A dimensão [Categoria](../../components/dimensions/category.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). |
| `productListItems[].name` | A dimensão [Produto](../../components/dimensions/product.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). Se `productListItems[].SKU` e `productListItems[].name` contêm dados, o valor em `productListItems[].SKU` é usado. |
| `productListItems[].priceTotal` | Ajuda a determinar a métrica [Receita](../../components/metrics/revenue.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). |
| `productListItems[].quantity` | Ajuda a determinar a métrica [Unidades](../../components/metrics/units.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). |
| `productListItems[].SKU` | A dimensão [Produto](../../components/dimensions/product.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). Se `productListItems[].SKU` e `productListItems[].name` contêm dados, o valor em `productListItems[].SKU` é usado. |
| `web.webInteraction.URL` | A variável de implementação [linkURL](../vars/config-vars/linkurl.md). |
| `web.webInteraction.name` | A dimensão [Link personalizado](../../components/dimensions/custom-link.md), [Link de download](../../components/dimensions/download-link.md) ou [Link de saída](../../components/dimensions/exit-link.md), dependendo do valor em `web.webInteraction.type` |
| `web.webInteraction.type` | Determina o tipo de link clicado. Os valores válidos incluem `other` (Links personalizados), `download` (Links de download) e `exit` (Links de saída). |
| `web.webPageDetails.URL` | A dimensão [URL da página](../../components/dimensions/page-url.md). |
| `web.webPageDetails.errorPage` | Sinalizador que ajuda a determinar a [dimensão](../../components/dimensions/pages-not-found.md) e a [métrica](../../components/metrics/pages-not-found.md) “Páginas não encontradas”. |
| `web.webPageDetails.name` | A dimensão [Página](../../components/dimensions/page.md). |
| `web.webPageDetails.server` | A dimensão [Servidor](../../components/dimensions/server.md). |
| `web.webPageDetails.siteSection` | A dimensão [Seção do site](../../components/dimensions/site-section.md). |
| `web.webReferrer.URL` | A dimensão [Referenciador](../../components/dimensions/referrer.md). |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mapeamento de outros campos XDM para variáveis do Analytics

Se houver dimensões ou métricas que você deseja adicionar ao Adobe Analytics, faça isso por meio de [Variáveis de dados de contexto](../vars/page-vars/contextdata.md). Quaisquer elementos de campo XDM que não são mapeados automaticamente são enviados para o Adobe Analytics como dados de contexto com o prefixo a.x. Em seguida, é possível mapear essa variável de dados de contexto para a variável do Analytics desejada usando [regras de processamento](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=pt-BR). Por exemplo, se você enviar o seguinte evento:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

O SDK da Web envia esses dados para o Adobe Analytics como a variável de dados de contexto `a.x._atag.search.term`. Em seguida, você pode usar uma regra de processamento para atribuir esse valor de variável de dados de contexto à variável do Analytics desejada, como uma eVar:

![Pesquisar regra de processamento de termos](assets/examplerule.png)
