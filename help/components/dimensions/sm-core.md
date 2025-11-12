---
title: Dimensões principais dos serviços de mídia de transmissão
description: Dimensões disponíveis ao habilitar o [!UICONTROL Media Core] para um conjunto de relatórios.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 7%

---

# Dimensões principais dos serviços de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita o [!UICONTROL Media Core] para um conjunto de relatórios. Consulte [Métricas principais dos serviços de mídia de streaming](../metrics/sm-core.md) para ver as métricas disponíveis.*

As dimensões principais dos serviços de mídia de transmissão fornecem funcionalidade básica de relatórios para dados coletados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Media Core]** em [Media Reporting](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Conteúdo]** | ID do conteúdo. | Início da mídia, Fechamento da mídia | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL Canal de conteúdo]** | A estação ou canal de distribuição onde o conteúdo é reproduzido. Qualquer valor de string é válido. | Início da mídia, Fechamento da mídia | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL Comprimento do conteúdo (variável)]** | O comprimento máximo (ou duração) do conteúdo consumido, em segundos. Esta dimensão é necessária para várias métricas, incluindo &#39;[!UICONTROL Audiência média por minuto]&#39;. Se essa dimensão não for definida, as métricas dependentes não estarão disponíveis.<br><br>Uma dimensão de classificação chamada &#39;[!UICONTROL Duração do vídeo]&#39; também está disponível, o que fornece uma finalidade semelhante. Essa dimensão e a classificação são tratadas como duas dimensões distintas. | Início da mídia, Fechamento da mídia | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL Nome do conteúdo (variável)]** | O nome amigável do conteúdo. Uma classificação chamada &#39;[!UICONTROL Nome do vídeo]&#39; também está disponível, o que fornece uma finalidade semelhante. Essa dimensão e a classificação são tratadas como duas dimensões distintas. | Início da mídia, Fechamento da mídia | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL Nome do player de conteúdo]** | O nome do reprodutor de conteúdo. | Início da mídia, Fechamento da mídia | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL Segmento de conteúdo]** | O intervalo que descreve a parte do conteúdo que foi exibida, em minutos. O segmento é calculado como os valores mín. e máx. do indicador de reprodução durante a sessão de reprodução. | Fechamento de mídia | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL Tipo de conteúdo]** | O tipo de conteúdo. Os valores válidos incluem `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` ou um valor personalizado. | Início da mídia, Fechamento da mídia | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL Caminho da mídia]** | O caminho que o visitante tomou para alcançar o conteúdo. | Início da mídia | `a.media.path` | |
| **[!UICONTROL Tipo de fluxo]** | O tipo de fluxo. Os valores válidos incluem `audio` e `video`. | Início da mídia, Fechamento da mídia | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

Além das dimensões acima, o Adobe cria automaticamente as seguintes dimensões de classificação. Você deve fazer upload dos dados de classificação para visualizar relatórios que usam essas dimensões.

| Nome da classificação | Dimensão principal | Descrição |
| --- | --- | --- |
| **[!UICONTROL Duração do vídeo]** | [!UICONTROL Conteúdo] | O comprimento máximo (ou duração) do conteúdo consumido, em segundos. As métricas que dependem da duração do conteúdo não podem usar essa classificação; você deve criar uma métrica calculada para obter métricas como &#39;[!UICONTROL Público-alvo médio por minuto]&#39; usando essa classificação. |
| **[!UICONTROL Nome do vídeo]** | [!UICONTROL Conteúdo] | O nome amigável do conteúdo. É o equivalente de classificação de &#39;[!UICONTROL Nome do conteúdo (variável)]&#39;. |
