---
description: Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.
title: Fluxos interdimensionais
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: be6056f9e7a64b47ab544594149ebfbe134f1c04
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 7%

---

# Fluxos interdimensionais

Um fluxo interdimensional permite analisar os caminhos do usuário em várias dimensões.

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Fluxos interdimensionais](https://video.tv.adobe.com/v/24041?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]

Este artigo mostra como usar esse fluxo para dois casos de uso: interações e eventos de aplicativos móveis e como campanhas impulsionam visitas da Web.

## Interações e eventos do aplicativo móvel

A dimensão [!UICONTROL Nome da tela] é usada neste fluxo de exemplo para ver como os usuários usam as várias telas (cenas) no aplicativo. A tela superior retornada é **[!UICONTROL luma: content: ios: en: home]**, que é a página inicial do aplicativo:

![Um fluxo mostrando o Item Adicionado.](assets/flowapp.png)

Para explorar a interação entre telas e tipos de evento (como adicionar ao carrinho, compras e outros) neste aplicativo, arraste e solte a dimensão **[!UICONTROL Tipos de evento]**:

* Sobre qualquer etapa disponível no fluxo, para substituir essa dimensão:

  ![Um fluxo mostrando a dimensão Página arrastada para as várias áreas.](assets/flowapp-replace.png)

* Fora da visualização de fluxo atual, para adicionar a dimensão:

  ![Um fluxo mostrando a dimensão Página arrastada para o espaço em branco no final.](assets/flowapp-add.png)

A visualização de fluxo abaixo mostra o resultado da adição da dimensão **[!UICONTROL Tipos de evento]**. A visualização fornece insights sobre como os usuários de aplicativos móveis se movem por várias telas no aplicativo antes de adicionar produtos ao carrinho, fechar o aplicativo, receber uma oferta e muito mais.

![Um fBaixo mostrando os resultados da dimensão Página no topo da lista.](assets/flowapp-result.png)

## Como as campanhas impulsionam as visitas da Web

Você deseja analisar quais campanhas direcionam visitas ao site. Você cria uma visualização de fluxo com o **[!UICONTROL Nome da campanha]** como a dimensão

![Dimensão do nome da campanha da Web de fluxo](assets/flowweb.png)

Substitua a última dimensão **[!UICONTROL Nome da Campanha]** pela dimensão **[!UICONTROL Nome da Página Formatada]** e adicione outra dimensão **[!UICONTROL Nome da Página Formatada]** ao final da visualização de fluxo.

![Nome da campanha da Web de fluxo e dimensão da página da Web](assets/flowweb-replace.png)

Você pode passar o mouse sobre qualquer um dos fluxos para ver mais detalhes. Por exemplo, quais campanhas resultaram em um check-out no carrinho.

![Focalizar o nome da campanha da Web de fluxo e a dimensão da página da Web](assets/flowweb-hover.png)
