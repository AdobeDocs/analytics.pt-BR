---
title: Dimensões de metadados de vídeo de mídia de transmissão
description: Dimensões disponíveis ao habilitar [!UICONTROL Metadados de vídeo] para um conjunto de relatórios.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Dimensões de metadados de vídeo de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita os [!UICONTROL Metadados de vídeo] para um conjunto de relatórios. Consulte [métricas de metadados de vídeo de streaming de mídia](../metrics/sm-video-metadata.md) para ver as métricas disponíveis.*

As dimensões e a mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio das bibliotecas de coleção de mídia de transmissão. O uso dessas dimensões requer a **[!UICONTROL Coleção de Mídia de Streaming de Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita os **[!UICONTROL Metadados de vídeo]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Carregamentos de anúncios | O tipo de anúncio carregado. | A ser determinado | `a.media.adLoad` |
| Faixa de horário | A hora do dia em que o conteúdo foi transmitido ou reproduzido. Qualquer valor de string é suportado. | Início da mídia, Fechamento da mídia | `a.media.dayPart` |
| Episódio | O número do episódio. | Início da mídia, Fechamento da mídia | `a.media.episode` |
| Tipo de feed de mídia | O tipo de feed. | Início da mídia, Fechamento da mídia | `a.media.feed` |
| Gênero | O tipo ou agrupamento de conteúdo conforme definido pelo produtor do conteúdo. Essa dimensão suporta vários valores, delimitados por vírgulas. | Início da mídia, Fechamento da mídia | `a.media.genre` |
| MVPD | O MVPD conforme fornecido pela autenticação Adobe. | Início da mídia, Fechamento da mídia | `a.media.pass.mvpd` |
| Rede | O nome da rede ou do canal | Início da mídia, Fechamento da mídia | `a.media.network` |
| Temporada | O número da temporada do programa. | Início da mídia, Fechamento da mídia | `a.media.season` |
| Programa | O nome do programa ou da série. | Início da mídia, Fechamento da mídia | `a.media.show` |
| Mostrar tipo | Um número inteiro que representa o tipo de conteúdo.<br>`0`: Episódio completo<br>`1`: Pré-visualização ou trailer<br>`2`: Clipe<br>`3`: Outro | Início da mídia, Fechamento da mídia | `a.media.type` |

{style="table-layout:auto"}
