---
title: Métricas de rastreamento do estado do player dos serviços de mídia de transmissão
description: Métricas disponíveis ao habilitar o [!UICONTROL Rastreamento do estado do player] para um conjunto de relatórios.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---

# Métricas de rastreamento do estado do player dos serviços de mídia de transmissão

As métricas de rastreamento do estado do player dos serviços de mídia de transmissão fornecem funcionalidade de relatórios complementares para a coleta de dados por meio de bibliotecas de serviços de mídia de transmissão. O uso dessas métricas exige o **[!UICONTROL Complemento Adobe Analytics para mídia de streaming]**. Entre em contato com a equipe de conta da Adobe para obter mais detalhes.

Ao habilitar o **[!UICONTROL Rastreamento do estado do player]** em [Relatórios de mídia](/help/admin/tools/manage-rs/edit-settings/media-management.md), as seguintes métricas estão disponíveis:

| Nome da métrica | Descrição | Enviado com | Variável de dados de contexto | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Fluxos afetados pelas legendas ocultas]** | Acionado se pelo menos um estado de Legendas ocultas ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Contagens de legendas ocultas]** | O número de vezes que o vídeo entrou em um estado de Legendas ocultas. | Fechamento de mídia | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Duração total das legendas ocultas]** | A quantidade de tempo que o vídeo ficou no estado de Legendas ocultas, em segundos. | Fechamento de mídia | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Fluxos afetados pela tela cheia]** | Acionado se pelo menos um estado de Tela cheia ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Contagens de tela inteira]** | O número de vezes que o vídeo entrou em um estado de Tela cheia. | Fechamento de mídia | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Duração total da tela inteira]** | O tempo em que o vídeo ficou no estado Tela cheia, em segundos. | Fechamento de mídia | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Fluxos afetados pela função em foco]** | Acionado se pelo menos um estado Em foco ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Contagens da função Em foco]** | O número de vezes que o vídeo entrou em um estado Em foco. | Fechamento de mídia | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Duração total do foco]** | O tempo em que o vídeo ficou no estado Em foco, em segundos. | Fechamento de mídia | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Fluxos afetados pela função mudo]** | Acionado se pelo menos um estado da função Mudo ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Contagens da função Mudo]** | O número de vezes que o vídeo entrou em um estado de Mudo. | Fechamento de mídia | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Duração total da função Mudo]** | O tempo em que o vídeo ficou no estado Mudo, em segundos. | Fechamento de mídia | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Fluxos afetados pela imagem na imagem]** | Acionado se pelo menos um estado Picture In Picture ocorrer durante a sessão de reprodução. | Fechamento de mídia | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL Contagens de Picture in picture]** | O número de vezes que o vídeo entrou em um estado Picture In Picture. | Fechamento de mídia | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Duração total do Picture in picture]** | O tempo em que o vídeo ficou no estado Picture In Picture, em segundos. | Fechamento de mídia | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
