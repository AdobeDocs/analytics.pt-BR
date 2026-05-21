---
description: Saiba como criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos em uma análise de fallout no Analysis Workspace.
keywords: fallout e segmentação;segmentos na análise de fallout;comparar segmentos no fallout
title: Aplicar Segmentos Na Análise De Fallout
feature: Visualizations
role: User, Admin
exl-id: 2177cd09-5a27-4295-8414-580cf53062cb
TQID: https://experienceleague.adobe.com/LZiLhy8ufqzxHyxjqWy1XLv5uU7JgB5eqzPm6wbXF6s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 40%

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

## Criar um segmento a partir de um ponto de contato

1. Crie um segmento a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Para fazê-lo, clique com o botão direito no ponto de contato e selecione **[!UICONTROL Criar segmentos a partir do ponto de contato]**.

   ![](assets/fallout-createsegment.png)

   O Construtor de segmentos abre, pré-preenchido com o segmento sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![](assets/fallout-definesegment.png)

1. Atribua um título e uma descrição ao segmento e salve-o.

   Agora é possível usar esse segmento em qualquer projeto.

## Adicionar um segmento como ponto de contato

Se quiser ver, por exemplo, como as ocorrências do aplicativo móvel tendem e afetam o fallout, basta arrastar o segmento de ocorrências do aplicativo móvel para o fallout:

![](assets/segment-touchpoint.png)

Ou você pode criar um ponto de contato AND arrastando o segmento Ocorrências do aplicativo móvel para outro ponto de verificação.

## Comparar segmentos no fallout

É possível comparar um número ilimitado de segmentos na visualização de Fallout. (Observe que o vídeo abaixo declara que você pode comparar até 3 segmentos, o que está errado.)



1. Selecione os segmentos que você deseja comparar no painel [!UICONTROL Segmento] à esquerda. No exemplo No exemplo, dois segmentos são selecionados: **[!UICONTROL iOS]** e **[!UICONTROL Android]**.
1. Arraste os três segmentos até a área de soltar Segmentos na parte superior da visualização.

   ![](assets/segment-compare.png)

1. Opcional: Você pode manter *Todas as Pessoas* como o contêiner padrão ou excluir o contêiner.

1. Agora é possível comparar o fallout nos três segmentos, por exemplo, em que um segmento está com desempenho melhor que outro ou em outros insights.
