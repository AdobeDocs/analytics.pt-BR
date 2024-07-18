---
title: Colisões de hash
description: Descreve o que é uma colisão de hash e como ela pode ocorrer.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 06f61fa7b39faacea89149650e378c8b8863ac4f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 6%

---

# Colisões de hash

Os Dimension no Adobe Analytics coletam valores de string. Às vezes, essas cadeias de caracteres têm centenas de caracteres, enquanto outras vezes são curtas. Para melhorar o desempenho, esses valores de sequência de caracteres não são usados diretamente no processamento. Em vez disso, um hash é calculado para cada valor para tornar todos os valores de um tamanho uniforme. Todos os relatórios são executados nesses valores com hash, o que aumenta drasticamente seu desempenho.

Para a maioria dos campos, a cadeia de caracteres é convertida inteiramente em minúsculas. A conversão de minúsculas reduz o número de valores únicos. Os valores são atribuídos a hashes mensalmente - o caso de um determinado valor usa o primeiro valor visto em cada mês. A cada mês, há uma pequena possibilidade de dois valores de variável exclusivos serem atribuídos ao mesmo valor. Isso é conhecido como *colisão de hash*.

Colisões de hash podem se manifestar nos relatórios da seguinte maneira:

* Se você visualizar um relatório ao longo do tempo e observar um pico inesperado, é possível que vários valores únicos para essa variável usem o mesmo hash.
* Se você usar um segmento e ver um valor inesperado, é possível que o item de dimensão inesperado use o mesmo hash que outro item de dimensão que correspondeu ao seu segmento.

## Probabilidades de colisão de hash

O Adobe Analytics usa hashes de 32 bits para a maioria das dimensões, o que significa que há 2<sup>32</sup> combinações de hash possíveis (aproximadamente 4,3 bilhões). Uma nova tabela de hash para cada dimensão é criada a cada mês. As chances aproximadas de encontrar uma colisão de hash com base no número de valores únicos são as seguintes. Essas probabilidades são baseadas em uma única dimensão para um único mês.

| Valores únicos | Probabilidades |
| --- | --- |
| 1.000 | 0,01% |
| 10.000 | 1% |
| 50.000 | 26% |
| 100.000 | 71% |

{style="table-layout:auto"}

Semelhante ao [paradoxo de aniversário](https://en.wikipedia.org/wiki/Birthday_problem), a probabilidade de colisões de hash aumenta drasticamente à medida que o número de valores únicos aumenta. Com 1 milhão de valores únicos, é provável que haja pelo menos 100 colisões de hash para essa dimensão.

## Reduzindo colisões de hash

A maioria das colisões de hash ocorre com dois valores incomuns, que não têm impacto significativo nos relatórios. Mesmo que um hash colida com um valor comum e incomum, o resultado é insignificante. No entanto, em casos raros em que dois valores populares experimentam uma colisão de hash, é possível ver seu efeito claramente. A Adobe recomenda o seguinte para reduzir seu efeito nos relatórios:

* **Alterar intervalo de datas**: as tabelas de hash mudam a cada mês. Alterar o intervalo de datas para abranger outro mês pode dar a cada valor hashes diferentes que não colidem.
* **Reduza o número de valores únicos**: você pode ajustar sua implementação ou usar [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) para ajudar a reduzir o número de valores únicos que uma dimensão coleta. Por exemplo, se a dimensão coletar um URL, você poderá remover cadeias de caracteres de consulta ou protocolo.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
