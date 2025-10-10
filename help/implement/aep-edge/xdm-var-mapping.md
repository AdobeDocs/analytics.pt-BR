---
title: Mapeamento da variável de objeto XDM para o Adobe Analytics
description: Visualize quais campos XDM a borda mapeia automaticamente para variáveis do Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1469'
ht-degree: 48%

---

# Mapeamento da variável de objeto XDM para o Adobe Analytics

A tabela a seguir mostra as variáveis XDM que o Adobe Experience Platform Edge Network mapeia automaticamente para o Adobe Analytics. Se você usar esses caminhos de campo XDM, nenhuma configuração adicional será necessária para enviar dados para o Adobe Analytics. Esses campos estão incluídos no grupo de campos **[!UICONTROL Modelo de evento de experiência do Adobe Analytics]**. O uso desses campos é recomendado se você pretende enviar dados para o Adobe Analytics e o Adobe Experience Platform.

Se sua organização planeja migrar para o Customer Journey Analytics, a Adobe recomenda usar o objeto `data` para enviar dados diretamente para o Adobe Analytics sem estar em conformidade com um esquema. Essa estratégia permite que sua organização use seu próprio esquema, em vez de usar o [!UICONTROL Modelo de evento de experiência do Adobe Analytics] (que é menos aplicável ao Customer Journey Analytics). Consulte [Mapeamento de variável de objeto de dados para o Adobe Analytics](data-var-mapping.md) para obter uma tabela de mapeamento semelhante.

## Prioridades de valor

A maioria dos campos de objeto XDM nesta tabela coincide com um [campo de objeto de dados](data-var-mapping.md). Se você definir um determinado campo de objeto XDM e seu respectivo campo de objeto de dados, o campo de objeto de dados terá prioridade. Se você usar os campos de objeto XDM e objeto de dados, a Adobe recomenda definir eventos personalizados usando o campo objeto de dados. Se o campo `data.__adobe.analytics.events` estiver presente, ele substituirá todos os campos de objeto XDM relacionados ao comércio e aos eventos personalizados.

## Mapeamento de campo do objeto XDM

As atualizações anteriores desta tabela podem ser encontradas no [histórico de confirmações desta página no GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md).

| Caminho de campo XDM | Variável e descrição do Analytics |
| --- | --- |
| `xdm.application.isClose` | Ajuda a definir a métrica de ciclo de vida móvel [Falhas](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Ajuda a determinar quando aumentar a métrica de ciclo de vida móvel [Primeiras inicializações](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Determina se um evento de encerramento é uma falha ou não. Os valores válidos incluem `close` (Uma sessão de ciclo de vida termina e um evento de pausa foi recebido para a sessão anterior) e `unknown` (Uma sessão do ciclo de vida termina sem um evento de pausa). Ajuda a definir a métrica de ciclo de vida móvel [Falhas](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | A métrica de ciclo de vida móvel [Instalações](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | A métrica de ciclo de vida móvel [Inicializações](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Ajuda a definir a dimensão de ciclo de vida móvel [ID do aplicativo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isUpgrade` | A métrica de ciclo de vida móvel [Atualizações](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Ajuda a definir a dimensão de ciclo de vida móvel [ID do aplicativo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | A métrica de ciclo de vida móvel [Duração da sessão anterior](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) para a métrica [Check-outs](/help/components/metrics/checkouts.md). |
| `xdm.commerce.checkouts.value` | Aumenta a métrica [Check-outs](/help/components/metrics/checkouts.md) pela quantidade desejada. |
| `xdm.commerce.order.currencyCode` | Define a variável da configuração [currencyCode](../vars/config-vars/currencycode.md). |
| `xdm.commerce.order.purchaseID` | Define a variável da página [purchaseID](../vars/page-vars/purchaseid.md). |
| `xdm.commerce.order.payments[0].transactionID` | Define a variável de página [transactionID](../vars/page-vars/transactionid.md). |
| `xdm.commerce.productListAdds.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Adições ao carrinho](/help/components/metrics/cart-additions.md). |
| `xdm.commerce.productListAdds.value` | Incrementa a métrica [Adições ao carrinho](/help/components/metrics/cart-additions.md). |
| `xdm.commerce.productListOpens.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Carrinhos](/help/components/metrics/carts.md). |
| `xdm.commerce.productListOpens.value` | Incrementa a métrica [Carrinhos](/help/components/metrics/carts.md). |
| `xdm.commerce.productListRemovals.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Remoções do carrinho](/help/components/metrics/cart-removals.md). |
| `xdm.commerce.productListRemovals.value` | Incrementa a métrica [Remoções do carrinho](/help/components/metrics/cart-removals.md). |
| `xdm.commerce.productListViews.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Visualizações do carrinho](/help/components/metrics/cart-views.md). |
| `xdm.commerce.productListViews.value` | Incrementa a métrica [Visualizações do carrinho](/help/components/metrics/cart-views.md). |
| `xdm.commerce.productViews.id` | Aplica [serialização de eventos](../vars/page-vars/events/event-serialization.md) à métrica [Visualizações do produto](/help/components/metrics/product-views.md). |
| `xdm.commerce.productViews.value` | Incrementa a métrica [Visualizações de produto](/help/components/metrics/product-views.md). |
| `xdm.commerce.purchases.value` | Incrementa a métrica [Pedidos](/help/components/metrics/orders.md). |
| `xdm.device.model` | A dimensão de ciclo de vida móvel [Nome do dispositivo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Ajuda a definir a dimensão [Intensidade de cor](/help/components/dimensions/color-depth.md). |
| `xdm.device.screenHeight` | Ajuda a definir a dimensão [Resolução do monitor.](/help/components/dimensions/monitor-resolution.md) |
| `xdm.device.screenWidth` | Ajuda a definir a dimensão [Resolução do monitor.](/help/components/dimensions/monitor-resolution.md) |
| `xdm.device.type` | O tipo de dispositivo móvel. |
| `xdm.environment.browserDetails.acceptLanguage` | Ajuda a definir a dimensão [Idioma](/help/components/dimensions/language.md). |
| `xdm.environment.browserDetails.cookiesEnabled` | Define a dimensão [Suporte a cookies](/help/components/dimensions/cookie-support.md). Os valores válidos incluem `Y` (o navegador aceita cookies) e `N` (o navegador rejeita cookies). |
| `xdm.environment.browserDetails.javaEnabled` | Define a dimensão [Java habilitado](/help/components/dimensions/java-enabled.md). Os valores válidos incluem `Y` (O Java está habilitado) e `N` (O Java está desabilitado). |
| `xdm.environment.browserDetails.userAgent` | Usado como um método de identificação [visitante único](/help/components/metrics/unique-visitors.md) de fallback. Normalmente preenchida com o uso do cabeçalho da solicitação HTTP do `User-Agent`. Você pode mapear esse campo para uma eVar se quiser usá-la nos relatórios. |
| `xdm.environment.browserDetails.viewportHeight` | Define a dimensão [Altura da janela do navegador](/help/components/dimensions/browser-height.md). |
| `xdm.environment.browserDetails.viewportWidth` | Define a dimensão [Largura do navegador](/help/components/dimensions/browser-width.md). |
| `xdm.environment.carrier` | A dimensão de ciclo de vida móvel [Nome da operadora](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Ajuda a definir a dimensão [Tipo de conexão](/help/components/dimensions/connection-type.md). |
| `xdm.environment._dc.language` | Define a variável de dados de contexto `a.locale`. Usado apenas se `xdm.environment.language` não estiver definido. A Adobe recomenda usar este campo sobre `xdm.environment.language`. |
| `xdm.environment.ipV4` | Usado como um método de identificação [visitante único](/help/components/metrics/unique-visitors.md) de fallback. Normalmente preenchida com o uso do cabeçalho HTTP do `X-Forwarded-For`. |
| `xdm.environment.language` | Define a variável de dados de contexto `a.locale`. Em vez disso, a Adobe recomenda usar `xdm.environment._dc.language`. |
| `xdm.environment.operatingSystem` | A dimensão de ciclo de vida móvel [Sistema operacional](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.operatingSystemVersion` | Ajuda a definir a dimensão de ciclo de vida móvel [Versão do sistema operacional](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Define a respectiva dimensão da [eVar](/help/components/dimensions/evar.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier5` | Define a respectiva dimensão da [Hierarquia](/help/components/dimensions/hierarchy.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Sobreposição do delimitador de propriedade de lista. O uso desse campo não é recomendado, pois o delimitador é recuperado automaticamente do [Administrador da variável de tráfego](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios. O uso desse campo pode criar uma incompatibilidade entre o delimitador usado e o delimitador esperado pelo Analytics. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Uma matriz de sequência de caracteres que contém os respectivos valores da [Propriedade de lista](../vars/page-vars/prop.md#list-props). |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena todas as strings `value` em cada matriz `list[]` à sua respectiva [variável de lista](../vars/page-vars/list.md). O delimitador é escolhido automaticamente com base no valor definido em [configurações do conjunto de relatórios](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Define a respectiva dimensão de [Propriedade](/help/components/dimensions/prop.md). |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Aplica a [serialização de eventos](../vars/page-vars/events/event-serialization.md) à respectiva métrica de [Eventos personalizados](/help/components/metrics/custom-events.md). Cada ID de evento reside no grupo principal de um conjunto de 100 grupos. Por exemplo, para aplicar a serialização a `event678`, use `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Aumenta a respectiva métrica de [Eventos personalizados](/help/components/metrics/custom-events.md) de acordo com o valor desejado. Cada evento reside no grupo principal de um conjunto de 100 grupos. Por exemplo, o campo para `event567` é `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | A [ID do serviço de identidade da Adobe Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home). |
| `xdm.marketing.trackingCode` | Define a dimensão [Código de rastreamento](/help/components/dimensions/tracking-code.md). |
| `xdm.media.mediaTimed.completes.value` | A métrica de serviços de mídia de streaming [Conteúdo concluído](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `a.media.view`, `a.media.timePlayed`, `a.media.play` |
| `xdm.media.mediaTimed.federated.value` | A métrica de serviços de mídia de streaming [Dados Federados](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | A métrica de serviços de mídia de streaming [Marcador de progresso de 25%](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#twenty-five--progress-marker). |
| `xdm.media.mediaTimed.mediaSegmentView.value` | A métrica de serviços de mídia de streaming [Exibições de Segmento de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | A métrica de serviços de streaming de mídia [Marcador de progresso de 50%](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#progress-marker). |
| `xdm.media.mediaTimed.pauseTime.value` | A métrica de serviços de mídia de streaming [Duração total da pausa](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | A métrica [Pausar Eventos](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#pause-events) dos serviços de mídia de streaming. |
| `xdm.mediaCollection.sessionDetails.assetID` | A dimensão [ID do ativo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#asset-id) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.friendlyName` | A dimensão [Nome do Vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-name) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.originator` | A dimensão [Originador](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#originator) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.episode` | A dimensão [Episódio](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#episode) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.genre` | A dimensão [Gênero](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#genre) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.rating` | A dimensão [Classificação de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-rating) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.season` | A dimensão [Temporada](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#season) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.name` | A dimensão [ID de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-id) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.show` | A dimensão de serviços de streaming de mídia [Programa](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#show). |
| `xdm.mediaCollection.sessionDetails.showType` | A dimensão [Tipo de programa](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#show-type) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.length` | A dimensão [Duração do vídeo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-length) dos serviços de streaming de mídia. |
| `xdm.media.mediaTimed.primaryAssetViewDetails.@id` | A dimensão [ID da Sessão de Mídia](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-session-id) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.channel` | A dimensão [Canal de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-channel) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.contentType` | A dimensão [Tipo de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-type) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.network` | A dimensão [Rede](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#network) dos serviços de streaming de mídia. |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | A dimensão [Segmento de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.playerName` | A dimensão [Nome do Player de Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-player-name) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.appVersion` | A dimensão [Versão do SDK](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#sdk-version) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.feed` | A dimensão [Tipo de Feed de Mídia](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-feed-type) dos serviços de streaming de mídia. |
| `xdm.mediaCollection.sessionDetails.streamFormat` | A dimensão de serviços de streaming de mídia [Formato de Stream](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | A métrica de serviços de streaming de mídia [Marcador de progresso de 10%](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#ten--progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | A métrica de serviços de mídia de streaming [Marcador de progresso de 95%](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#ninety-five--progress-marker). |
| `xdm.mediaCollection.sessionDetails.hasResume` | A métrica de serviços de streaming de mídia [Resumo do Conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | A métrica de serviços de streaming de mídia [Inícios da mídia](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | A métrica de serviços de streaming de mídia [Marcador de progresso de 75%](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#seventy-five--progress-marker). |
| `xdm.media.mediaTimed.timePlayed.value` | A métrica de serviços de mídia de streaming [Tempo gasto com conteúdo](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | A métrica de serviços de mídia de streaming [Tempo gasto com a mídia](https://experienceleague.adobe.com/pt-br/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | O local de latitude do visitante. Ajuda a definir as dimensões [Local do ciclo de vida móvel](/help/components/dimensions/lifecycle-dimensions.md). |
| `xdm.placeContext.geo._schema.longitude` | O local da longitude do visitante. Ajuda a definir as dimensões [Local do ciclo de vida móvel](/help/components/dimensions/lifecycle-dimensions.md). |
| `xdm.placeContext.geo.postalCode` | A dimensão [Código postal](/help/components/dimensions/zip-code.md). |
| `xdm.placeContext.geo.stateProvince` | A dimensão [Estados dos Estados Unidos](/help/components/dimensions/us-states.md). |
| `xdm.placeContext.localTime` | Aparece como `t_time_info` nos [feeds de dados](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Aplica um merchandising de [sintaxe do produto](../vars/page-vars/products.md) para eVars. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Aplica um merchandising de [sintaxe do produto](../vars/page-vars/products.md) para eventos. |
| `xdm.productListItems[].productCategories[].categoryID` | A dimensão [Categoria](/help/components/dimensions/category.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). |
| `xdm.productListItems[].name` | A dimensão [Produto](/help/components/dimensions/product.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). Se `xdm.productListItems[].SKU` e `xdm.productListItems[].name` contêm dados, o valor em `xdm.productListItems[].SKU` é usado. |
| `xdm.productListItems[].priceTotal` | Ajuda a determinar a métrica [Receita](/help/components/metrics/revenue.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). |
| `xdm.productListItems[].quantity` | Ajuda a determinar a métrica [Unidades](/help/components/metrics/units.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). |
| `xdm.productListItems[].SKU` | A dimensão [Produto](/help/components/dimensions/product.md). Consulte também a variável da página de [produtos](../vars/page-vars/products.md). Se `xdm.productListItems[].SKU` e `xdm.productListItems[].name` contêm dados, o valor em `xdm.productListItems[].SKU` é usado. |
| `xdm.web.webInteraction.URL` | A variável de implementação [linkURL](../vars/config-vars/linkurl.md). |
| `xdm.web.webInteraction.name` | A dimensão [Link personalizado](/help/components/dimensions/custom-link.md), [Link de download](/help/components/dimensions/download-link.md) ou [Link de saída](/help/components/dimensions/exit-link.md), dependendo do valor em `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Determina o tipo de link clicado. Os valores válidos incluem `other` (Links personalizados), `download` (Links de download) e `exit` (Links de saída). |
| `xdm.web.webPageDetails.URL` | A dimensão [URL da página](/help/components/dimensions/page-url.md). |
| `xdm.web.webPageDetails.isErrorPage` | Sinalizador que ajuda a determinar a [dimensão](/help/components/dimensions/pages-not-found.md) e a [métrica](/help/components/metrics/pages-not-found.md) “Páginas não encontradas”. |
| `xdm.web.webPageDetails.name` | A dimensão [Página](/help/components/dimensions/page.md). |
| `xdm.web.webPageDetails.server` | A dimensão [Servidor](/help/components/dimensions/server.md). |
| `xdm.web.webPageDetails.siteSection` | A dimensão [Seção do site](/help/components/dimensions/site-section.md). |
| `xdm.web.webReferrer.URL` | A dimensão [Referenciador](/help/components/dimensions/referrer.md). |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mapeamento de outros campos XDM para variáveis do Analytics

Se houver dimensões ou métricas que você deseja adicionar ao Adobe Analytics, faça isso por meio de [Variáveis de dados de contexto](../vars/page-vars/contextdata.md).

### Mapeamento implícito

Quaisquer elementos de campo XDM que não são mapeados automaticamente são enviados para o Adobe Analytics como dados de contexto com o prefixo `a.x.`. Você pode mapear essa variável de dados de contexto para a variável do Analytics desejada usando [regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md). Por exemplo, se você enviar o seguinte evento:

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

O SDK da Web envia esses dados para o Adobe Analytics como a variável de dados de contexto `a.x._atag.search.term`. Em seguida, você pode usar uma regra de processamento para atribuir esse valor de variável de dados de contexto à variável do Analytics desejada, como um `eVar`:

![Regra de processamento de termo de pesquisa](assets/examplerule.png)

## Mapeamento explícito

Também é possível mapear explicitamente elementos de campo XDM como dados de contexto. Qualquer elemento de campo XDM que seja mapeado explicitamente, usando o elemento `contextData`, é enviado para o Adobe Analytics como dados de contexto sem um prefixo. Você pode mapear essa variável de dados de contexto para a variável do Analytics desejada usando [regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md). Por exemplo, se você enviar o seguinte evento:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "analytics": {
                "contextData" : {
                    "someValue" : "1"
                }
            }
        }
    }
})
```

O Web SDK envia esses dados para o Adobe Analytics como a variável de dados de contexto `somevalue` com o valor `1`.  Em seguida, você pode usar uma regra de processamento para atribuir esse valor de variável de dados de contexto à variável do Analytics desejada, como um `eVar`:

![Regra de processamento de termo de pesquisa](assets/examplerule-explicit.png)
