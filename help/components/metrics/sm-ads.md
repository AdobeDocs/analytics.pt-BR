---
title: Métricas de anúncio de mídia de transmissão
description: Métricas disponíveis ao habilitar o [!UICONTROL Anúncios de mídia] para um conjunto de relatórios.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---

# Métricas de anúncio de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita o [!UICONTROL Anúncios de Mídia] para um conjunto de relatórios. Consulte [dimensões de anúncios de mídia de streaming](../dimensions/sm-ads.md) para ver as dimensões disponíveis.*

As métricas de anúncios de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio de bibliotecas de coleção de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de Coleção de Mídia de Streaming Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Anúncios de mídia]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Anúncio completo | Acionado quando um anúncio de vídeo é concluído. | Fechamento do anúncio | `a.media.ad.complete` |
| Anúncio iniciado | Acionado quando um anúncio de vídeo é iniciado. | Início do anúncio | `a.media.ad.view` |
| Tempo gasto com o anúncio | O tempo total gasto assistindo ao anúncio, em segundos. | Fechamento do anúncio | `a.media.ad.timePlayed` |
| Tempo gasto com a mídia | Soma a duração de todos os eventos PLAY (conteúdo principal e de publicidade), em segundos. | Fechamento de mídia | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
