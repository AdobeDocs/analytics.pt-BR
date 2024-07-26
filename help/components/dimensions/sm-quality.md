---
title: Dimensões de qualidade de streaming de mídia
description: Dimensões disponíveis ao habilitar a [!UICONTROL Qualidade de mídia] para um conjunto de relatórios.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# Dimensões de qualidade de streaming de mídia

*Esta página descreve as dimensões disponíveis quando você habilita a [!UICONTROL Qualidade de Mídia] para um conjunto de relatórios. Consulte [Métricas de qualidade de streaming de mídia](../metrics/sm-quality.md) para ver as métricas disponíveis.*

As dimensões de qualidade da mídia de transmissão fornecem relatórios relacionados à qualidade do conteúdo que o visitante consome. O uso dessas dimensões requer o [!UICONTROL complemento de Coleção de Mídia de Streaming de Adobe]. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita a **[!UICONTROL Qualidade de mídia]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes dimensões estão disponíveis:

| nome do Dimension | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Taxa média de bits | A taxa média de bits, em intervalos de bucket de 100 KBPS. É calculada como uma média ponderada de todos os valores de taxa de bits em relação à duração da reprodução em uma determinada sessão de reprodução. | Fechamento de mídia | `a.media.qoe.bitrateAverageBucket` |
| Alterações na taxa de bits | O número de alterações na taxa de bits que ocorreram durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.bitrateChangeCount` |
| Eventos de buffer | O número de vezes que o reprodutor de mídia entrou em um estado de buffer durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.bufferCount` |
| Duração total do buffer | A quantidade total de tempo gasto com buffering, em segundos. | Fechamento de mídia | `a.media.qoe.bufferTime` |
| Quadros soltos | O número total de quadros ignorados que ocorreram durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.droppedFrameCount` |
| Erros | O número total de erros ocorridos durante uma sessão de reprodução. | Fechamento de mídia | `a.media.qoe.errorCount` |
| IDs de erro externo | Todas as IDs de erro exclusivas de qualquer origem externa, como erros de CDN. Você deve fornecer os códigos de erro ou IDs desejados. Várias IDs de erro são permitidas. | Fechamento de mídia | `a.media.qoe.externalErrors` |
| IDs de erro do Player SDK | Todas as IDs de erro exclusivas geradas pelo SDK do reprodutor de conteúdo. Você deve fornecer os códigos de erro ou IDs desejados. Várias IDs de erro são permitidas. | Fechamento de mídia | `a.media.qoe.playerSdkErrors` |
| Hora de início | O padrão desse valor é `0` se ele não for definido por meio do QoSObject. Defina o valor em milissegundos. O Analysis Workspace relata essa dimensão em segundos. | Início da mídia, Fechamento da mídia | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
