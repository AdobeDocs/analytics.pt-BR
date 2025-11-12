---
title: Serviços e dimensões de mídia de transmissão
description: Dimensões disponíveis ao habilitar o [!UICONTROL Anúncios de mídia] para um conjunto de relatórios.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# Serviços e dimensões de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita o [!UICONTROL Media Ads] para um conjunto de relatórios. Consulte [Métricas de anúncio de mídia de streaming](../metrics/sm-ads.md) para ver as métricas disponíveis.*

Os serviços e dimensões de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Anúncios de mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Anúncio]** | O identificador exclusivo do anúncio. | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL Nome do anúncio (variável)]** | O nome amigável do anúncio. Uma dimensão de classificação chamada &#39;[!UICONTROL Ad name]&#39; também está disponível, o que fornece uma finalidade semelhante. Essa dimensão e a classificação são tratadas como duas dimensões distintas. | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL Nome do player do anúncio]** | O nome do reprodutor que renderiza o anúncio. | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL Comprimento do anúncio (variável)]** | A duração do anúncio de vídeo, em segundos. | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL Pod de anúncio]** | O identificador exclusivo do pod de anúncios. | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL Anúncio na posição pod]** | A posição de índice do anúncio dentro do intervalo do anúncio principal (indexado por 0). | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL Anunciante]** | A empresa ou marca em destaque no anúncio. | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL ID da campanha]** | A ID da campanha publicitária | Início do anúncio, Fechamento do anúncio | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

Além das dimensões acima, o Adobe cria automaticamente as seguintes dimensões de classificação. Você deve fazer upload dos dados de classificação para visualizar relatórios que usam essas dimensões.

| Nome da classificação | Dimensão principal | Descrição |
| --- | --- | --- |
| **[!UICONTROL ID do ativo]** | [[!UICONTROL Conteúdo]](sm-core.md) | O identificador exclusivo do conteúdo do ativo de mídia. Os exemplos incluem o identificador de episódio da série de TV, o identificador de ativo do filme ou o identificador de evento em tempo real. Normalmente, essas IDs são derivadas de autoridades de metadados, como EIDR, TMS/Gracenote, Rovi ou de outros sistemas proprietários ou internos. |
| **[!UICONTROL Classificação de conteúdo]** | [[!UICONTROL Conteúdo]](sm-core.md) | A classificação conforme definido pelas diretrizes dos pais da TV. |
| **[!UICONTROL Primeira transmissão]** | [[!UICONTROL Conteúdo]](sm-core.md) | A data em que o conteúdo foi exibido na televisão pela primeira vez. Como essa dimensão de classificação é uma cadeia de caracteres, qualquer formato de data é permitido. A Adobe recomenda usar um formato de data consistente, como `YYYY-MM-DD`. |
| **[!UICONTROL Primeira data digital]** | [[!UICONTROL Conteúdo]](sm-core.md) | A data quando o conteúdo foi exibido em qualquer canal ou plataforma digital pela primeira vez. Como essa dimensão de classificação é uma cadeia de caracteres, qualquer formato de data é permitido. A Adobe recomenda usar um formato de data consistente, como `YYYY-MM-DD`. |
| **[!UICONTROL Comprimento do anúncio]** | [!UICONTROL Anúncio] | A duração do anúncio de vídeo, em segundos. |
| **[!UICONTROL Nome do anúncio]** | [!UICONTROL Anúncio] | O nome amigável do anúncio. É o equivalente de classificação de &#39;[!UICONTROL Nome do anúncio (variável)]&#39;. |
| **[!UICONTROL Creative ID]** | [!UICONTROL Anúncio] | A ID do criativo do anúncio. |
| **[!UICONTROL Nome do pod]** | [!UICONTROL Pod de anúncio] | O nome amigável do pod de anúncio. |
| **[!UICONTROL Posição do pod]** | [!UICONTROL Pod de anúncio] | O deslocamento do ad break no conteúdo, em segundos. |
