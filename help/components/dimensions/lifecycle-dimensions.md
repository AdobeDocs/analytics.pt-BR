---
title: Dimensões do ciclo de vida móvel
description: Dimensões com base em dados coletados usando o Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 23%

---

# Dimensões do ciclo de vida móvel

*Os dados de referência desta página são acompanhados com frequência pelo Adobe Experience Platform Mobile SDK. Para obter informações sobre o dispositivo móvel usando o agente de usuário, consulte [Dimensões de pesquisa móvel](mobile-dimensions.md). Para métricas rastreadas com o Mobile SDK, consulte [Métricas de ciclo de vida móvel](../metrics/lifecycle-metrics.md).*

| Nome da dimensão de ciclo de vida | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| [!UICONTROL Data da primeira inicialização] | | |
| [!UICONTROL Nome do dispositivo (SDK)] | | `a.DeviceName` |
| [!UICONTROL Versão do Sistema Operacional (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolução (SDK)] | | `a.Resolution` |
| [!UICONTROL Source de aquisição] | | `a.referrer.campaign.source` |
| [!UICONTROL Id Do Aplicativo] | | `a.AppID` |
| [!UICONTROL Medium de aquisição] | | `a.referrer.campaign.medium` |
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
| [!UICONTROL Nome da ação] | | |
| [!UICONTROL Valor vitalício (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon Principal] | | |
| [!UICONTROL Beacon secundário] | | |
| [!UICONTROL UUID do sinal] | | |
| [!UICONTROL Proximidade do sinal] | | |
| [!UICONTROL Dias desde a última utilização] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hora do dia (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Dia da Semana (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL ID do Ponto de Interesse] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
