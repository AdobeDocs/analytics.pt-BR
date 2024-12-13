---
title: Dimensões principais de mídia de transmissão
description: Dimensões disponíveis ao habilitar o [!UICONTROL Media Core] para um conjunto de relatórios.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 10%

---

# Dimensões principais de mídia de transmissão

*Esta página descreve as dimensões disponíveis quando você habilita o [!UICONTROL Media Core] para um conjunto de relatórios. Consulte [Métricas principais de streaming de mídia](../metrics/sm-core.md) para ver as métricas disponíveis.*

As dimensões principais de mídia de transmissão fornecem funcionalidade básica de relatórios para dados coletados por meio de bibliotecas de coleção de mídia de transmissão. O uso dessas dimensões requer a **[!UICONTROL Coleção de Mídia de Streaming de Adobe]**. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.

Quando você habilita o **[!UICONTROL Media Core]** em [Media Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), as seguintes dimensões estão disponíveis:

| Nome da dimensão | Descrição | Enviado com | Variável de dados de contexto |
| --- | --- | --- | --- |
| Conteúdo | ID do conteúdo. | Início da mídia, Fechamento da mídia | `a.media.name` |
| Canal de conteúdo | A estação ou canal de distribuição onde o conteúdo é reproduzido. Qualquer valor de string é válido. | Início da mídia, Fechamento da mídia | `a.media.channel` |
| Comprimento do conteúdo (variável) | O comprimento máximo (ou duração) do conteúdo consumido, em segundos. Essa dimensão é necessária para várias métricas, incluindo &quot;Público-alvo médio por minuto&quot;. Se essa dimensão não for definida, as métricas dependentes não estarão disponíveis.<br><br>Uma dimensão de classificação chamada &#39;Duração do vídeo&#39; também está disponível, o que fornece uma finalidade semelhante. Essa dimensão e a classificação são tratadas como duas dimensões distintas. | Início da mídia, Fechamento da mídia | `a.media.length` |
| Nome do conteúdo (variável) | O nome amigável do conteúdo. Uma classificação chamada &quot;Nome do vídeo&quot; também está disponível, o que fornece um propósito semelhante. Essa dimensão e a classificação são tratadas como duas dimensões distintas. | Início da mídia, Fechamento da mídia | `a.media.friendlyName` |
| Nome do reprodutor de conteúdo | O nome do reprodutor de conteúdo. | Início da mídia, Fechamento da mídia | `a.media.playerName` |
| Segmento de conteúdo | O intervalo que descreve a parte do conteúdo que foi exibida, em minutos. O segmento é calculado como os valores mín. e máx. do indicador de reprodução durante a sessão de reprodução. | Fechamento de mídia | `a.media.segment` |
| Tipo de conteúdo | O tipo de conteúdo. Os valores válidos incluem `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` ou um valor personalizado. | Início da mídia, Fechamento da mídia | `a.contentType` |
| Caminho da mídia | O caminho que o visitante tomou para alcançar o conteúdo. | Início da mídia | `a.media.path` |
| Tipo de transmissão | O tipo de fluxo. Os valores válidos incluem `audio` e `video`. | Início da mídia, Fechamento da mídia | `a.media.streamType` |

{style="table-layout:auto"}

Além das dimensões acima, o Adobe cria automaticamente as seguintes dimensões de classificação. Você deve fazer upload dos dados de classificação para visualizar relatórios que usam essas dimensões.

| Nome da classificação | Dimensão principal | Descrição |
| --- | --- | --- |
| Duração do vídeo | Conteúdo | O comprimento máximo (ou duração) do conteúdo consumido, em segundos. As métricas que dependem da duração do conteúdo não podem usar essa classificação; você deve criar uma métrica calculada para obter métricas como &quot;Público-alvo médio por minuto&quot; usando essa classificação. |
| Nome do vídeo | Conteúdo | O nome amigável do conteúdo. É o equivalente de classificação do Nome do conteúdo (variável). |

{style="table-layout:auto"}
