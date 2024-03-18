---
title: Dimensões do ciclo de vida móvel
description: Dimension com base em dados coletados usando o SDK móvel.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 26%

---

# Dimensões do ciclo de vida móvel

*Esses dados de referência da página são rastreados normalmente pelo SDK móvel da Adobe Experience Platform. Para obter informações sobre o dispositivo móvel usando o agente do usuário, consulte [Dimensões de pesquisa móvel](mobile-dimensions.md). Para métricas rastreadas com o SDK móvel, consulte [Métricas de ciclo de vida móvel](../metrics/lifecycle-metrics.md).*

| Nome da dimensão de ciclo de vida | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| [!UICONTROL Data da primeira inicialização] | | A ser definido |
| [!UICONTROL Nome do dispositivo (SDK)] | | `a.DeviceName` |
| [!UICONTROL Versão do sistema operacional (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolução (SDK)] | | `a.Resolution` |
| [!UICONTROL Origem da aquisição] | | `a.referrer.campaign.source` |
| [!UICONTROL ID do aplicativo] | | `a.AppID` |
| [!UICONTROL Meio de aquisição] | | `a.referrer.campaign.medium` |
| [!UICONTROL Termo de aquisição] | | `a.referrer.campaign.term` |
| [!UICONTROL Conteúdo de aquisição] | | `a.refferer.campaign.content` |
| [!UICONTROL Nome da aquisição] | | `a.referrer.campaign.name` |
| [!UICONTROL Localização (abaixo de 10 km)] | A latitude e a longitude do visitante, com precisão até a primeira casa decimal. Por exemplo, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Localização (abaixo de 100 m)] | A latitude e a longitude do visitante, com precisão da terceira casa decimal. Por exemplo, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL Localização (abaixo de 1 m)] | A latitude e a longitude do visitante, com precisão da quinta casa decimal. Por exemplo, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL Nome do ponto de interesse] | | `a.loc.poi` |
| [!UICONTROL Distância até o centro do ponto de interesse] | | `a.loc.dist` |
| [!UICONTROL Número de Lançamento] | | `a.Launches` |
| [!UICONTROL Dias desde a primeira utilização] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Nome da ação] | | A ser definido |
| [!UICONTROL Valor vitalício (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon principal] | | A ser definido |
| [!UICONTROL Beacon secundário] | | A ser definido |
| [!UICONTROL UUID do sinal] | | A ser definido |
| [!UICONTROL Proximidade do sinal] | | A ser definido |
| [!UICONTROL Dias desde a última utilização] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hora do dia (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Dia da semana (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL ID do ponto de interesse] | | A ser definido |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
