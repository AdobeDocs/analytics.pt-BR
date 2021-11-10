---
description: Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.
title: Fluxos interdimensionais
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: b0baf1fbc8cf4cafe1d5292774e47556c9b0151b
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 96%

---

# Fluxos interdimensionais

Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.

Aqui está um vídeo sobre quebra automática de texto e fluxo multidimensional no Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/24041/?quality=12)

Um rótulo de dimensão na parte superior de cada coluna de Fluxo torna mais intuitivo o uso de várias dimensões em uma visualização de fluxo:

![](assets/flow.png)

Vamos analisar dois casos de uso: um de aplicativo e um da web.

## Caso de uso 1: aplicativo {#section_3D31D37B9C9F4134AE46C96291E41294}

A dimensão de [!UICONTROL Nome da ação] foi adicionada ao fluxo, com os principais itens retornados sendo [!UICONTROL ItemAdded]:

![](assets/multi-dimensional-flow.png)

Para explorar a interação entre telas/páginas e ações neste aplicativo, você pode arrastar a dimensão de página a diferentes locais, dependendo do que você deseja explorar:

* Arraste-o para uma área (dentro do retângulo com margens pretas exibido) para **substituir** os resultados principais nos finais:

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* Arraste para o espaço branco no final (observe o colchete preto) para **adicionar à** visualização:

   ![](assets/multi-dimensional-flow4.png)

Aqui está o resultado se você decidir substituir o item ItemScaled na coluna da direita com a dimensão de Página. Os principais resultados são substituídos para os principais resultados para a dimensão de Página:

![](assets/multi-dimensional-flow5.png)

Agora você pode ver como os clientes se movem pelas ações e páginas. Você pode explorar o fluxo, clicando em diferentes nós:

![](assets/multi-dimensional-flow6.png)

É isso que acontece ao adicionar outra dimensão de Nome de ação no final da visualização:

![](assets/multi-dimensional-flow7.png)

Isso permitirá insights aprofundados e possíveis alterações ao aplicativo que você está analisando.

## Caso de uso 2: web {#section_8D55983FA0C84926995270052AE01CD8}

Este caso de uso mostra como você pode analisar quais campanhas impulsionam a maioria das entradas em um site.

Arraste a dimensão de Nome da campanha para um novo fluxo:

![](assets/multi-dimensional-flow8.png)

Agora, quero saber para quais páginas essas campanhas estão impulsionando tráfego, então, arrasto a dimensão de Página à direita dos resultados de fluxo para adicionar à visualização:

![](assets/multi-dimensional-flow9.png)
