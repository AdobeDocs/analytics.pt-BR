---
title: Métricas de rastreamento do estado do player de mídia de transmissão
description: Métricas disponíveis ao habilitar o [!UICONTROL Rastreamento do estado do player] para um conjunto de relatórios.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---

# Métricas de rastreamento do estado do player de mídia de transmissão

As métricas de rastreamento do estado do player de mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio de bibliotecas de coleção de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento de Coleção de Mídia de Streaming Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Ao habilitar o **[!UICONTROL Rastreamento do estado do player]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Fluxos afetados pelas legendas ocultas | Acionado se pelo menos um estado de Legendas ocultas ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.closedcaptioning.set` |
| Contagens de legendas ocultas | O número de vezes que o vídeo entrou em um estado de Legendas ocultas. | Fechamento de mídia | `a.media.states.closedcaptioning.count` |
| Duração total das legendas ocultas | A quantidade de tempo que o vídeo ficou no estado de Legendas ocultas, em segundos. | Fechamento de mídia | `a.media.states.closedcaptioning.time` |
| Fluxos afetados pela tela cheia | Acionado se pelo menos um estado de Tela cheia ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.fullscreen.set` |
| Contagens de tela inteira | O número de vezes que o vídeo entrou em um estado de Tela cheia. | Fechamento de mídia | `a.media.states.fullscreen.count` |
| Duração total da tela inteira | O tempo em que o vídeo ficou no estado Tela cheia, em segundos. | Fechamento de mídia | `a.media.states.fullscreen.time` |
| Fluxos afetados pela função em foco | Acionado se pelo menos um estado Em foco ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.infocus.set` |
| Contagens da função Em foco | O número de vezes que o vídeo entrou em um estado Em foco. | Fechamento de mídia | `a.media.states.infocus.count` |
| Duração total da função Em foco | O tempo em que o vídeo ficou no estado Em foco, em segundos. | Fechamento de mídia | `a.media.states.infocus.time` |
| Fluxos afetados pela função mudo | Acionado se pelo menos um estado da função Mudo ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.mute.set` |
| Contagens da função Mudo | O número de vezes que o vídeo entrou em um estado de Mudo. | Fechamento de mídia | `a.media.states.mute.count` |
| Duração total da função Mudo | O tempo em que o vídeo ficou no estado Mudo, em segundos. | Fechamento de mídia | `a.media.states.mute.time` |
| Fluxos afetados pelo picture in picture | Acionado se pelo menos um estado Picture In Picture ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.pictureinpicture.set` |
| Contagens de Picture in picture | O número de vezes que o vídeo entrou em um estado Picture In Picture. | Fechamento de mídia | `a.media.states.pictureinpicture.count` |
| Duração total do Picture in picture | O tempo em que o vídeo ficou no estado Picture In Picture, em segundos. | Fechamento de mídia | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
