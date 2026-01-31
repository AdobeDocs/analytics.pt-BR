---
title: Mapeamento de campo do objeto de dados para o Adobe Analytics
description: Veja quais campos de objetos de dados a Experience Platform Edge mapeia automaticamente para variáveis do Analytics.
feature: Implementation Basics
role: Admin, Developer
exl-id: 45b2fbbc-73ca-40b3-9484-b406ae99fdad
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 77%

---

# Mapeamento de campo do objeto de dados para o Adobe Analytics

A tabela a seguir mostra o campo do objeto de dados que o Adobe Experience Platform Edge Network mapeia automaticamente para o Adobe Analytics. Se você usar esses caminhos de campo de objeto de dados, nenhuma configuração adicional será necessária para enviar dados para o Adobe Analytics.

Recomenda-se o uso desses campos caso você pretenda utilizar o Customer Journey Analytics no futuro. Este método de implementação permite que sua organização envie dados para a Adobe usando o SDK da Web sem estar em conformidade com um esquema XDM. Quando sua organização estiver pronta para enviar dados para a Adobe Experience Platform, você poderá usar o [Mapeamento de sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/data-prep#mapping) para apontar campos de objeto de dados para seus respectivos campos XDM.

## Prioridades de valor

A maioria dos campos de objeto de dados nesta tabela corresponde a um [campo XDM mapeado](xdm-var-mapping.md). Durante a assimilação do Adobe Analytics, os valores são mapeados primeiro do XDM para as variáveis do Analytics. Os campos de objeto de dados reconhecidos são mapeados e substituem quaisquer valores definidos anteriormente quando eles são mapeados para a mesma variável do Analytics. Por exemplo, se `data.__adobe.analytics.events` estiver presente, ele substituirá todo o conjunto de eventos que de outra forma seriam derivados do XDM. Os eventos não são combinados em ambas as fontes. Uma cadeia de caracteres vazia (`""`) em um campo de objeto de dados deixa em branco sua variável do Analytics mapeada para a ocorrência, mesmo se o campo XDM correspondente contiver um valor.

Alguns campos de objetos de dados também oferecem suporte ao respectivo [Valor do parâmetro de consulta](../validate/query-parameters.md) como valores abreviados. Você pode usar campos padrão de objetos de dados e campos abreviados de objetos de dados alternadamente, desde que cada um deles seja para variáveis exclusivas. Evite definir um campo de objeto de dados padrão e seu respectivo campo de objeto de dados abreviado ao mesmo tempo. A Adobe não pode garantir qual campo tem prioridade.

## Mapeamento de campos de objetos de dados

As atualizações anteriores desta tabela podem ser encontradas no [histórico de confirmações desta página no GitHub](https://github.com/AdobeDocs/analytics.pt-br/commits/main/help/implement/aep-edge/data-var-mapping.md). De maneira semelhante às variáveis do AppMeasurement, todos os campos de objetos de dados fazem distinção entre maiúsculas e minúsculas.

| Caminho do campo de objeto de dados | Variável e descrição do Analytics |
| --- | --- |
| `data.__adobe.analytics.browserHeight` | A dimensão [Altura do navegador](../../components/dimensions/browser-height.md). O campo abreviado `data.__adobe.analytics.bh` também é aceito. |
| `data.__adobe.analytics.browserWidth` | A dimensão [Largura do navegador](../../components/dimensions/browser-width.md). O campo abreviado `data.__adobe.analytics.bw` também é aceito. |
| `data.__adobe.analytics.campaign` | A dimensão [Código de rastreamento](../../components/dimensions/tracking-code.md). O campo abreviado `data.__adobe.analytics.v0` também é aceito. |
| `data.__adobe.analytics.channel` | A dimensão [Seção do site](../../components/dimensions/site-section.md). O campo abreviado `data.__adobe.analytics.ch` também é aceito. |
| `data.__adobe.analytics.colorDepth` | A dimensão [Intensidade de cor](../../components/dimensions/color-depth.md). O campo abreviado `data.__adobe.analytics.c` também é aceito. |
| `data.__adobe.analytics.connectionType` | A dimensão [Tipo de conexão](../../components/dimensions/connection-type.md). O campo abreviado `data.__adobe.analytics.ct` também é aceito. |
| `data.__adobe.analytics.contextData` | [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md). |
| `data.__adobe.analytics.cookiesEnabled` | A dimensão [Suporte a cookies](../../components/dimensions/cookie-support.md). O campo abreviado `data.__adobe.analytics.k` também é aceito. |
| `data.__adobe.analytics.currencyCode` | A variável de implementação [`currencyCode`](../vars/config-vars/currencycode.md). O campo abreviado `data.__adobe.analytics.cc` também é aceito. |
| `data.__adobe.analytics.dynamicVariablePrefix` | A variável de implementação [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md). |
| `data.__adobe.analytics.eVar1` - `data.__adobe.analytics.eVar250` | Dimensões de [eVar](../../components/dimensions/evar.md). Os campos abreviados `data.__adobe.analytics.v1` - `data.__adobe.analytics.v250` também são aceitos. |
| `data.__adobe.analytics.events` | [Eventos personalizados](../../components/metrics/custom-events.md). Formate este campo de forma semelhante à variável de implementação [`events`](../vars/page-vars/events/events-overview.md). |
| `data.__adobe.analytics.javaEnabled` | A dimensão [Java habilitado](../../components/dimensions/java-enabled.md). O campo abreviado `data.__adobe.analytics.v` também é aceito. |
| `data.__adobe.analytics.latitude` | Ajuda a definir as dimensões do ciclo de vida móvel [Local](../../components/dimensions/lifecycle-dimensions.md). O campo abreviado `data.__adobe.analytics.lat` também é aceito. |
| `data.__adobe.analytics.linkName` | A dimensão [Link personalizado](../../components/dimensions/custom-link.md), [Link de download](../../components/dimensions/download-link.md) ou [Link de saída](../../components/dimensions/exit-link.md), dependendo do valor em `data.__adobe.analytics.linkType`. O campo abreviado `data.__adobe.analytics.pev2` também é aceito. |
| `data.__adobe.analytics.linkURL` | A variável de implementação [`linkURL`](../vars/config-vars/linkurl.md). O campo abreviado `data.__adobe.analytics.pev1` também é aceito. |
| `data.__adobe.analytics.linkType` | Determina o tipo de link clicado. Os valores válidos incluem `o` (Links personalizados), `d` (Links de download) e `e` (Links de saída). O campo abreviado `data.__adobe.analytics.pe` também é aceito. |
| `data.__adobe.analytics.list1` - `data.__adobe.analytics.list3` | Variáveis de implementação [`list`](/help/implement/vars/page-vars/list.md). Os campos abreviados `data.__adobe.analytics.l1` - `data.__adobe.analytics.list3` também são aceitos. |
| `data.__adobe.analytics.longitude` | Ajude a definir as dimensões do ciclo de vida móvel de [Local](../../components/dimensions/lifecycle-dimensions.md). O campo abreviado `data.__adobe.analytics.lon` também é aceito. |
| `data.__adobe.analytics.pageName` | A dimensão [Página](/help/components/dimensions/page.md). |
| `data.__adobe.analytics.pageURL` | A dimensão [URL da página](/help/components/dimensions/page-url.md). O campo abreviado `data.__adobe.analytics.g` também é aceito. |
| `data.__adobe.analytics.pageType` | A variável de implementação [`pageType`](../vars/page-vars/pagetype.md). |
| `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75` | Dimensões [prop](../../components/dimensions/prop.md). Os campos abreviados `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` também são aceitos. |
| `data.__adobe.analytics.purchaseID` | A variável de implementação [`purchaseID`](../vars/page-vars/purchaseid.md). |
| `data.__adobe.analytics.products` | A variável de implementação [`products`](../vars/page-vars/products.md), seguindo formatação semelhante. |
| `data.__adobe.analytics.referrer` | A dimensão [Referenciador](/help/components/dimensions/referrer.md). |
| `data.__adobe.analytics.resolution` | A dimensão [Resolução do monitor](../../components/dimensions/monitor-resolution.md). O campo abreviado `data.__adobe.analytics.s` também é aceito. |
| `data.__adobe.analytics.server` | A dimensão [Servidor](/help/components/dimensions/server.md). |
| `data.__adobe.analytics.transactionID` | A variável de implementação [`transactionID`](../vars/page-vars/transactionid.md). O campo abreviado `data.__adobe.analytics.xact` também é aceito. |
| `data.__adobe.analytics.zip` | A dimensão [Código postal](../../components/dimensions/zip-code.md). |

{style="table-layout:auto"}
