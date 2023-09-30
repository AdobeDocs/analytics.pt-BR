---
title: Dimensões do ciclo de vida móvel
description: Dimension com base em dados coletados usando o SDK móvel.
feature: Dimensions
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 55%

---

# Dimensões do ciclo de vida móvel

*Esses dados de referência da página são rastreados normalmente pelo SDK móvel da Adobe Experience Platform. Para obter informações sobre o dispositivo móvel usando o agente do usuário, consulte [Dimensões de pesquisa móvel](mobile-dimensions.md). Para métricas rastreadas com o SDK móvel, consulte [Métricas de ciclo de vida móvel](../metrics/lifecycle-metrics.md).*

| Nome da dimensão de ciclo de vida | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| [!UICONTROL Data da primeira inicialização] | | A definir (esta é a data de instalação?) |
| [!UICONTROL Nome do dispositivo (SDK)] | | `a.DeviceName` |
| [!UICONTROL Versão do sistema operacional (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolução (SDK)] | | `a.Resolution` |
| [!UICONTROL Fonte da aquisição] | | `a.referrer.campaign.source` |
| [!UICONTROL ID do aplicativo] | | `a.AppID` |
| [!UICONTROL Meio da aquisição] | | `a.referrer.campaign.medium` |
| [!UICONTROL Termo de aquisição] | | `a.referrer.campaign.term` |
| [!UICONTROL Conteúdo da aquisição] | | `a.refferer.campaign.content` |
| [!UICONTROL Nome da aquisição] | | `a.referrer.campaign.name` |
| [!UICONTROL Localização (abaixo de 10 km)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Localização (abaixo de 100 m)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL Localização (abaixo de 1 m)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL Nome do ponto de interesse] | | `a.loc.poi` |
| [!UICONTROL Distância até o centro do ponto de interesse] | | `a.loc.dist` |
| [!UICONTROL Número de lançamento] | | `a.Launches` |
| [!UICONTROL Dias desde a primeira utilização] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Nome da ação] | | A ser definido |
| [!UICONTROL Valor da duração (evar)] | | `a.ltv.amount` |
| [!UICONTROL Maior sinal] | | A ser definido |
| [!UICONTROL Menor sinal] | | A ser definido |
| [!UICONTROL UUID do sinal] | | A ser definido |
| [!UICONTROL Proximidade do sinal] | | A ser definido |
| [!UICONTROL Dias desde a última utilização] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Horário do dia (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Dia da semana (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL ID do ponto de interesse] | | A ser definido |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
