---
title: Métricas de ciclo de vida móvel
description: Métricas baseadas em dados coletados usando o SDK móvel.
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 10%
---
# Métricas de ciclo de vida móvel

>[!BEGINSHADEBOX]

*Esta página faz referência a dados rastreados comumente pelo Adobe Experience Platform Mobile SDK. Para dimensões rastreadas com o Mobile SDK, consulte [Dimensões do ciclo de vida móvel](../dimensions/lifecycle-dimensions.md). Para obter informações sobre o dispositivo móvel usando o agente de usuário, consulte [Dimensões de pesquisa móvel](../dimensions/mobile-dimensions.md).*

>[!ENDSHADEBOX]

| Nome da métrica de ciclo de vida | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| **[!UICONTROL Primeiras inicializações]** | O número de vezes que o aplicativo foi executado pela primeira vez após sua instalação ou reinstalação. | `a.InstallEvent` |
| **[!UICONTROL Atualizações]** | O número de vezes que o aplicativo foi executado pela primeira vez após uma atualização ou após a alteração de seu número de versão. | `a.UpgradeEvent` |
| **[!UICONTROL Inicializações]** | O número de vezes que o aplicativo foi executado, incluindo execuções após falhas e instalações. Uma inicialização também é contada quando o aplicativo é retomado do plano de fundo depois que o tempo limite da sessão do ciclo de vida é excedido. | `a.LaunchEvent` |
| **[!UICONTROL Falhas]** | O número de vezes que o aplicativo travou antes de ser fechado. A falha é relatada na próxima vez que o aplicativo for iniciado. | `a.CrashEvent` |
| **[!UICONTROL Duração total da sessão]** | O número total de segundos que as sessões do aplicativo duraram com base no tempo em que o aplicativo ficou aberto e no primeiro plano. Cada inicialização relata a duração da sessão anterior; essa métrica é a soma desses valores. | `a.PrevSessionLength` |
| **[!UICONTROL Tempo da ação total]** | O número total de segundos (tempo do relógio) entre o início e o término de uma ação cronometrada, entre sessões. Preenchido pelos métodos `trackTimedAction` no SDK herdado do Mobile Services (4.x). | `a.action.time.total` |
| **[!UICONTROL Tempo da ação no aplicativo]** | O número de segundos gastos no aplicativo entre o início e o fim de uma ação cronometrada, entre sessões. Preenchido pelos métodos `trackTimedAction` no SDK herdado do Mobile Services (4.x). | `a.action.time.inapp` |
| **[!UICONTROL Valor vitalício (evento)]** | O valor vitalício de um usuário, como compras, visualizações de anúncios, conclusões de vídeo ou compartilhamentos sociais. Preenchido pelo método `trackLifetimeValueIncrease` no SDK herdado do Mobile Services (4.x). | `a.ltv.amount` |

>[!NOTE]
>
>As métricas [!UICONTROL Tempo total de ação], [!UICONTROL Tempo de ação no aplicativo] e [!UICONTROL Valor de tempo de vida (evento)] são preenchidas por métodos no SDK herdado do Mobile Services (4.x), para o qual não há mais suporte. O Adobe Experience Platform Mobile SDK não preenche essas métricas automaticamente. Consulte [Migração da Adobe Mobile Library (v4) para o Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) para ver alternativas para ações cronometradas e rastreamento do valor vitalício.
