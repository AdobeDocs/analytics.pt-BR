---
title: Dimensões de anúncio de mídia de transmissão
description: Dimensões disponíveis ao habilitar o [!UICONTROL Anúncios de mídia] para um conjunto de relatórios.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 15%

---

# Dimensões de anúncio de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita o [!UICONTROL Media Ads] para um conjunto de relatórios. Consulte [Métricas de anúncio de mídia de streaming](../metrics/sm-ads.md) para ver as métricas disponíveis.*

As dimensões e a mídia de transmissão fornecem funcionalidade de relatórios complementar para a coleção de dados por meio das bibliotecas de coleção de mídia de transmissão. O uso dessas dimensões requer a **[!UICONTROL Coleção de Mídia de Streaming de Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Anúncios de mídia]** em [Relatórios de mídia](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Publicidade | O identificador exclusivo do anúncio. | Início do anúncio, Fechamento do anúncio | `a.media.ad.name` |
| Nome do anúncio (variável) | O nome amigável do anúncio. Uma dimensão de classificação chamada &quot;Nome do anúncio&quot; também está disponível, o que fornece uma finalidade semelhante. Essa dimensão e a classificação são tratadas como duas dimensões distintas. | Início do anúncio, Fechamento do anúncio | `a.media.ad.friendlyName` |
| Nome do player do anúncio | O nome do reprodutor que renderiza o anúncio. | Início do anúncio, Fechamento do anúncio | `a.media.ad.playerName` |
| Comprimento do anúncio (variável) | A duração do anúncio de vídeo, em segundos. | Início do anúncio, Fechamento do anúncio | `a.media.ad.length` |
| Pod de anúncio | O identificador exclusivo do pod de anúncios. | Início do anúncio, Fechamento do anúncio | `a.media.ad.pod` |
| Posição do anúncio no pod | A posição de índice do anúncio dentro do intervalo do anúncio principal (indexado por 0). | Início do anúncio, Fechamento do anúncio | `a.media.ad.podPosition` |
| Anunciante | A empresa ou marca em destaque no anúncio. | Início do anúncio, Fechamento do anúncio | `a.media.ad.advertiser` |
| ID da campanha | A ID da campanha publicitária | Início do anúncio, Fechamento do anúncio | `a.media.ad.campaign` |

{style="table-layout:auto"}

Além das dimensões acima, o Adobe cria automaticamente as seguintes dimensões de classificação. Você deve fazer upload dos dados de classificação para visualizar relatórios que usam essas dimensões.

| Nome da classificação | Dimensão principal | Descrição |
| --- | --- | --- |
| ID do ativo | [Conteúdo](sm-core.md) | O identificador exclusivo do conteúdo do ativo de mídia. Os exemplos incluem o identificador de episódio da série de TV, o identificador de ativo do filme ou o identificador de evento em tempo real. Normalmente, essas IDs são derivadas de autoridades de metadados, como EIDR, TMS/Gracenote, Rovi ou de outros sistemas proprietários ou internos. |
| Classificação de conteúdo | [Conteúdo](sm-core.md) | A classificação conforme definido pelas diretrizes dos pais da TV. |
| Data da primeira exibição | [Conteúdo](sm-core.md) | A data quando o conteúdo foi exibido na televisão pela primeira vez. Como essa dimensão de classificação é uma cadeia de caracteres, qualquer formato de data é permitido. A Adobe recomenda o uso de um formato de data consistente, como `YYYY-MM-DD`. |
| Primeira data digital | [Conteúdo](sm-core.md) | A data quando o conteúdo foi exibido em qualquer canal ou plataforma digital pela primeira vez. Como essa dimensão de classificação é uma cadeia de caracteres, qualquer formato de data é permitido. A Adobe recomenda o uso de um formato de data consistente, como `YYYY-MM-DD`. |
| Duração do anúncio | Publicidade | A duração do anúncio de vídeo, em segundos. |
| Nome do anúncio | Publicidade | O nome amigável do anúncio. É o equivalente de classificação de &quot;Nome do anúncio (variável)&quot;. |
| ID de criação | Publicidade | A ID do criativo do anúncio. |
| Nome do pod | Pod de anúncio | O nome amigável do pod de anúncio. |
| Posição do pod | Pod de anúncio | O deslocamento do ad break no conteúdo, em segundos. |

{style="table-layout:auto"}
