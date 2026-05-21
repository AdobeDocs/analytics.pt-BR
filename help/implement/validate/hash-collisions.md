---
title: Colisões de hash
description: Descreve o que é uma colisão de hash e como ela pode ocorrer.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/yjYX-h-8jJA7k-jzRMOJ0l2BxN5-no2kCfySkGYss8w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 5%

---

# Colisões de hash

As dimensões no Adobe Analytics coletam valores de string. Às vezes, essas cadeias de caracteres têm centenas de caracteres, enquanto outras vezes são curtas. Para melhorar o desempenho, esses valores de sequência de caracteres não são usados diretamente no processamento do tempo do relatório. Em vez disso, um hash é calculado para cada valor, produzindo um identificador de tamanho uniforme. Para a maioria dos campos, o valor é convertido em minúsculas antes do hash, o que reduz o número total de valores únicos. Todos os relatórios são executados nesses valores com hash, o que aumenta drasticamente seu desempenho.

O Adobe Analytics mantém uma tabela de hash separada para cada variável e cada tabela é recriada todo mês. Em qualquer uma dessas tabelas, dois valores de origem diferentes podem produzir ocasionalmente o mesmo hash, conhecido como *colisão de hash*.

Colisões de hash podem se manifestar nos relatórios da seguinte maneira:

* Se você visualizar um relatório ao longo do tempo e observar um pico inesperado, é possível que vários valores únicos para essa variável usem o mesmo hash.
* Se você usar um segmento e ver um valor inesperado, é possível que o item de dimensão inesperado use o mesmo hash que outro item de dimensão que correspondeu ao seu segmento.

## Probabilidades de colisão de hash

O Adobe Analytics usa hashes de 32 bits para a maioria das dimensões, o que significa que há 2<sup>32</sup> combinações de hash possíveis (aproximadamente 4,3 bilhões). As chances aproximadas de encontrar uma colisão de hash com base no número de valores únicos são as seguintes. Essas probabilidades são baseadas em uma única dimensão para um único mês.

| Valores únicos | Probabilidades |
| --- | --- |
| 1.000 | 0.01% |
| 10.000 | 1% |
| 50.000 | 26% |
| 100.000 | 71% |

Semelhante ao [paradoxo de aniversário](https://en.wikipedia.org/wiki/Birthday_problem), a probabilidade de colisões de hash aumenta drasticamente à medida que o número de valores únicos aumenta. Com 1 milhão de valores únicos, é provável que haja pelo menos 100 colisões de hash para essa dimensão.

## Reduzindo colisões de hash

As colisões de hash não podem ser totalmente eliminadas, mas seu impacto nos relatórios pode ser atenuado. A maioria das colisões de hash ocorre com dois valores incomuns, que não têm impacto significativo nos relatórios. Mesmo que um hash colida com um valor comum e incomum, o resultado é insignificante. No entanto, em casos raros em que dois valores populares experimentam uma colisão de hash, é possível ver seu efeito claramente. A Adobe recomenda o seguinte para reduzir seu efeito nos relatórios:

* **Alterar intervalo de datas**: as tabelas de hash mudam a cada mês. Alterar o intervalo de datas para abranger outro mês pode dar a cada valor hashes diferentes que não colidem. Normalmente, é a maneira mais rápida de eliminar uma anomalia visível de um relatório específico.
* **Reduza o número de valores únicos**: você pode ajustar sua implementação ou usar [Regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para ajudar a reduzir o número de valores únicos que uma dimensão coleta. Por exemplo, se a dimensão coletar um URL, você poderá remover cadeias de caracteres de consulta ou protocolo.
* **Usar [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) ou [Feeds de Dados](/help/export/analytics-data-feed/data-feed-overview.md)**: essas ferramentas não dependem de tabelas de hash.
* **Mover para [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=pt-BR)**: o Customer Journey Analytics não tem camada de hash e [não tem limites de cardinalidade em dimensões](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Considere mudar para este produto se as colisões de hash ou o [[!UICONTROL Tráfego baixo]](/help/technotes/low-traffic.md) afetarem frequentemente seus relatórios.

>[!MORELIKETHIS]
>
>* Valor [[!UICONTROL Tráfego baixo] no Adobe Analytics](/help/technotes/low-traffic.md)
>* [Visão geral das regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
