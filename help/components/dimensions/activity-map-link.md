---
description: O nome do link clicado.
title: Link para o Activity Map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 8%

---

# Link para o Activity Map

O &#39;Link de Activity Map&#39; [dimensão](overview.md) exibe os links mais populares que foram clicados. É possível usar essa dimensão para comparar quais links do site são mais usados, independentemente de onde os links foram clicados.

## Preencher esta dimensão com dados

Esta dimensão recupera dados da [Variável de dados de contexto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Se sua implementação usar [Activity Map](/help/analyze/activity-map/overview.md), essa variável de dados de contexto coletará dados automaticamente quando os links forem clicados.

Para um determinado link que foi clicado, o Activity Map pesquisa o seguinte (em ordem):

1. A variável `s_objectID`
1. O texto interno do link
1. O atributo `alt` para imagens
1. O atributo `title`
1. O atributo `src` para imagens
1. O atributo `action` para formulários

Se o elemento clicado não contiver nenhum dos critérios acima, o Activity Map não coletará dados para esse clique.

## Itens de dimensão

Os itens de Dimension incluem o texto do link ou outros atributos de link nos quais os visitantes clicam. A estrutura do site e a implementação da organização determinam os valores exatos coletados.
