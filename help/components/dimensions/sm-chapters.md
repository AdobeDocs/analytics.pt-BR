---
title: Dimensões do capítulo de mídia de streaming
description: Dimensões disponíveis ao habilitar [!UICONTROL Capítulos de mídia] para um conjunto de relatórios.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# Dimensões do capítulo de serviços de mídia de streaming

*Esta página descreve as dimensões disponíveis quando você habilita os [!UICONTROL Capítulos de mídia] para um conjunto de relatórios. Consulte [Métricas de capítulo de serviços de mídia de streaming](../metrics/sm-chapters.md) para ver as métricas disponíveis.*

As dimensões de capítulo dos serviços de mídia de transmissão fornecem funcionalidade de relatório complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Ao habilitar **[!UICONTROL Capítulos da mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), a seguinte dimensão estará disponível:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Capítulo]** | A ID do capítulo gerada automaticamente. | Fechamento do capítulo | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

Além das dimensões acima, o Adobe cria automaticamente as seguintes dimensões de classificação. Você deve fazer upload dos dados de classificação para visualizar relatórios que usam essas dimensões.

| Nome da classificação | Dimensão principal | Descrição |
| --- | --- | --- |
| **[!UICONTROL Originador]** | [[!UICONTROL Conteúdo]](sm-core.md) | O criador do conteúdo. |
| **[!UICONTROL Comprimento do capítulo]** | [!UICONTROL Capítulo] | A duração do capítulo, em segundos. |
| **[!UICONTROL Nome do capítulo]** | [!UICONTROL Capítulo] | O nome amigável do capítulo. |
| **[!UICONTROL Deslocamento de capítulo]** | [!UICONTROL Capítulo] | O deslocamento do capítulo dentro do conteúdo desde o início, em segundos. |
| **[!UICONTROL Posição do capítulo]** | [!UICONTROL Capítulo] | A posição de índice do capítulo no conteúdo. |
