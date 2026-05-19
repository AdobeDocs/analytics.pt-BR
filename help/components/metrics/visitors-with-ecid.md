---
title: Visitantes com Experience Cloud ID
description: O número de visitantes únicos que usam o serviço da Adobe Experience Cloud ID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: e6c28e30-8689-4bf4-8fa8-561343d308a9id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 76%

---

# Visitantes com Experience Cloud ID

A [métrica](overview.md) de &quot;Visitantes com Experience Cloud ID&quot; mostra o número de visitantes únicos identificados pela Adobe que usam o [serviço Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR). Essa métrica pode ser útil para comparar com a métrica [Visitantes únicos](unique-visitors.md) e garantir que a maioria dos visitantes do site usem o serviço de ID. Se uma grande parte dos visitantes não usar os cookies do serviço de ID, pode haver um problema na implementação.

>[!NOTE]
>
>Essa métrica é especialmente importante para a depuração se você usar vários serviços do CX Enterprise, como Adobe Target ou Adobe Audience Manager. Segmentos compartilhados entre produtos CX Enterprise não incluem visitantes sem uma Experience Cloud ID.

## Como essa métrica é calculada

Essa métrica tem como base a métrica [Visitantes únicos](unique-visitors.md), mas inclui somente pessoas identificadas utilizando a `mid` sequência de consulta (com base no cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=pt-BR)).

## Depurar a configuração da Experience Cloud ID

A métrica &quot;Visitantes com Experience Cloud ID&quot; pode ser útil para solucionar problemas de integrações do CX Enterprise ou para identificar áreas do site que não têm o serviço de ID implantado.

Arraste os &quot;Visitantes com Experience Cloud ID&quot; lado a lado com a dimensão “Visitantes únicos” para compará-los:

![Comparação de visitantes únicos](assets/metric-mcvid1.png)

Nesse exemplo, perceba que cada página tem o mesmo número de “Visitantes únicos” quanto de “Visitantes com Experience Cloud ID”. No entanto, o número total de “Visitantes únicos” é maior que o número total de Visitantes com Experience Cloud ID. Você pode criar uma [métrica calculada](../calculated-metrics/cm-overview.md) para descobrir quais páginas não estão configurando o serviço de ID. É possível utilizar a seguinte definição:

![Definição de métrica calculada](assets/metric-mcvid2.png)

Ao adicionar a métrica calculada ao relatório, é possível classificar os Relatórios de páginas para que as páginas com os maiores números de visitantes sem MCID apareçam:

![Páginas sem serviço de ID](assets/metric-mcvid3.png)

Observe que o item de dimensão “Visualizações rápidas de produto” não é implementado corretamente com o Serviço de identidade. Você pode trabalhar com as equipes apropriadas em sua organização para atualizar essas páginas o mais rápido possível. É possível criar um relatório semelhante a este com qualquer tipo de dimensão, como [Tipo de navegador](../dimensions/browser-type.md), [Seção do site](../dimensions/site-section.md) ou qualquer [eVar](../dimensions/evar.md).
