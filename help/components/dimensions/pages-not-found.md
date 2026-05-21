---
title: Páginas não encontradas (dimensões)
description: URLs que retornaram um erro ao site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 77%

---

# Páginas não encontradas

*Esta página de ajuda descreve como a dimensão &quot;Páginas não encontradas&quot; funciona como uma [dimensão](overview.md). Consulte a página de métricas [Páginas não encontradas](../metrics/pages-not-found.md) para obter informações sobre como ela funciona como uma métrica.*

A dimensão “Páginas não encontradas” exibe URLs que continham um erro. Essa dimensão é útil quando você deseja diminuir o número de erros que os visitantes recebem no site.

* É possível utilizar essa dimensão em uma [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para ver em quais páginas os visitantes clicam para chegar ao erro. Em seguida, você pode trabalhar com equipes de desenvolvimento em sua organização para corrigir o link em cada página.
* É possível utilizar essa dimensão com a dimensão [“Referenciador”](referrer.md) para ver o lugar no site que os visitantes chegam quando eles vêm de links externos. É possível implementar redirecionamentos para o local desejado ou trabalhar com terceiros para corrigir o link.

## Preencher esta dimensão com dados

Essa dimensão recupera dados de [`pageType` e das `g` sequências de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Se a sequência de consulta `pageType` for igual a `errorPage`, a sequência de consulta `g` (URL da página) será registrada. O AppMeasurement coleta esses dados usando a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md). Se a variável `pageType` não estiver definida ou programada como algo diferente de `errorPage`, nenhum dado para essa dimensão será coletado.

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas do site em que ocorreu um erro.
