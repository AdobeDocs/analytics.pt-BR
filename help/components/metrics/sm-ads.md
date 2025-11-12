---
title: Métricas e serviços de mídia de transmissão
description: Métricas disponíveis ao habilitar o [!UICONTROL Anúncios de mídia] para um conjunto de relatórios.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Métricas e serviços de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita o [!UICONTROL Anúncios de Mídia] para um conjunto de relatórios. Consulte [Serviços e dimensões de mídia de streaming](../dimensions/sm-ads.md) para ver as dimensões disponíveis.*

Os serviços e métricas de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Anúncios de mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Anúncio concluído]** | Acionado quando um anúncio de vídeo é concluído. | Fechamento do anúncio | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL Início do anúncio]** | Acionado quando um anúncio de vídeo é iniciado. | Início do anúncio | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL Tempo gasto com anúncio]** | O tempo total gasto assistindo ao anúncio, em segundos. | Fechamento do anúncio | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL Tempo gasto com a mídia]** | Soma a duração de todos os eventos &#39;[!UICONTROL Play]&#39; (conteúdo principal e de anúncio), em segundos. | Fechamento de mídia | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
