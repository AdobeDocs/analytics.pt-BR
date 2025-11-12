---
title: Dimensões de metadados de vídeo de serviços de mídia de transmissão
description: Dimensões disponíveis ao habilitar [!UICONTROL Metadados de vídeo] para um conjunto de relatórios.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 2%

---

# Dimensões de metadados de vídeo de serviços de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita os [!UICONTROL Metadados de vídeo] para um conjunto de relatórios. Consulte [Métricas de metadados de vídeo de serviços de mídia de streaming](../metrics/sm-video-metadata.md) para obter as métricas disponíveis.*

Os serviços e dimensões de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleta de dados por meio de bibliotecas de coleta de serviços de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita os **[!UICONTROL Metadados de vídeo]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Carregamentos de anúncio]** | O tipo de anúncio carregado. | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL Parte do dia]** | A hora do dia em que o conteúdo foi transmitido ou reproduzido. Qualquer valor de string é suportado. | Início da mídia, Fechamento da mídia | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL Episódio]** | O número do episódio. | Início da mídia, Fechamento da mídia | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL Tipo de feed de mídia]** | O tipo de feed. | Início da mídia, Fechamento da mídia | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL Gênero]** | O tipo ou agrupamento de conteúdo conforme definido pelo produtor do conteúdo. Essa dimensão suporta vários valores, delimitados por vírgulas. | Início da mídia, Fechamento da mídia | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | O MVPD conforme fornecido pela autenticação Adobe. | Início da mídia, Fechamento da mídia | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL Rede]** | O nome da rede ou do canal. | Início da mídia, Fechamento da mídia | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL Temporada]** | O número da temporada do programa. | Início da mídia, Fechamento da mídia | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL Programa]** | O nome do programa ou da série. | Início da mídia, Fechamento da mídia | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL Mostrar tipo]** | Um número inteiro que representa o tipo de conteúdo.<br>`0`: Episódio completo<br>`1`: Pré-visualização ou trailer<br>`2`: Clipe<br>`3`: Outro | Início da mídia, Fechamento da mídia | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

