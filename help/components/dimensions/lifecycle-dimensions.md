---
title: Dimensões do ciclo de vida móvel
description: Dimensões com base em dados coletados usando o Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 8%
---
# Dimensões do ciclo de vida móvel

>[!BEGINSHADEBOX]

*Esta página faz referência a dados rastreados comumente pelo Adobe Experience Platform Mobile SDK. Para obter informações sobre o dispositivo móvel usando o agente de usuário, consulte [Dimensões de pesquisa móvel](mobile-dimensions.md). Para métricas rastreadas com o Mobile SDK, consulte [Métricas de ciclo de vida móvel](../metrics/lifecycle-metrics.md).*

>[!ENDSHADEBOX]

| Nome da dimensão de ciclo de vida | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| **[!UICONTROL Data da primeira inicialização]** | A data em que o aplicativo foi executado pela primeira vez após ter sido instalado ou reinstalado, no formato `M/d/yyyy`. | `a.InstallDate` |
| **[!UICONTROL Nome do dispositivo (SDK)]** | O nome do dispositivo que o SDK coleta. | `a.DeviceName` |
| **[!UICONTROL Versão do Sistema Operacional (SDK)]** | O nome e a versão do sistema operacional que o SDK coleta. | `a.OSVersion` |
| **[!UICONTROL Resolução (SDK)]** | A resolução da tela do dispositivo em pixels, como largura x altura. | `a.Resolution` |
| **[!UICONTROL Source de aquisição]** | O referenciador original de uma campanha de aquisição de aplicativo, como um boletim informativo ou uma rede social. | `a.referrer.campaign.source` |
| **[!UICONTROL Id Do Aplicativo]** | O nome e a versão do aplicativo, no formato `AppName BundleVersion (app version code)`. Por exemplo, `MyAppName 1.1(1)`. | `a.AppID` |
| **[!UICONTROL Medium de aquisição]** | O meio de marketing para uma campanha de aquisição de aplicativo, como um banner ou email. | `a.referrer.campaign.medium` |
| **[!UICONTROL Termo de aquisição]** | Palavras-chave pagas ou outros termos associados a uma campanha de aquisição de aplicativo. | `a.referrer.campaign.term` |
| **[!UICONTROL Conteúdo de aquisição]** | O nome ou a ID do conteúdo que exibiu o link de aquisição do aplicativo. | `a.referrer.campaign.content` |
| **[!UICONTROL Nome da aquisição]** | O nome da campanha de aquisição de aplicativo. | `a.referrer.campaign.name` |
| **[!UICONTROL Localização (abaixo de 10 km)]** | A latitude e a longitude do visitante, com precisão até a primeira casa decimal. Por exemplo, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL Localização (abaixo de 100 m)]** | A latitude e a longitude do visitante, com precisão da terceira casa decimal. Por exemplo, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL Localização (abaixo de 1 m)]** | A latitude e a longitude do visitante, com precisão da quinta casa decimal. Por exemplo, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL Nome do ponto de interesse]** | O nome do ponto de interesse (POI) em que o dispositivo está. Quando você usa a [extensão do Places](https://developer.adobe.com/client-sdks/solution/places/), esse valor é o nome da região do Places. | `a.loc.poi` |
| **[!UICONTROL Distância até o centro do ponto de interesse]** | A distância entre o dispositivo e o centro do ponto de interesse em que o dispositivo está. | `a.loc.dist` |
| **[!UICONTROL Número de Lançamento]** | O número de vezes que o aplicativo foi iniciado ou trazido para o plano de fundo. | `a.Launches` |
| **[!UICONTROL Dias desde a primeira utilização]** | O número de dias desde a primeira execução do aplicativo. | `a.DaysSinceFirstUse` |
| **[!UICONTROL Nome da ação]** | O nome da ação enviada em uma chamada `trackAction`. | `a.action` |
| **[!UICONTROL Valor vitalício (evar)]** | O valor vitalício de um usuário, como compras, visualizações de anúncios, conclusões de vídeo ou compartilhamentos sociais. | `a.ltv.amount` |
| **[!UICONTROL Beacon Principal]** | A ID principal do beacon ao qual o dispositivo está próximo. | `a.beacon.major` |
| **[!UICONTROL Beacon secundário]** | A ID secundária do beacon ao qual o dispositivo está próximo. | `a.beacon.minor` |
| **[!UICONTROL UUID do sinal]** | A UUID do beacon ao qual o dispositivo está próximo. | `a.beacon.uuid` |
| **[!UICONTROL Proximidade do sinal]** | A proximidade do dispositivo com o sinal: `0` (desconhecido), `1` (imediato), `2` (próximo) ou `3` (distante). | `a.beacon.prox` |
| **[!UICONTROL Dias desde a última utilização]** | O número de dias desde a última utilização do aplicativo. | `a.DaysSinceLastUse` |
| **[!UICONTROL Hora do dia (SDK)]** | A hora em que o aplicativo foi iniciado, no formato de 24 horas. Útil para hora do visitante para determinar horas de pico de uso. | `a.HourOfDay` |
| **[!UICONTROL Dia da Semana (SDK)]** | O dia da semana em que o aplicativo foi iniciado. | `a.DayOfWeek` |
| **[!UICONTROL ID do Ponto de Interesse]** | A ID do ponto de interesse em que o dispositivo está. Quando você usa a [extensão do Places](https://developer.adobe.com/client-sdks/solution/places/), esse valor é a ID da região do Places. | `a.loc.poi.id` |

>[!NOTE]
>
>Algumas dessas dimensões são preenchidas por métodos no SDK herdado do Mobile Services (4.x), que não é mais compatível. O Adobe Experience Platform Mobile SDK não os preenche automaticamente:
>
>* **Dimensões de aquisição** ([!UICONTROL Source de Aquisição], [!UICONTROL Medium], [!UICONTROL Termo], [!UICONTROL Conteúdo] e [!UICONTROL Nome]): preenchido pela Aquisição de Aplicativos Móveis, para a qual o SDK Móvel [não oferece suporte](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/).
>* **[!UICONTROL Localização] dimensões e [!UICONTROL Distância até o Centro do Ponto de Interesse]**: preenchida pelo método 4.x `trackLocation`. O Mobile SDK substitui este método pela [extensão do Places](https://developer.adobe.com/client-sdks/solution/places/), que preenche o [!UICONTROL Nome do Ponto de Interesse] e a [!UICONTROL ID do Ponto de Interesse].
>* **[!UICONTROL Valor vitalício (evar)]**: preenchido pelo método 4.x `trackLifetimeValueIncrease`.
>* **Dimensões do sinal** ([!UICONTROL Beacon Principal], [!UICONTROL Menor], [!UICONTROL UUID] e [!UICONTROL Proximidade]): preenchido pelo método 4.x `trackBeacon`. Para enviar dados de beacon com o Mobile SDK, consulte [Rastreamento de beacons](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/).
>
>Consulte [Migração da Adobe Mobile Library (v4) para o Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) para obter mais informações.
