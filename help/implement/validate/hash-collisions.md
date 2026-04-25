---
title: Colisões de hash
description: Descreve o que é uma colisão de hash e como ela pode ocorrer.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: e6dd38fe34d7e0ab69bdf1c68716427905caa356
workflow-type: tm+mt
source-wordcount: '539'
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

As colisões de hash não podem ser totalmente eliminadas, mas seu impacto nos relatórios pode ser atenuado. A maioria das colisões de hash ocorre com dois valores incomuns, que não têm impacto significativo nos relatórios. Mesmo que um hash colida com um valor comum e incomum, o resultado é insignificante. However, in rare cases where two popular values experience a hash collision, it is possible to see its effect clearly. Adobe recommends the following to reduce its effect in reports:

* **Change the date range**: Hash tables change each month. Changing the date range to span another month can give each value different hashes that don&#39;t collide. It is usually the fastest way to clear a visible anomaly from a specific report.
* **Reduce the number of unique values**: You can adjust your implementation or use [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) to help reduce the number of unique values that a dimension collects. For example, if your dimension collects a URL, you can strip query strings or protocol.
* **Use [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) or [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md)**: These tools do not rely on hash tables.
* **Move to [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=pt-BR)**: Customer Journey Analytics has no hashing layer and [no cardinality limits on dimensions](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Consider moving to this product if hash collisions or [[!UICONTROL Low-Traffic]](/help/technotes/low-traffic.md) frequently affect your reports.

>[!MORELIKETHIS]
>
>* [[!UICONTROL Low-Traffic] value in Adobe Analytics](/help/technotes/low-traffic.md)
>* [Processing rules overview](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
