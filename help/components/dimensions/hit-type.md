---
title: Tipo de ocorrência
description: Determina se a ocorrência foi uma ocorrência em primeiro ou segundo plano.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 84%

---

# Tipo de ocorrência

A [dimensão](overview.md) do &quot;Tipo de ocorrência&quot; determina se um aplicativo móvel estava em primeiro ou segundo plano quando a ocorrência foi enviada para os servidores de coleta de dados da Adobe. Essa dimensão só é relevante para conjuntos de relatórios que contêm dados para aplicativos móveis. Os dados do navegador coletados pelo AppMeasurement sempre relatam a ocorrência como “Primeiro plano”.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações do SDK móvel na versão 4.13.6 ou superior. Se você não usar o SDK móvel, todas as ocorrências serão listas no item de dimensão “Primeiro plano”. Se “Desativar os relatórios herdados e a atribuição para ocorrências em segundo plano” estiver marcado, as ocorrências em segundo plano serão exibidas apenas nos [Conjuntos de relatórios virtuais](../vrs/vrs-mobile-visit-processing.md).

## Itens de dimensão

Os itens de dimensão incluem `"Foreground"` e `"Background"`. Qualquer ocorrência que não foi enviada em segundo plano de um aplicativo móvel pertence ao item de dimensão `"Foreground"`. Qualquer ocorrência enviada em que o aplicativo móvel estava em segundo plano pertence ao item de dimensão `"Background"`.
