---
title: Métricas principais dos serviços de mídia de transmissão
description: Métricas disponíveis ao habilitar o [!UICONTROL Media Core] para um conjunto de relatórios.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# Métricas principais dos serviços de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita o [!UICONTROL Media Core] para um conjunto de relatórios. Consulte [Dimensões principais dos serviços de mídia de streaming](../dimensions/sm-core.md) para ver as dimensões disponíveis.*

As métricas principais dos serviços de mídia de transmissão fornecem funcionalidade básica de relatórios para dados coletados por meio de bibliotecas de coleção de serviços de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Media Core]** em [Media Reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Média de público-alvo por minuto]** | A quantidade total de tempo gasto em um determinado conteúdo, dividida por sua duração para todas as suas sessões de reprodução.<br>`[Time spent] / [Media length]` | Fechamento de mídia | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL Conteúdo concluído]** | Acionado quando um conteúdo é concluído. Essa métrica não significa necessariamente que eles visualizaram todo o conteúdo; eles podem ter pulado para frente. Isso só significa que eles atingiram o fim do conteúdo. | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL Fluxos afetados pausados]** | Um booleano que é acionado se uma ou mais pausas ocorreram durante a reprodução do conteúdo. | Fechamento de mídia | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL Pausar eventos]** | A contagem de pausas que ocorreram durante uma sessão de reprodução. | Fechamento de mídia | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL Duração total da pausa]** | A duração total de todos os eventos de pausa, em segundos. | Fechamento de mídia | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL Início do conteúdo]** | O primeiro quadro da mídia é consumido. Se um usuário ignorar durante um anúncio ou buffering, esse evento não será acionado. | Fechamento de mídia | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL marcador de progresso de 10%]**<br>**[!UICONTROL marcador de progresso de 25%]**<br>**[!UICONTROL marcador de progresso de 50%]**<br>**[!UICONTROL marcador de progresso de 75%]**<br>**[!UICONTROL marcador de progresso de 95%]** | O indicador de reprodução passa o marcador indicado do conteúdo com base na duração. Cada marcador é contado apenas uma vez, mesmo se a busca for regressiva. Se a busca for para frente, os marcadores ignorados não são contados. | Fechamento de mídia | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL Resumo do conteúdo]** | Um booleano que é acionado quando o conteúdo é retomado após mais de 30 minutos de buffer, pausa ou período de paralisação. Também aciona se definido pelo reprodutor no objeto VideoInfo trackPlay. | Fechamento de mídia | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL Exibições do segmento de conteúdo]** | Um booleano que é acionado no primeiro quadro do segmento visualizado. | Fechamento de mídia | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL Início da mídia]** | Um booleano que é acionado quando a mídia é carregada inicialmente. Esse evento inclui anúncios, buffering e erros. | Início da mídia | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL Tempo gasto com o conteúdo]** | A duração total do evento para todos os eventos do tipo PLAY no conteúdo principal, em segundos. | Fechamento de mídia | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL Tempo de execução exclusivo]** | A quantidade total de tempo em que o conteúdo único é reproduzido, em segundos. Essa métrica exclui o tempo de reprodução ao exibir conteúdo repetido, como a busca de forma retroativa. | Fechamento de mídia | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
