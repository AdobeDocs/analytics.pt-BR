---
description: Saiba como criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos em uma análise de fallout no Analysis Workspace.
keywords: fallout e segmentação;segmentos na análise de fallout;comparar segmentos no fallout
title: Aplicar Segmentos Na Análise De Fallout
feature: Visualizations
role: User, Admin
exl-id: 2177cd09-5a27-4295-8414-580cf53062cb
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 71%

---

# Aplicar segmentos na análise de fallout

Você pode criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos no Analysis Workspace.

>[!IMPORTANT]
>
>Os segmentos usados como pontos de verificação no Fallout devem usar um contêiner que esteja em um nível inferior ao contexto geral da visualização do Fallout. Com um Fallout de contexto de visitante, os segmentos usados como pontos de verificação devem ser segmentos baseados em visita ou ocorrência. Com um Fallout de contexto de visita, os segmentos usados como ponto de verificação devem ser segmentos baseados em ocorrências. Se você usar uma combinação inválida, o fallout será de 100%. Você vê um aviso na visualização de Fallout ao adicionar um segmento incompatível como ponto de contato. Determinadas combinações inválidas de contêineres de segmento resultarão em diagramas de Fallout inválidos, por exemplo:
>
>* Usar um segmento com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto do visitante.
>* Usar um segmento com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas.
>* Usar um segmento com base em visitas como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas.
>

## Criar um segmento a partir de um ponto de contato {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Crie um segmento a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Para fazê-lo, clique com o botão direito no ponto de contato e selecione **[!UICONTROL Criar segmentos a partir do ponto de contato]**.

   ![](assets/segment-from-touchpoint.png)

   O Construtor de segmentos abre, pré-preenchido com o segmento sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![](assets/segment-builder.png)

1. Atribua um título e uma descrição ao segmento e salve-o.

   Agora você pode usar este segmento em qualquer relatório que quiser.

## Adicionar um segmento como ponto de contato {#section_17611C1A07444BE891DC21EE8FC03EFC}

Se quiser ver, por exemplo, a tendência dos seus usuários dos EUA e como eles afetam o fallout, basta arrastar o segmento de usuários dos EUA ao fallout:

![](assets/segment-touchpoint.png)

Ou, você pode criar um ponto de contato AND, arrastando o segmento de usuários dos EUA ao outro ponto de verificação.

## Comparar segmentos no fallout {#section_E0B761A69B1545908B52E05379277B56}

É possível comparar um número ilimitado de segmentos na visualização de Fallout. (Observe que o vídeo abaixo declara que você pode comparar até 3 segmentos, o que está errado.)


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Comparar segmentos em uma visualização de fallout](https://video.tv.adobe.com/v/30765?quality=12&learn=on&captions=por_br){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


1. Selecione os segmentos que deseja comparar no painel [!UICONTROL Segmentos] à esquerda. Em nosso exemplo, selecionamos dois segmentos: usuários dos EUA e usuários de fora dos EUA.
1. Arraste-os à área de Segmento na parte superior.

   ![](assets/segment-drop.png)

1. Opcional: você pode manter “Todas as visitas” como o contêiner padrão ou excluí-lo.

   ![](assets/seg-compare.png)

1. Agora você pode comparar o fallout nos dois segmentos, como onde um segmento supera outro, ou outros insights.
