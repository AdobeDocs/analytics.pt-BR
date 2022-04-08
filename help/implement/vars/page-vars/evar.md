---
title: null
description: null
feature: Dimensions
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 









## 





## 



## Clique na propriedade desejada.

Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).

* Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
* Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].

Localize a seção [!UICONTROL eVars].

### Você pode definir uma eVar para um valor ou um elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

s.eVar1 e s.eVar250 no AppMeasurement e no editor de código personalizado do`post_evar`

1. Cada eVar é uma string que contém valores personalizados específicos para sua organização. O comprimento máximo delas é de 255 bytes; valores com mais de 255 bytes são truncados automaticamente quando enviados para a Adobe.
2. eVars de contador
3. Os valores de eVars normalmente contêm um valor de string. No entanto, você pode configurar eVars para que contenham um contador. Por exemplo, você gostaria de contar o número de pesquisas internas feitas antes de uma compra. Em vez de definir um valor de texto, você usaria a seguinte sintaxe:

Se mais que duas casas decimais forem fornecidas, o contador da eVar é arredondado para duas casas decimais. Um contador eVar não pode conter números negativos.

| [!IMPORTANT] | Primeiro, você deve configurar eVars como &quot;Contador&quot; no Admin Console antes de usar eVars de contador. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no Guia de administração. | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* The `visitor_id` column ties hits to the same visitor. In actual raw data, the concatenated values of `visid_high` and `visid_low` determine visitor ID.
* The `pagename` column populates the Pages dimension.
* The `evar` column determines the hits when eVar1 was explicitly set.
* The `post_evar1` carries the previous value, dependent on the variable&#39;s allocation and expiration set under report suite settings.
* The `event_list` column contains all metric data. For this example, `event1` is &#39;Searches&#39;, and the other events are standard shopping cart metrics. In actual raw data, `event_list` contains a comma-delimited set of numbers with a lookup table tying those numbers to a metric.

### Translating data collection to reporting

Tools in Adobe Analytics, such as Analysis Workspace, work off of this collected data. For example, if you pulled a report using eVar1 as the dimension and Orders as the metric, you would see a report similar to the following:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace pulls this report using the following logic:

* Look through all `event_list` values, and pick out all the hits with `purchase` in them.
* Out of those hits, display the `post_evar1` value.

### The importance of allocation and expiration

Since allocation and expiration determine what values persist, they are vital in getting the most value out of an analytics implementation. Adobe highly recommends that you discuss within your organization how multiple values for each eVar are handled (allocation) and when eVars stop persisting data (expiration).

* By default, an eVar uses last allocation. New values overwrite persisted values.
* By default, an eVar uses an expiration of visit. Once a visit ends, values stop copying over from row to row in the `post_evar` column.

You can change eVar allocation and expiration under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

## Value of eVars over props

Adobe recommends using eVars in most cases, supported through the following:

* eVars have a 255-byte limit in reports. Props have a 100-byte limit.
* Props by default do not persist beyond the hit they are set. eVars have custom expiration, allowing you to determine when an eVar no longer gets credit for a subsequent event. However, if you use [report time processing](/help/components/vrs/vrs-report-time-processing.md), both props and eVars can use a custom attribution model.
* Adobe supports up to 250 eVars, and only 75 props.

See [prop](prop.md) for more comparisons between props and eVars.
