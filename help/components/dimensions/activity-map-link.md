---
description: O nome do link clicado.
title: Link do Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
TQID: https://experienceleague.adobe.com/A5HaPb0TghRKVykJ9V2UMJ0mlsYElLkCyBwxzTd6VII
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
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 8%

---

# Link do Activity Map

O &#39;Link do Activity Map&#39; [dimensão](overview.md) exibe os links mais populares que foram clicados. É possível usar essa dimensão para comparar quais links do site são mais usados, independentemente de onde os links foram clicados.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Se sua implementação usa o [Activity Map](/help/analyze/activity-map/overview.md), esta variável de dados de contexto coleta dados automaticamente quando os links são clicados.

Para um determinado link que foi clicado, o Activity Map pesquisa o seguinte (em ordem):

1. A variável `s_objectID`
1. O texto interno do link
1. O atributo `alt` para imagens
1. O atributo `title`
1. O atributo `src` para imagens
1. O atributo `action` para formulários

Se o elemento clicado não contiver nenhum dos critérios acima, a Activity Map não coletará dados para esse clique.

## Itens de dimensão

Os itens do Dimension incluem o texto do link ou outros atributos de link nos quais os visitantes clicam. A estrutura do site e a implementação da organização determinam os valores exatos coletados.
