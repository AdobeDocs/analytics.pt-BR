---
title: Métricas de capítulo de mídia de streaming
description: Métricas disponíveis ao habilitar [!UICONTROL Capítulos de mídia] para um conjunto de relatórios.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%

---

# Métricas de capítulo de mídia de streaming

*Esta página descreve as métricas disponíveis quando você habilita os [!UICONTROL Capítulos de mídia] para um conjunto de relatórios. Consulte [dimensões do capítulo de mídia de streaming](../dimensions/sm-chapters.md) para ver as dimensões disponíveis.*

As métricas de capítulo de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio de bibliotecas de coleção de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de Coleção de Mídia de Streaming Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Ao habilitar **[!UICONTROL Capítulos da mídia]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes métricas estarão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Capítulo completo | Um booleano que é acionado quando um capítulo é concluído. | Fechamento do capítulo | `a.media.chapter.complete` |
| Início do capítulo | Um booleano que é acionado quando um capítulo é iniciado. | Início do capítulo | `a.media.chapter.view` |
| Tempo gasto com capítulo | O tempo gasto no capítulo, em segundos. | Fechamento do capítulo | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
