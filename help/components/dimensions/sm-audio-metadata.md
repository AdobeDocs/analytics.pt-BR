---
title: Dimensões de metadados de áudio de mídia de transmissão
description: Dimensões disponíveis ao habilitar [!UICONTROL Metadados de áudio] para um conjunto de relatórios.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 8%

---

# Dimensões de metadados de áudio de mídia de transmissão

As dimensões e a mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio das bibliotecas de coleção de mídia de transmissão. O uso dessas dimensões requer a **[!UICONTROL Coleção de Mídia de Streaming de Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita os **[!UICONTROL Metadados de áudio]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Álbum | O nome do álbum. | Início da mídia, Fechamento da mídia | `a.media.album` |
| Artista | O nome do artista. | Início da mídia, Fechamento da mídia | `a.media.artist` |
| Autora | O nome do autor do audiobook. | Início da mídia, Fechamento da mídia | `a.media.author` |
| Rótulo | O nome da gravadora. | Início da mídia, Fechamento da mídia | `a.media.label` |
| Editor | O nome do publicador do conteúdo de áudio. | Início da mídia, Fechamento da mídia | `a.media.publisher` |
| Estação | O nome ou a ID da estação de rádio. | Início da mídia, Fechamento da mídia | `a.media.station` |

{style="table-layout:auto"}
