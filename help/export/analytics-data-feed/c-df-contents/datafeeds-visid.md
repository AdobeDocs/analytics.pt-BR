---
description: 'null'
keywords: Feed de dados; tarefa; visitantes; Experience Cloud ID; ID do visitante do Analytics; identify
seo-description: 'null'
seo-title: Identificar visitantes
solution: Analytics
title: Identificar visitantes
topic: Reports and Analytics
uuid: 2490 b 67 e-a 333-422 d -82 fa-cb 0670 ef 2 e 0 c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Identificar visitantes

O Analytics oferece diversos mecanismos para identificar visitantes (listados em [Identificação de visitantes](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)). Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**Para identificar visitantes únicos:**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5, 8 e 9 são linhas de resumo carregadas por meio de fontes de dados. 7 representa os carregamentos de fonte de dados da ID de transação que não devem ser incluídos nas contagens de visita e de visitante. Consulte [Pesquisa de fonte de hit](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combine `post_visid_high` with `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

Caso queira determinar qual mecanismo foi usado para definir o valor da ID de visitante (por exemplo, para calcular a aceitação de cookies), o `post_visid_type` possui uma chave de pesquisa que indica qual método de ID foi usado. As chaves de pesquisa estão listadas juntamente com os mecanismos de ID de visitante na [tabela abaixo](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A).

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

A Experience Cloud ID é relatada em uma coluna separada, `mcvisid`. Como essa ID é relatada em uma coluna própria, pode não ficar claro se o Analytics está usando essa ID ou uma ID diferente.

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. Esses campos são os únicos de ID do visitante com um valor em cada linha no feed de dados.

## ID de visitante do Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Existem várias maneiras de identificar um visitante no Analytics (listadas na tabela a seguir em ordem de preferência):

| Pedido usado | Parâmetro de consulta (método de coleta) | Valor da coluna post_visid_type | Presente quando |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) | 0 | s.visitorID está configurada. |
| ![](assets/step2_icon.png) | [aid (s_vi cookie)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_analytics) | 3 | O visitante possuía um cookie s_vi antes da implantação do serviço de ID de visitante ou seu [período de carência](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_grace_period) da ID de visitante está configurado. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ cookie definido pelo Serviço de identidade)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | O navegador do visitante aceita cookies (originais) e o Serviço de identidade é implantado. |
| ![](assets/step4_icon.png) | [fid (cookie de fallback em H.25.3 ou mais recente, ou AppMeasurement para JavaScript)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 4 | O navegador do visitante aceita cookies (originais). |
| ![](assets/step5_icon.png) | [Cabeçalho de inscrição em dispositivos móveis HTTP](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_mobile) | 2 | O dispositivo é reconhecido como um dispositivo móvel. |
| ![](assets/step6_icon.png) | [Endereço IP, Agente do usuário, Endereço IP de gateway](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 1 | O navegador do visitante não aceita cookies. |

Em diversos cenários você poderá ver 2 ou 3 IDs distintas em uma chamada, mas o Analytics usará a primeira ID da lista como a ID de visitante oficial e separará o valor entre as colunas `post_visid_high` e `post_visid_low`. Por exemplo, se você estiver enviando uma ID de visitante personalizada (incluída no parâmetro de consulta "vid"), essa ID será usada antes de outras IDs que possam estar presentes nessa mesma ocorrência.
