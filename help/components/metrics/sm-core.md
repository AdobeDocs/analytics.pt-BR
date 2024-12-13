---
title: Métricas principais de mídia de transmissão
description: Métricas disponíveis ao habilitar o [!UICONTROL Media Core] para um conjunto de relatórios.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---

# Métricas principais de mídia de transmissão

*Esta página descreve as métricas disponíveis quando você habilita o [!UICONTROL Media Core] para um conjunto de relatórios. Consulte [dimensões principais de mídia de streaming](../dimensions/sm-core.md) para ver as dimensões disponíveis.*

As métricas principais de mídia de transmissão fornecem a funcionalidade básica de relatórios para dados coletados por meio de bibliotecas de coleção de mídia de transmissão. O uso destas métricas requer a **[!UICONTROL Coleção de Mídia de Streaming de Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Media Core]** em [Media Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Público médio a cada minuto | A quantidade total de tempo gasto em um determinado conteúdo, dividida por sua duração para todas as suas sessões de reprodução.<br>`[Time spent] / [Media length]` | Fechamento de mídia | `a.media.averageMinuteAudience` |
| Conteúdo completo | Acionado quando um conteúdo é concluído. Essa métrica não significa necessariamente que eles visualizaram todo o conteúdo; eles podem ter pulado para frente. Isso só significa que eles atingiram o fim do conteúdo. | `a.media.complete` |
| Fluxos afetados pausados | Um booleano que é acionado se uma ou mais pausas ocorreram durante a reprodução do conteúdo. | Fechamento de mídia | `a.media.pause` |
| Pausar eventos | A contagem de pausas que ocorreram durante uma sessão de reprodução. | Fechamento de mídia | `a.media.pauseCount` |
| Duração total da pausa | A duração total de todos os eventos de pausa, em segundos. | Fechamento de mídia | `a.media.pauseTime` |
| Início do conteúdo | O primeiro quadro da mídia é consumido. Se um usuário ignorar durante um anúncio ou buffering, esse evento não será acionado. | Fechamento de mídia | `a.media.play` |
| Marcador de progresso em 10% | O indicador de reprodução passa o marcador de 10% do conteúdo com base na duração. Esse marcador é contado apenas uma vez, mesmo se a busca for regressiva. Se a busca for para frente, os marcadores ignorados não são contados. | Fechamento de mídia | `a.media.progress10` |
| Marcador de progresso em 25% | O indicador de reprodução passa o marcador de 25% do conteúdo com base na duração. Esse marcador é contado apenas uma vez, mesmo se a busca for regressiva. Se a busca for para frente, os marcadores ignorados não são contados. | Fechamento de mídia | `a.media.progress25` |
| Marcador de progresso em 50% | O indicador de reprodução passa o marcador de 50% do conteúdo com base na duração. Esse marcador é contado apenas uma vez, mesmo se a busca for regressiva. Se a busca for para frente, os marcadores ignorados não são contados. | Fechamento de mídia | `a.media.progress50` |
| Marcador de progresso em 75% | O indicador de reprodução passa o marcador de 75% do conteúdo com base na duração. Esse marcador é contado apenas uma vez, mesmo se a busca for regressiva. Se a busca for para frente, os marcadores ignorados não são contados. | Fechamento de mídia | `a.media.progress75` |
| Marcador de progresso em 95% | O indicador de reprodução passa o marcador de 95% do conteúdo com base na duração. Esse marcador é contado apenas uma vez, mesmo se a busca for regressiva. Se a busca for para frente, os marcadores ignorados não são contados. | Fechamento de mídia | `a.media.progress95` |
| Resumo de conteúdo | Um booleano que é acionado quando o conteúdo é retomado após mais de 30 minutos de buffer, pausa ou período de paralisação. Também aciona se definido pelo reprodutor no objeto VideoInfo trackPlay. | Fechamento de mídia | `a.media.resume` |
| Visualizações do segmento de conteúdo | Um booleano que é acionado no primeiro quadro do segmento visualizado. | Fechamento de mídia | `a.media.segmentView` |
| Início da mídia | Um booleano que é acionado quando a mídia é carregada inicialmente. Esse evento inclui anúncios, buffering e erros. | Início da mídia | `a.media.view` |
| Tempo gasto com o conteúdo | A duração total do evento para todos os eventos do tipo PLAY no conteúdo principal, em segundos. | Fechamento de mídia | `a.media.timePlayed` |
| Tempo de reprodução exclusivo | A quantidade total de tempo em que o conteúdo único é reproduzido, em segundos. Essa métrica exclui o tempo de reprodução ao exibir conteúdo repetido, como a busca de forma retroativa. | Fechamento de mídia | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}
