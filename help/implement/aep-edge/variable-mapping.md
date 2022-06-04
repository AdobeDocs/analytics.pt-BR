---
title: Mapeamento de variável do Analytics no Adobe Experience Edge
description: Visualize quais campos XDM o Edge mapeia automaticamente para variáveis do Analytics.
source-git-commit: 984d62f6ece15ebbd41dbbd1e3cb800faa7f323b
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---


# Mapeamento de variável do Analytics no Adobe Experience Edge

A tabela a seguir mostra as variáveis que a Rede de borda do Adobe Experience Platform mapeia automaticamente para o Adobe Analytics. Se você usar esses Caminhos de campo XDM, nenhuma configuração adicional será necessária para enviar dados para a Adobe Analytics.

| Caminho do campo XDM | Dimensão e descrição do Analytics |
| --- | --- |
| `application.id` | A dimensão móvel [ID do aplicativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.isClose` | Ajuda a definir a métrica móvel [Falhas](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Determina se um evento de fechamento é uma falha ou não. Os valores válidos incluem `close` (Uma sessão de ciclo de vida termina e um evento de pausa foi recebido para a sessão anterior) e `unknown` (Uma sessão do ciclo de vida termina sem um evento de pausa). |
| `application.isInstall` | A métrica móvel [Instala](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | A métrica móvel [Lançamentos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Ajuda a definir a dimensão móvel [ID do aplicativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.launches.value` | A métrica móvel [Lançamentos](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isUpgrade` | A métrica móvel [Atualizações](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Ajuda a definir a dimensão móvel [ID do aplicativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | A métrica móvel [Duração total da sessão](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Aplica-se [serialização de eventos](../vars/page-vars/events/event-serialization.md) para [Check-outs](../../components/metrics/checkouts.md) métrica. |
| `commerce.checkouts.value` | Aumenta o [Check-outs](../../components/metrics/checkouts.md) pela quantidade desejada. |
| `commerce.order.currencyCode` | Define a variável [currencyCode](../vars/config-vars/currencycode.md) variável de configuração. |
| `commerce.order.purchaseID` | Define a variável [purchaseID](../vars/page-vars/purchaseid.md) variável de página. |
| `commerce.productListAdds.id` | Aplica-se [serialização de eventos](../vars/page-vars/events/event-serialization.md) para [Adições ao carrinho](../../components/metrics/cart-additions.md) métrica. |
| `commerce.productListAdds.value` | Aumenta o [Adições ao carrinho](../../components/metrics/cart-additions.md) pela quantidade desejada. |
| `commerce.productListOpens.id` | Aplica-se [serialização de eventos](../vars/page-vars/events/event-serialization.md) para [Carrinhos](../../components/metrics/carts.md) métrica. |
| `commerce.productListOpens.value` | Aumenta o [Carrinhos](../../components/metrics/carts.md) pela quantidade desejada. |
| `commerce.productListRemovals.id` | Aplica-se [serialização de eventos](../vars/page-vars/events/event-serialization.md) para [Remoções do carrinho](../../components/metrics/cart-removals.md) métrica. |
| `commerce.productListRemovals.value` | Aumenta o [Remoções do carrinho](../../components/metrics/cart-removals.md) pela quantidade desejada. |
| `commerce.productListViews.id` | Aplica-se [serialização de eventos](../vars/page-vars/events/event-serialization.md) para [Exibições do carrinho](../../components/metrics/cart-views.md) métrica. |
| `commerce.productListViews.value` | Aumenta o [Exibições do carrinho](../../components/metrics/cart-views.md) pela quantidade desejada. |
| `commerce.productViews.id` | Aplica-se [serialização de eventos](../vars/page-vars/events/event-serialization.md) para [Exibições do produto](../../components/metrics/product-views.md) métrica. |
| `commerce.productViews.value` | Aumenta o [Exibições do produto](../../components/metrics/product-views.md) pela quantidade desejada. |
| `commerce.purchases.value` | Aumenta o [Pedidos](../../components/metrics/orders.md) pela quantidade desejada. |
| `device.manufacturer` | O fabricante do dispositivo móvel. |
| `device.model` | A dimensão móvel [Nome do dispositivo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.modelNumber` | O número do modelo do dispositivo móvel. |
| `device.colorDepth` | Ajuda a definir a variável [Intensidade de cor](../../components/dimensions/color-depth.md) dimensão. |
| `device.screenHeight` | Ajuda a definir a variável [Resolução do Monitor](../../components/dimensions/monitor-resolution.md) dimensão. Certifique-se de também definir o campo XDM `device.screenWidth`. |
| `device.screenWidth` | Ajuda a definir a variável [Resolução do Monitor](../../components/dimensions/monitor-resolution.md) dimensão. Certifique-se de também definir o campo XDM `device.screenHeight`. |
| `device.type` | O tipo de dispositivo móvel. |
| `environment.browserDetails.acceptLanguage` | Ajuda a definir a variável [Idioma](../../components/dimensions/language.md) dimensão. |
| `environment.browserDetails.cookiesEnabled` | Define a variável [Suporte a cookies](../../components/dimensions/cookie-support.md) dimensão. Os valores válidos incluem `Y` (o navegador aceita cookies) e `N` (o navegador rejeita cookies). |
| `environment.browserDetails.javaEnabled` | Define a variável [Java ativado](../../components/dimensions/java-enabled.md) dimensão. Os valores válidos incluem `Y` (O Java está ativado) e `N` (O Java está desativado). |
| `environment.browserDetails.userAgent` | Usado como um fallback [visitante único](../../components/metrics/unique-visitors.md) método de identificação. Normalmente preenchida com o uso da variável `User-Agent` Cabeçalho da solicitação HTTP. Você pode mapear esse campo para um eVar se desejar usá-lo nos relatórios. |
| `environment.browserDetails.viewportHeight` | Define a variável [Altura da janela do navegador](../../components/dimensions/browser-height.md) dimensão. |
| `environment.browserDetails.viewportWidth` | Define a variável [Largura do navegador](../../components/dimensions/browser-width.md) dimensão. |
| `environment.carrier` | A dimensão móvel [Nome da operadora](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Ajuda a definir a variável [Tipo de conexão](../../components/dimensions/connection-type.md) dimensão. |
| `environment.ipV4` | Usado como um fallback [visitante único](../../components/metrics/unique-visitors.md) método de identificação. Normalmente preenchida com o uso da variável `X-Forwarded-For` Cabeçalho HTTP. |
| `environment.language` | A Localidade da dimensão móvel. |
| `environment.operatingSystem` | A dimensão móvel [Sistema operacional](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | A dimensão móvel [Versão do sistema operacional](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.type` | Indica se o evento veio de um [wearable](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/c-android-wearables--additional-notes.html) dispositivo. Os valores válidos incluem `Application` (o evento veio do aplicativo), `Extension` (o evento veio do aplicativo wearable), ou `Widget` (o evento veio de um widget móvel). |
| `identityMap.ECID[0].id` | O [ID do serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). |
| `marketing.trackingCode` | Define a variável [Código de rastreamento](../../components/dimensions/tracking-code.md) dimensão. |
| `media.mediaTimed.completes.value` | A métrica do Media Analytics [Conteúdo concluído](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | A métrica do Media Analytics [Dados federados](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | A métrica do Media Analytics [Marcador de progresso de 25%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | A métrica do Media Analytics [Visualizações do segmento de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `media.mediaTimed.midpoints.value` | A métrica do Media Analytics [Marcador de progresso de 50%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | A métrica do Media Analytics [Duração total da pausa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `media.mediaTimed.pauses.value` | A métrica do Media Analytics [Pausar eventos](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `media.mediaTimed.primaryAssetReference.@id` | A dimensão do Media Analytics [ID do ativo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `media.mediaTimed.primaryAssetReference.dc:title` | A dimensão do Media Analytics [Nome do vídeo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | A dimensão do Media Analytics [Originador](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Episode.iptc4xmpExt:Number` | A dimensão do Media Analytics [Episódio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Genre` | A dimensão do Media Analytics [Gênero](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | A dimensão do Media Analytics [Classificação de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Season.iptc4xmpExt:Number` | A dimensão do Media Analytics [Temporada](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Series.iptc4xmpExt:Identifier` | A dimensão do Media Analytics [ID de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `media.mediaTimed.primaryAssetReference.iptc4xmpExt:Series.iptc4xmpExt:Name` | A dimensão do Media Analytics [Mostrar](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `media.mediaTimed.primaryAssetReference.showType` | A dimensão do Media Analytics [Mostrar tipo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `media.mediaTimed.primaryAssetReference.xmpDM:duration` | A dimensão do Media Analytics [Duração do vídeo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.@id` | A dimensão do Media Analytics [ID da sessão de mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.broadcastChannel` | A dimensão do Media Analytics [Canal de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.broadcastContentType` | A dimensão do Media Analytics [Tipo de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.broadcastNetwork` | A dimensão do Media Analytics [Rede](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `media.mediaTimed.primaryAssetViewDetails.mediaSegmentView.value` | A dimensão do Media Analytics [Segmento de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.playerName` | A dimensão do Media Analytics [Nome do reprodutor de conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.playerSDKVersion.version` | A dimensão do Media Analytics [Versão do SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.sourceFeed` | A dimensão do Media Analytics [Tipo de feed de mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.streamFormat` | A dimensão do Media Analytics [Formato de transmissão](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `media.mediaTimed.progress10.value` | A métrica do Media Analytics [Marcador de progresso de 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | A métrica do Media Analytics [Marcador de progresso de 95%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | A métrica do Media Analytics [Resumo do conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `media.mediaTimed.starts.value` | A métrica do Media Analytics [Inícios da mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | A métrica do Media Analytics [Marcador de progresso de 75%](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | A métrica do Media Analytics [Tempo gasto com conteúdo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | A métrica do Media Analytics [Tempo gasto com a mídia](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `placeContext.geo.latitude` | A Latitude da dimensão móvel. |
| `placeContext.geo.longitude` | A Longitude da dimensão Móvel. |
| `placeContext.geo.postalCode` | O [Código Postal](../../components/dimensions/zip-code.md) dimensão. |
| `placeContext.geo.stateProvince` | O [Estados dos Estados Unidos](../../components/dimensions/us-states.md) dimensão. |
| `productListItems[N].lineItemId` | O [Categoria](../../components/dimensions/category.md) dimensão. |
| `productlistitems[N].name` | O [Produto](../../components/dimensions/product.md) dimensão. |
| `productlistitems[N].priceTotal` | Ajuda a determinar o [Receita](../../components/metrics/revenue.md) métrica. |
| `productlistitems[N].quantity` | Ajuda a determinar o [Unidades](../../components/metrics/units.md) métrica. |
| `web.webInteraction.URL` | O [linkURL](../vars/config-vars/linkurl.md) variável de implementação. |
| `web.webInteraction.name` | O [Link personalizado](../../components/dimensions/custom-link.md), [Link de download](../../components/dimensions/download-link.md)ou [Link de saída](../../components/dimensions/exit-link.md) , dependendo do valor em `web.webInteraction.type` |
| `web.webInteraction.type` | Determina o tipo de link clicado. Os valores válidos incluem `lnk_o` (Links personalizados), `lnk_d` (Links de download) e `lnk_e` (Links de saída). |
| `web.webPageDetails.URL` | O [URL da página](../../components/dimensions/page-url.md) dimensão. |
| `web.webPageDetails.errorPage` | Sinalizador que ajuda a determinar as &quot;Páginas não encontradas&quot; [dimension](../../components/dimensions/pages-not-found.md) e [métrica](../../components/metrics/pages-not-found.md). |
| `web.webPageDetails.name` | O [Página](../../components/dimensions/page.md) dimensão. |
| `web.webPageDetails.server` | O [Servidor](../../components/dimensions/server.md) dimensão. |
| `web.webPageDetails.siteSection` | O [Seção do site](../../components/dimensions/site-section.md) dimensão. |
| `web.webReferrer.URL` | O [Referenciador](../../components/dimensions/referrer.md) dimensão. |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mapeamento de outros campos XDM para variáveis do Analytics

Se houver dimensões ou métricas que você deseja adicionar ao Adobe Analytics, faça isso por meio de [Variáveis de dados de contexto](../vars/page-vars/contextdata.md). Todos os elementos de campo XDM são enviados para o Adobe Analytics como Dados de contexto com o prefixo `a.x`. Em seguida, é possível mapear essa variável de dados de contexto para a variável do Analytics desejada usando [Regras de processamento](../../admin/admin/c-processing-rules/processing-rules.md). Por exemplo, se você enviar o seguinte evento:

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

O SDK da Web envia esses dados para o Adobe Analytics como a variável de dados de contexto `a.x._atag.search.term`. Em seguida, você pode usar uma regra de processamento para atribuir esse valor de variável de dados de contexto à variável do Analytics desejada, como um eVar:

![Pesquisar regra de processamento de termos](assets/examplerule.png)
