---
title: Visitantes com Experience Cloud ID
description: O número de visitantes únicos que usam o serviço da Adobe Experience Cloud ID.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 19%

---


# Visitantes com Experience Cloud ID

A métrica &quot;Visitante com ID do Experience Cloud mostra o número de visitantes únicos identificados pela Adobe usando o serviço [de ID do](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html)Experience Cloud. Essa dimensão é útil para comparar com a métrica visitantes [](unique-visitors.md) únicos para garantir que a maioria dos visitantes do site use o serviço de ID. Se uma grande parte dos visitantes não usar os cookies do serviço de ID, isso pode indicar um problema na implementação.

>[!NOTE]
>
>Essa métrica é especialmente importante para a depuração se você usar vários serviços de Experience Cloud, como Adobe Target ou Adobe Audience Manager. Segmentos compartilhados em produtos Experience Cloud não incluem visitantes sem uma ID de Experience Cloud.

## Como essa métrica é calculada

Essa métrica é baseada na métrica visitantes [](unique-visitors.md) únicos, exceto que inclui somente indivíduos identificados usando a string do `mid` query (com base no [`s_ecid`](https://docs.adobe.com/content/help/pt-BR/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

## Depurar a configuração da ID do Experience Cloud

A métrica &quot;Visitante com ID do Experience Cloud&quot; pode ser útil na solução de problemas de integrações de Experience Cloud ou na identificação de áreas do site que não têm o serviço de ID implantado.

Arraste os &quot;Visitantes com Experience Cloud ID&quot; lado a lado com visitantes únicos para compará-los:

![Comparação de visitantes únicos](assets/metric-mcvid1.png)

Neste exemplo, observe que cada página tem o mesmo número de &quot;Visitantes únicos&quot; que &quot;Visitantes com uma ID de Experience Cloud&quot;. No entanto, o número total de Visitantes únicos é maior que o número total de Visitantes com Experience Cloud ID. Você pode criar uma métrica [](../c-calcmetrics/cm-overview.md) calculada para descobrir quais páginas não estão configurando o serviço de ID. Você pode usar a seguinte definição:

![Definição de métrica calculada](assets/metric-mcvid2.png)

Ao adicionar a métrica calculada ao relatório, é possível classificar o relatórios de Páginas, de forma que as páginas com os maiores números de visitantes sem MCID apareçam:

![Páginas sem serviço de ID](assets/metric-mcvid3.png)

Observe que o item de dimensão &quot;Visualizações rápidas de produto&quot; não é implementado corretamente com o Serviço de identidade. Você pode trabalhar com equipes apropriadas em sua organização para atualizar essas páginas o mais rápido possível. Você pode criar um relatório semelhante com qualquer tipo de dimensão, como tipo [de](../dimensions/browser-type.md)Navegador, seção [](../dimensions/site-section.md)Site ou qualquer [eVar](../dimensions/evar.md).
