---
description: Saiba mais sobre
title: Atribuição e tipo de métrica
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 69%

---

# Atribuição e tipo de métrica

Ao [criar uma métrica calculada](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), você pode especificar o tipo de métrica e o modelo de atribuição.

## Tipo de métrica

Para especificar o tipo de métrica ao criar uma métrica calculada:

1. Selecione o ícone de engrenagem ao lado da métrica cujo tipo você deseja selecionar.

   ![](assets/cm_type_alloc.png)

1. Escolha entre as seguintes opções:

   | Tipo de métrica | Definição |
   |---|---|
   | Padrão | Essas métricas são as mesmas métricas usadas nos relatórios padrão do [!DNL Analytics]. Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item de linha. Por exemplo, [Pedidos] / [Visitas] pega os pedidos de um item de linha específico e divide pelo número de visitas do item de linha específico. |
   | Total geral | Use Total geral para o período do relatório em cada item de linha. Se uma fórmula consistiu de uma única métrica de total geral, ela exibe o mesmo número total em cada item de linha. As métricas de total geral são úteis para criar métricas calculadas que se comparam aos dados totais do site. Por exemplo, [Pedidos] / [Total de visitas] mostra a proporção de pedidos com relação a TODAS as visitas ao site, e não apenas visitas ao item de linha específico. |

## Como a alocação linear funciona

[A atribuição](/help/analyze/analysis-workspace/attribution/overview.md) é a maneira como os modelos de alocação em métricas calculadas são avaliados.

Para obter uma lista completa de modelos de atribuição não padrão e janelas de retrospectiva com suporte, consulte [Modelos de atribuição e janelas de retrospectiva](/help/analyze/analysis-workspace/attribution/models.md).

O exemplo a seguir ilustra como as métricas calculadas com alocações lineares funcionam nos relatórios:

| | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 | Ocorrência 6 | Ocorrência 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dados de entrada | PROMOÇÃO A | - | PROMOÇÃO A | PROMOÇÃO B | - | PROMOÇÃO C | $10 |
| eVar de último contato | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO B | PROMOÇÃO B | PROMOÇÃO C | $10 |
| eVar de primeiro contato | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | $10 |
| Exemplo de propriedade | PROMOÇÃO A | - | PROMOÇÃO A | PROMOÇÃO B | - | PROMOÇÃO C | $10 |

Neste exemplo, os valores A, B e C foram enviados para uma variável nas ocorrências 1, 3, 4 e 6 antes de uma compra de US$10 ser feita na ocorrência 7. Na segunda linha, esses valores persistem entre as ocorrências com base na visita do último contato. A terceira linha ilustra uma persistência na visita do primeiro contato. Por fim, a última linha ilustra como os dados seriam relatados para uma propriedade que não tenha persistência.

