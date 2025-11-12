---
title: Dimensões de metadados de áudio dos serviços de mídia de transmissão
description: Dimensões disponíveis ao habilitar [!UICONTROL Metadados de áudio] para um conjunto de relatórios.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 4%

---

# Dimensões de metadados de áudio dos serviços de mídia de transmissão

Os serviços e dimensões de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita os **[!UICONTROL Metadados de áudio]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Álbum]** | O nome do álbum. | Início da mídia, Fechamento da mídia | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL Artista]** | O nome do artista. | Início da mídia, Fechamento da mídia | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL Autor]** | O nome do autor do audiobook. | Início da mídia, Fechamento da mídia | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL Rótulo]** | O nome da gravadora. | Início da mídia, Fechamento da mídia | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL Publicador]** | O nome do publicador do conteúdo de áudio. | Início da mídia, Fechamento da mídia | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL Estação]** | O nome ou a ID da estação de rádio. | Início da mídia, Fechamento da mídia | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
