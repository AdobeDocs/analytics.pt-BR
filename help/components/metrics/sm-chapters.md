---
title: Métricas de capítulo de serviços de mídia de streaming
description: Métricas disponíveis ao habilitar [!UICONTROL Capítulos de mídia] para um conjunto de relatórios.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 5%

---

# Métricas de capítulo de serviços de mídia de streaming

*Esta página descreve as métricas disponíveis quando você habilita os [!UICONTROL Capítulos de mídia] para um conjunto de relatórios. Consulte [Dimensões do capítulo de serviços de mídia de streaming](../dimensions/sm-chapters.md) para ver as dimensões disponíveis.*

As métricas de capítulo dos serviços de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio de bibliotecas de coleção de serviços de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de mídia do Adobe Analytics para streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Ao habilitar **[!UICONTROL Capítulos da mídia]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes métricas estarão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Capítulo completo | Um booleano que é acionado quando um capítulo é concluído. | Fechamento do capítulo | `a.media.chapter.complete` |
| Início do capítulo | Um booleano que é acionado quando um capítulo é iniciado. | Início do capítulo | `a.media.chapter.view` |
| Tempo gasto com capítulo | O tempo gasto no capítulo, em segundos. | Fechamento do capítulo | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
