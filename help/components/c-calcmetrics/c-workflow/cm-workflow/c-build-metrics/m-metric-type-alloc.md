---
description: Saiba mais sobre
title: Tipo de métrica e atribuição
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 21c4d1b591daf7229bd36845e42e2dec473e792f
workflow-type: ht
source-wordcount: '635'
ht-degree: 100%

---

# Tipo de métrica e atribuição {#metric-type-attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modelo"
>abstract="Selecione um modelo de atribuição para a métrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Último contato"
>abstract="100% do crédito vai para o último valor de dimensão visto por um visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primeiro contato"
>abstract="100% do crédito vai para o primeiro valor de dimensão visto por um visitante."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linear"
>abstract="O crédito é distribuído uniformemente em todos os valores de dimensão."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participação"
>abstract="100% de crédito para cada valor de dimensão visto por um visitante.<br/>Os totais da coluna estão exagerados."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Mesmo contato"
>abstract="O crédito é fornecido somente para valores de dimensão que ocorrem no mesmo evento que a conversão."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Mesmo contato"
>abstract="O crédito é fornecido somente para valores de dimensão que ocorrem no mesmo evento que a conversão."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="Forma de U"
>abstract="40% do crédito é atribuído ao primeiro valor de dimensão, 40% ao último, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="60% do crédito é atribuído ao valor da última dimensão, 20% ao primeiro, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="60% do crédito é atribuído ao valor da última dimensão, 20% ao primeiro, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J invertido"
>abstract="60% do crédito é atribuído ao primeiro valor de dimensão, 20% ao último, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J invertido"
>abstract="60% do crédito é atribuído ao primeiro valor de dimensão, 20% ao último, 20% é compartilhado pelo meio."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Declínio de tempo"
>abstract="Os valores de dimensão mais próximos do tempo a uma conversão recebem mais crédito."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizado"
>abstract="Defina sua própria posição com base na ponderação de atribuição."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizado"
>abstract="Defina sua própria posição com base na ponderação de atribuição."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorítmico"
>abstract="O crédito é determinado dinamicamente em um algoritmo estatístico."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Container"
>abstract="Selecione um container para definir o escopo desejado da atribuição."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Janela de pesquisa"
>abstract="Essa configuração determina a janela de atribuição de dados que será aplicada a cada conversão."

Ao [criar uma métrica calculada](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), é possível especificar o tipo de métrica e o modelo de atribuição.

## Tipo de métrica

Para especificar o tipo de métrica ao criar uma métrica calculada:

1. Selecione o ícone de engrenagem ao lado da métrica cujo tipo você deseja selecionar.

   ![](assets/cm_type_alloc.png)

1. Escolha entre as seguintes opções:

   | Tipo de métrica | Definição |
   |---|---|
   | Padrão | Essas métricas são as mesmas métricas usadas nos relatórios padrão do [!DNL Analytics]. Se uma fórmula consistir de uma única métrica padrão, ela exibirá dados idênticos à sua métrica não calculada equivalente. Métricas padrão são úteis ao criar métricas calculadas específicas para cada item de linha. Por exemplo, [Pedidos] / [Visitas] pega os pedidos de um item de linha específico e divide pelo número de visitas do item de linha específico. |
   | Total geral | Use o total geral do período de relatório em cada item de linha. Se a fórmula consistir de uma única métrica de total geral, ela exibirá o mesmo número total em cada item de linha. Métricas de total geral são úteis para criar métricas calculadas que se comparam aos dados totais do site. Por exemplo, [Pedidos] / [Total de visitas] mostra a proporção de pedidos com relação a TODAS as visitas ao site, e não apenas visitas ao item de linha específico. |

## Como a alocação linear funciona

A [Atribuição](/help/analyze/analysis-workspace/attribution/overview.md) é uma forma de se avaliar os modelos de alocação em métricas calculadas.

Para obter uma lista completa de modelos de atribuição não padrão e janelas de retrospectiva permitidas, consulte [Modelos de atribuição e janelas de retrospectiva](/help/analyze/analysis-workspace/attribution/models.md).

O seguinte exemplo ilustra como as métricas calculadas com alocações lineares funcionam nos relatórios:

| | Ocorrência 1 | Ocorrência 2 | Ocorrência 3 | Ocorrência 4 | Ocorrência 5 | Ocorrência 6 | Ocorrência 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dados de entrada | PROMOÇÃO A | - | PROMOÇÃO A | PROMOÇÃO B | - | PROMOÇÃO C | $10 |
| eVar de último contato | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO B | PROMOÇÃO B | PROMOÇÃO C | $10 |
| eVar de primeiro contato | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | PROMOÇÃO A | $10 |
| Exemplo de propriedade | PROMOÇÃO A | - | PROMOÇÃO A | PROMOÇÃO B | - | PROMOÇÃO C | $10 |

Neste exemplo, os valores A, B e C foram enviados para uma variável nas ocorrências 1, 3, 4 e 6 antes de uma compra de US$10 ser feita na ocorrência 7. Na segunda linha, esses valores persistem entre as ocorrências com base na visita do último contato. A terceira linha ilustra uma persistência na visita do primeiro contato. Por fim, a última linha ilustra como os dados seriam relatados para uma propriedade que não tenha persistência.

