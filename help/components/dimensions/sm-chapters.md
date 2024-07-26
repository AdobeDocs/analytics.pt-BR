---
title: Dimensões do capítulo de mídia de streaming
description: Dimensões disponíveis ao habilitar [!UICONTROL Capítulos de mídia] para um conjunto de relatórios.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 14%

---

# Dimensões do capítulo de mídia de streaming

*Esta página descreve as dimensões disponíveis quando você habilita os [!UICONTROL Capítulos de mídia] para um conjunto de relatórios. Consulte [métricas do capítulo Mídia de streaming](../metrics/sm-chapters.md) para ver as métricas disponíveis.*

As dimensões do capítulo Mídia de transmissão fornecem funcionalidade de relatório complementar para a coleção de dados por meio de bibliotecas de coleção de mídia de transmissão. O uso dessas dimensões requer o **[!UICONTROL Complemento de Coleção de Mídia de Streaming de Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Ao habilitar **[!UICONTROL Capítulos da mídia]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), a seguinte dimensão estará disponível:

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
