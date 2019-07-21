---
description: Você pode criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos na Analysis Workspace.
keywords: fallout e segmentação; segmentos na análise de fallout; comparar segmentos no fallout
seo-description: Você pode criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos na Analysis Workspace.
seo-title: Aplicar segmentos na análise de fallout
title: Aplicar segmentos na análise de fallout
uuid: e 87 a 33 df -160 e -4943-8 d 02-4 d 6609 ae 3 bb 1
translation-type: tm+mt
source-git-commit: 769d076549484c6939157ef217225493ddbe130e

---


# Aplicar segmentos na análise de fallout

Você pode criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos na Analysis Workspace.

>[!IMPORTANT]
>Os segmentos usados como pontos de verificação no Fallout devem usar um contêiner em um nível inferior do contexto geral da visualização de Fallout. Com um Fallout de contexto de visitante, os segmentos usados como pontos de verificação devem ser segmentos baseados em visitas ou em ocorrências. Com um Fallout de contexto de visita, os segmentos usados como ponto de verificação devem ser segmentos baseados em ocorrências. Se você usar uma combinação inválida, o fallout será 100%. Adicionamos um aviso à visualização de Fallout que será exibida quando você adicionar um segmento incompatível como um ponto de contato. Algumas combinações de contêiner de segmento inválidas resultarão em diagramas de fallout inválidos, como

>* Usar um segmento com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto do visitante
>* Usar um segmento com base em visitantes como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas
>* Usar um segmento com base em visita como um ponto de contato dentro de uma visualização de Fallout de contexto de visitas


## Create a segment from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Primeiro, crie um segmento a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Você faz isso clicando com o botão direito do mouse no ponto de contato e selecionando **[!UICONTROL Criar segmentos a partir do ponto de contato]**.

   ![](assets/segment-from-touchpoint.png)

   O Construtor de segmentos abre, pré-preenchido com o segmento sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![](assets/segment-builder.png)

1. Atribua um título e uma descrição ao segmento e salve-o.

   Agora você pode usar este segmento em qualquer relatório que quiser.

## Add a segment as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

Se quiser ver, por exemplo, a tendência dos seus usuários dos EUA e como eles afetam o fallout, basta arrastar o segmento de usuários dos EUA ao fallout:

![](assets/segment-touchpoint.png)

Ou, você pode criar um ponto de contato AND, arrastando o segmento de usuários dos EUA ao outro ponto de verificação.

## Compare segments in fallout {#section_E0B761A69B1545908B52E05379277B56}

É possível comparar um número ilimitado de segmentos na visualização de Fallout.

1. Selecione os segmentos que deseja comparar no painel [!UICONTROL Segmentos] à esquerda. Em nosso exemplo, selecionamos dois segmentos: usuários dos EUA e usuários de fora dos EUA.
1. Arraste-os à área de Segmento na parte superior.

   ![](assets/segment-drop.png)

1. Opcional: você pode manter “Todas as visitas” como contêiner padrão ou excluí-lo.

   ![](assets/seg-compare.png)

1. Agora você pode comparar o fallout nos dois segmentos, como onde um segmento supera outro, ou outros insights.

