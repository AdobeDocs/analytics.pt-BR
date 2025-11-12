---
title: Dimensões de qualidade dos serviços de mídia de transmissão
description: Dimensões disponíveis ao habilitar a [!UICONTROL Qualidade de mídia] para um conjunto de relatórios.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%

---

# Dimensões de qualidade dos serviços de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita a [!UICONTROL Qualidade de Mídia] para um conjunto de relatórios. Consulte [Métricas de qualidade de serviços de mídia de streaming](../metrics/sm-quality.md) para obter as métricas disponíveis.*

As dimensões de qualidade dos serviços de mídia de transmissão fornecem relatórios relacionados à qualidade do conteúdo que o visitante consome. O uso dessas dimensões requer o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita a **[!UICONTROL Qualidade de mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes dimensões estão disponíveis:

| Nome das dimensões | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Taxa média de bits]** | A taxa média de bits, em intervalos de bucket de 100 KBPS. É calculada como uma média ponderada de todos os valores de taxa de bits em relação à duração da reprodução em uma determinada sessão de reprodução. | Fechamento de mídia | `a.media.qoe.`<br>`bitrateAverageBucket` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrate`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateAverageBucket` |
| **[!UICONTROL Alterações na taxa de bits]** | O número de alterações na taxa de bits que ocorreram durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Eventos de buffer]** | O número de vezes que o reprodutor de mídia entrou em um estado de buffer durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferCount` |
| **[!UICONTROL Duração total do buffer]** | A quantidade total de tempo gasto com buffering, em segundos. | Fechamento de mídia | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferTime` |
| **[!UICONTROL Quadros soltos]** | O número total de quadros ignorados que ocorreram durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`droppedFrames` |
| **[!UICONTROL Erros]** | O número total de erros ocorridos durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`errorCount` |
| **[!UICONTROL IDs de erro externo]** | Todas as IDs de erro exclusivas de qualquer origem externa, como erros de CDN. Você deve fornecer os códigos de erro ou IDs desejados. Várias IDs de erro são permitidas. | Fechamento de mídia | `a.media.qoe.`<br>`externalErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`externalErrors` |
| **[!UICONTROL IDs de erro do Player SDK]** | Todas as IDs de erro exclusivas geradas pelo SDK do reprodutor de conteúdo. Você deve fornecer os códigos de erro ou IDs desejados. Várias IDs de erro são permitidas. | Fechamento de mídia | `a.media.qoe.`<br>`playerSdkErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`playerSdkErrors` |
| **[!UICONTROL Hora de início]** | O padrão desse valor é `0` se ele não for definido por meio do QoSObject. Defina o valor em milissegundos. O Analysis Workspace relata essa dimensão em segundos. | Início da mídia, Fechamento da mídia | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`timeToStart` |
