---
title: Dimensões de qualidade dos serviços de mídia de transmissão
description: Dimensões disponíveis ao habilitar a [!UICONTROL Qualidade de mídia] para um conjunto de relatórios.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Dimensões de qualidade dos serviços de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita a [!UICONTROL Qualidade de Mídia] para um conjunto de relatórios. Consulte [Métricas de qualidade de serviços de mídia de streaming](../metrics/sm-quality.md) para obter as métricas disponíveis.*

As dimensões de qualidade dos serviços de mídia de transmissão fornecem relatórios relacionados à qualidade do conteúdo que o visitante consome. O uso dessas dimensões requer o [!UICONTROL Complemento de mídia do Adobe Analytics para streaming]. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Quando você habilita a **[!UICONTROL Qualidade de mídia]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes dimensões estão disponíveis:

| Nome das dimensões | Descrição | Enviado com | Variável de dados de contexto |
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
