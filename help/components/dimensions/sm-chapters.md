---
title: Dimensões do capítulo de mídia de streaming
description: Dimensões disponíveis ao habilitar [!UICONTROL Capítulos de mídia] para um conjunto de relatórios.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 13%

---

# Dimensões do capítulo de serviços de mídia de streaming

*Esta página descreve as dimensões disponíveis quando você habilita os [!UICONTROL Capítulos de mídia] para um conjunto de relatórios. Consulte [Métricas de capítulo de serviços de mídia de streaming](../metrics/sm-chapters.md) para ver as métricas disponíveis.*

As dimensões de capítulo dos serviços de mídia de transmissão fornecem funcionalidade de relatório complementar para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento de mídia do Adobe Analytics para streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Ao habilitar **[!UICONTROL Capítulos da mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), a seguinte dimensão estará disponível:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Capítulo | A ID do capítulo gerada automaticamente. | Fechamento do capítulo | `a.media.chapter.name` |

{style="table-layout:auto"}

Além das dimensões acima, o Adobe cria automaticamente as seguintes dimensões de classificação. Você deve fazer upload dos dados de classificação para visualizar relatórios que usam essas dimensões.

| Nome da classificação | Dimensão principal | Descrição |
| --- | --- | --- |
| Originador | [Conteúdo](sm-core.md) | O criador do conteúdo. |
| Extensão do capítulo | Capítulo | O comprimento do capítulo, em segundos. |
| Nome do capítulo | Capítulo | O nome amigável do capítulo. |
| Deslocamento de capítulo | Capítulo | O deslocamento do capítulo dentro do conteúdo desde o início, em segundos. |
| Posição do capítulo | Capítulo | A posição de índice do capítulo no conteúdo. |

{style="table-layout:auto"}
