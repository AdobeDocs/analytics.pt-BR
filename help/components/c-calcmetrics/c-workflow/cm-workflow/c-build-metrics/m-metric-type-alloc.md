---
description: 'Saiba mais sobre '
title: Atribuição e tipo de métrica
uuid: 64649698-df2a-42c3-bb31-938f766e1d1f
translation-type: ht
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: ht
source-wordcount: '908'
ht-degree: 100%

---


# Atribuição e tipo de métrica

Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo e o modelo de atribuição.

## Tipo de métrica

![](assets/cm_type_alloc.png)

| Tipo de métrica | Definição |
|---|---|
| Padrão | Essas métricas são as mesmas métricas usadas nos relatórios padrão do [!DNL Analytics]. Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item de linha. Por exemplo, [Pedidos] / [Visitas] pega os pedidos de um item de linha específico e divide pelo número de visitas do item de linha específico. |
| Total | Use o total para informar o período de relatórios em cada item de linha. Se uma fórmula consistir em uma única métrica de total, ela exibirá o mesmo número total em cada item de linha. Métricas de total são úteis para a criação de métricas calculadas que comparam os dados totais do site. Por exemplo, [Pedidos] / [Total de visitas] mostra a proporção de pedidos com relação a TODAS as visitas ao site, e não apenas visitas ao item de linha específico. |

## Modelo de atribuição de coluna

>[!IMPORTANT]
>
>Em julho de 2018, o [!DNL Analytics] introduziu o [Attribution IQ](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/attribution/models.html), que reimaginou a maneira que modelos de alocação em métricas calculadas são avaliados. Como parte dessa alteração, as métricas calculadas que usam um modelo de alocação não padrão foram migradas para novos modelos de atribuição melhorados:
>
>* Para obter uma lista completa de modelos de atribuição não padrão e janelas de lookback com suporte, consulte a documentação do [Attribution IQ](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/attribution/models.html).
>* Os modelos de alocação &quot;Último contato do canal de marketing&quot; e &quot;Primeiro contato do canal de marketing&quot; serão migrados para os novos modelos de atribuição &quot;Último contato&quot; e &quot;Primeiro contato&quot;, respectivamente (Observe que &quot;Canais de marketing&quot; não será descontinuado - apenas os dois modelos de alocação que aparecem nas métricas calculadas o serão).
>* Além disso, corrigiremos a maneira como a alocação linear é calculada. Para clientes que usam métricas calculadas com modelos de alocação &quot;linear&quot;, os relatórios podem ser levemente alterados para refletir o novo modelo de atribuição corrigido. Essa alteração nas métricas calculadas será refletida no Analysis Workspace, Reports &amp; Analytics, na API de relatórios e no Report Builder. Para obter mais informações, consulte **Como a alocação linear funciona (desde 19 de julho de 2018)** abaixo.

>



## Como a alocação linear funciona (desde 19 de julho de 2018)

Em julho de 2018, o Adobe alterou a maneira como a alocação linear é informada para Métricas calculadas. Essa alteração afeta o Analysis Workspace, o Reports &amp; Analytics, o Report Builder, o Activity Map e as APIs de relatórios. A alteração afetará principalmente as eVars e outras dimensões persistentes. Observe que essas alterações serão aplicadas apenas às métricas calculadas e não afetarão outros relatórios que usem alocação linear (como o relatório Páginas no Reports &amp; Analytics). Os outros relatórios que usam alocação linear continuarão a usar o método existente de alocação linear.

O seguinte exemplo ilustra como as métricas calculadas com alocação linear serão alteradas nos relatórios:

|  | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 | Ocorrência 6 | Ocorrência 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dados de entrada | PROMOÇÃO A | - | PROMOÇÃO A | PROMOÇÃO B | - | PROMOÇÃO C | $10 |
| eVar de último contato | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO B | PROMOÇÃO B | PROMOÇÃO C | $10 |
| eVar de primeiro contato | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | $10 |
| Exemplo de propriedade | PROMOÇÃO A | - | PROMOÇÃO A | PROMOÇÃO B | - | PROMOÇÃO C | $10 |

Neste exemplo, os valores A, B e C foram enviados para uma variável nas ocorrências 1, 3, 4 e 6 antes de uma compra de US$10 ser feita na ocorrência 7. Na segunda linha, esses valores persistem entre as ocorrências com base na visita do último contato. A terceira linha ilustra uma persistência na visita do primeiro contato. Por fim, a última linha ilustra como os dados seriam relatados para uma propriedade que não tenha persistência.

## Diferenças em como a alocação linear funciona no Reports &amp; Analytics e no Workspace

Há algumas diferenças em como a atribuição linear funciona nessas duas ferramentas:

* No Reports &amp; Analytics, a atribuição linear (processada) sempre é baseada em visitas, e no Workspace pode ser baseada em visitas ou visitantes.
* No Reports &amp; Analytics, se o valor Nenhum fosse transmitido na primeira ocorrência de uma visita, o valor (inicial) persistiria da visita anterior. Esse NÃO é o caso no Workspace (Attribution IQ). Se nenhum valor for transmitido na primeira ocorrência de uma visita, “Nenhum” será o valor inicial.

## Como a alocação linear funcionava antes de julho de 2018

Antes de 19 de julho de 2018, a atribuição linear era calculada após a persistência do primeiro contato ou do último contato já ter ocorrido. Isso significava que para a eVar último contato acima, os US$10 seriam distribuídos da seguinte maneira: A = 10 * (3/6) = US$5, B = 10 * (2/6) = US$3,33, C = 10 * (1/6) = US$1,67.

Para a eVar primeiro contato acima, todos os US$10 seriam dados a A. Para a propriedade: A = 10 * (2/4) = US$5, B = 10 * (1/4) = US$2,50 e C = 10 * (1/4) = US$2,50. Para resumir a alocação linear como ela funcionava anteriormente:

| Valores | eVar de último contato atual | eVar de primeiro contato atual | Propriedade atual |
|---|---|---|---|
| PROMOÇÃO A | US$5,00 | US$10,00 | US$5,00 |
| PROMOÇÃO B | US$3,33 | $0 | US$2,50 |
| PROMOÇÃO C | US$1,67 | $0 | US$2,50 |
| Total | US$10,00 | US$10,00 | US$10,00 |

**Resumo de como a alocação linear funciona desde 19 de julho de 2018**

Em 19 de julho de 2018, corrigimos este comportamento nas métricas calculadas. Em vez de usar os valores persistentes com base no último contato ou no primeiro contato, o [!DNL Analytics] usa apenas os valores que foram passados (a primeira linha da tabela superior). Sendo assim, as configurações de alocação de dimensão não afetam mais a maneira como a alocação linear é calculada (isso significa que propriedades e eVars serão tratadas da mesma maneira) e os resultados reflete o que foi originalmente passado em vez dos valores do primeiro ou do último contato que possam ter persistido. Então, em todos os três casos, A = 10 * (2/4) = US$5, B = 10 * (1/4) = US$2,50 e C = 10 * (1/4) = US$2,50.

| Valores | Nova eVar de último contato | Nova eVar de primeiro contato | Nova propriedade |
|---|---|---|---|
| PROMOÇÃO A | US$5,00 | US$5,00 | US$5,00 |
| PROMOÇÃO B | US$2,50 | US$2,50 | US$2,50 |
| PROMOÇÃO C | US$2,50 | US$2,50 | US$2,50 |
| Total | US$10,00 | US$10,00 | US$10,00 |

