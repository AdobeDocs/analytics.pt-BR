---
title: Visitantes com Experience Cloud ID
description: O número de visitantes únicos que usam uma ECID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: e6c28e30-8689-4bf4-8fa8-561343d308a9
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 384
ht-degree: 25%

---

# Visitantes com Experience Cloud ID

A [métrica](overview.md) de &#39;[!UICONTROL Visitantes com Experience Cloud ID]&#39; mostra o número de visitantes únicos identificados pela Adobe com uma ECID (usando o [Serviço de ID do Visitante](https://experienceleague.adobe.com/pt-br/docs/id-service/using/home) ou o [Serviço de Identidade da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/home)). Essa métrica pode ser útil para comparar com a métrica [Visitantes únicos](unique-visitors.md) e garantir que a maioria dos visitantes do site usem uma ECID. Se uma grande parte dos visitantes não usar esse identificador, ele pode indicar um problema na implementação.

>[!NOTE]
>
>Essa métrica é especialmente importante para a depuração se você usar vários serviços do CX Enterprise, como Adobe Target ou Adobe Audience Manager. Segmentos compartilhados entre produtos CX Enterprise não incluem visitantes sem uma ECID.

## Como essa métrica é calculada

Essa métrica tem como base a métrica [Visitantes únicos](unique-visitors.md), mas inclui somente pessoas identificadas utilizando a `mid` sequência de consulta (com base no cookie [`s_ecid`](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/cookies/analytics)).

## Depurar a configuração da ECID

A métrica &#39;[!UICONTROL Visitantes com Experience Cloud ID]&#39; pode ser útil para solucionar problemas de integrações do CX Enterprise ou para identificar áreas do site que não têm o Serviço de ID de Visitante ou o Serviço de Identidade da Experience Platform implantado.

Arraste os &#39;[!UICONTROL Visitantes com Experience Cloud ID]&#39; lado a lado com Visitantes únicos para compará-los:

![Comparação de visitantes únicos](assets/metric-mcvid1.png)

Neste exemplo, observe que cada página tem o mesmo número de &#39;[!UICONTROL Visitantes únicos]&#39; que &#39;[!UICONTROL Visitantes com Experience Cloud ID]&#39;. No entanto, o número total de &#39;[!UICONTROL Visitantes únicos]&#39; é maior que o número total de &#39;[!UICONTROL Visitantes com Experience Cloud ID]&#39;. Você pode criar uma [métrica calculada](../calculated-metrics/cm-overview.md) para descobrir quais páginas não estão usando uma ECID usando a seguinte definição:

![Definição de métrica calculada](assets/metric-mcvid2.png)

Ao adicionar a métrica calculada ao relatório, você pode classificar os relatórios de Páginas para que as páginas com o maior número de visitantes sem uma ECID apareçam:

![Páginas sem ECID](assets/metric-mcvid3.png)

Observe que o item de dimensão &quot;Visualizações rápidas de produto&quot; não é implementado corretamente com uma ECID. Você pode trabalhar com as equipes apropriadas em sua organização para atualizar essas páginas o mais rápido possível. É possível criar um relatório semelhante a este com qualquer tipo de dimensão, como [Tipo de navegador](../dimensions/browser-type.md), [Seção do site](../dimensions/site-section.md) ou qualquer [eVar](../dimensions/evar.md).
