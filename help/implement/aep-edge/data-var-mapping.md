---
title: Mapeamento da variável de objeto de dados para o Adobe Analytics
description: Visualize quais campos de objeto de dados o Experience Platform Edge mapeia automaticamente para variáveis do Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: 97d830653bfb9ad68d1d885dd8dff0ecf49055d7
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 5%

---

# Mapeamento da variável de objeto de dados para o Adobe Analytics

A tabela a seguir mostra as variáveis de objeto de dados que a Rede de borda da Adobe Experience Platform mapeia automaticamente para a Adobe Analytics. Se você usar esses caminhos de campo de objeto de dados, nenhuma configuração adicional será necessária para enviar dados para o Adobe Analytics.

O uso desses campos é recomendado se você pretende usar o Customer Journey Analytics no futuro. Esse método de implementação permite que sua organização envie dados para o Adobe usando o SDK da Web sem estar em conformidade com um esquema XDM. Quando sua organização estiver pronta para enviar dados para a Adobe Experience Platform, você poderá usar [Mapeamento de sequência de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/data-prep.html#mapping) para apontar campos de objeto de dados para seus respectivos campos XDM.

## Prioridades de valor

A maioria dos campos de objeto de dados nesta tabela coincide com um [campo XDM mapeado](xdm-var-mapping.md). Se você definir uma determinada `data` e seu respectivo campo XDM, o campo do objeto de dados terá prioridade. Se você usar os campos de objeto XDM e objeto de dados, o Adobe recomenda definir eventos personalizados usando o campo objeto de dados. Se o campo `data.__adobe.analytics.events` estiver presente, substituirá todos os campos de objeto XDM relacionados ao comércio e aos eventos personalizados.

Alguns campos de objetos de dados também oferecem suporte aos respectivos [Consultar valor de parâmetro](../validate/query-parameters.md) como valores abreviados. Você pode usar campos padrão de objetos de dados e campos abreviados de objetos de dados alternadamente, desde que cada um deles seja para variáveis exclusivas. Evite definir um campo de objeto de dados padrão e seu respectivo campo de objeto de dados abreviado ao mesmo tempo. O Adobe não pode garantir qual campo tem prioridade.

## Mapeamento de campo do objeto de dados

As atualizações anteriores desta tabela podem ser encontradas no [histórico de confirmações desta página no GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/data-var-mapping.md).

| Caminho do campo de objeto de dados | Variável e descrição do Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | A variável [Altura do navegador](../../components/dimensions/browser-height.md) dimensão. O campo abreviado `data.__adobe.analytics.bh` O também é compatível. |
| `data.__adobe.analytics.browserWidth` | A variável [Largura do navegador](../../components/dimensions/browser-width.md) dimensão. O campo abreviado `data.__adobe.analytics.bw` O também é compatível. |
| `data.__adobe.analytics.campaign` | A variável [Código de rastreamento](../../components/dimensions/tracking-code.md) dimensão. O campo abreviado `data.__adobe.analytics.v0` O também é compatível. |
| `data.__adobe.analytics.channel` | A variável [Seção do site](../../components/dimensions/site-section.md) dimensão. O campo abreviado `data.__adobe.analytics.ch` O também é compatível. |
| `data.__adobe.analytics.colorDepth` | A variável [Intensidade de cor](../../components/dimensions/color-depth.md) dimensão. O campo abreviado `data.__adobe.analytics.c` O também é compatível. |
| `data.__adobe.analytics.connectionType` | A variável [Tipo de conexão](../../components/dimensions/connection-type.md) dimensão. O campo abreviado `data.__adobe.analytics.ct` O também é compatível. |
| `data.__adobe.analytics.contextData` | [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | A variável [Suporte a cookies](../../components/dimensions/cookie-support.md) dimensão. O campo abreviado `data.__adobe.analytics.k` O também é compatível. |
| `data.__adobe.analytics.currencyCode` | A variável [`currencyCode`](../vars/config-vars/currencycode.md) variável de implementação. O campo abreviado `data.__adobe.analytics.cc` O também é compatível. |
| `data.__adobe.analytics.dynamicVariablePrefix` | A variável [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) variável de implementação. |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | [eVar](../../components/dimensions/evar.md) dimensões. Os campos abreviados `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` também são compatíveis. |
| `data.__adobe.analytics.events` | [Eventos personalizados](../../components/metrics/custom-events.md). Formatar este campo de forma semelhante à [`events`](../vars/page-vars/events/events-overview.md) variável de implementação. |
| `data.__adobe.analytics.javaEnabled` | A variável [Java ativado](../../components/dimensions/java-enabled.md) dimensão. O campo abreviado `data.__adobe.analytics.v` O também é compatível. |
| `data.__adobe.analytics.latitude` | Ajuda a definir o [Localização](../../components/dimensions/lifecycle-dimensions.md) dimensões do ciclo de vida móvel. O campo abreviado `data.__adobe.analytics.lat` O também é compatível. |
| `data.__adobe.analytics.linkName` | A variável [Link personalizado](../../components/dimensions/custom-link.md), [Link de download](../../components/dimensions/download-link.md)ou [Link de saída](../../components/dimensions/exit-link.md) dimensão, dependendo do valor em `data.__adobe.analytics.linkType`. O campo abreviado `data.__adobe.analytics.pev2` O também é compatível. |
| `data.__adobe.analytics.linkURL` | A variável [`linkURL`](../vars/config-vars/linkurl.md) variável de implementação. O campo abreviado `data.__adobe.analytics.pev1` O também é compatível. |
| `data.__adobe.analytics.linkType` | Determina o tipo de link clicado. Os valores válidos incluem `o` (Links personalizados), `d` (Links de download) e `e` (Links de saída). O campo abreviado `data.__adobe.analytics.pe` O também é compatível. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | [`list`](/help/implement/vars/page-vars/list.md) variáveis de implementação. Os campos abreviados `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` também são compatíveis. |
| `data.__adobe.analytics.longitude` | Ajuda para definir o [Localização](../../components/dimensions/lifecycle-dimensions.md) dimensões do ciclo de vida móvel. O campo abreviado `data.__adobe.analytics.lon` O também é compatível. |
| `data.__adobe.analytics.pageName` | A dimensão [Página](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | A variável [URL da página](/help/components/dimensions/page-url.md) dimensão. O campo abreviado `data.__adobe.analytics.g` O também é compatível. |
| `data.__adobe.analytics.pageType` | A variável [`pageType`](../vars/page-vars/pagetype.md) variável de implementação. |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | [Prop](../../components/dimensions/prop.md) dimensões. Os campos abreviados `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` também são compatíveis. |
| `data.__adobe.analytics.purchaseID` | A variável [`purchaseID`](../vars/page-vars/purchaseid.md) variável de implementação. |
| `data.__adobe.analytics.products` | A variável [`products`](../vars/page-vars/products.md) variável de implementação, seguindo uma formatação semelhante. |
| `data.__adobe.analytics.referrer` | A dimensão [Referenciador](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | A variável [Resolução do monitor](../../components/dimensions/monitor-resolution.md) dimensão. O campo abreviado `data.__adobe.analytics.s` O também é compatível. |
| `data.__adobe.analytics.server` | A dimensão [Servidor](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | A variável [`transactionID`](../vars/page-vars/transactionid.md) variável de implementação. O campo abreviado `data.__adobe.analytics.xact` O também é compatível. |
| `data.__adobe.analytics.zip` | A variável [Código postal](../../components/dimensions/zip-code.md) dimensão. |

{style="table-layout:auto"}