---
title: Analisar dados afetados por eventos
description: Entenda como os dados afetados por um evento contribuem para a qualidade geral dos dados.
translation-type: ht
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# Analisar dados afetados por eventos

Às vezes, um evento pode afetar a qualidade dos dados em sua organização. Alguns exemplos:

* Um bot enviando dados atípicos, como milhões de dólares em receita
* Sua organização enviou uma atualização ao site que afetou negativamente a implementação do Analytics
* Outros problemas que afetam a qualidade ou a integridade dos dados

Se o seu site tiver algum tipo de problema de qualidade de dados, você pode excluí-lo dos relatórios para evitar tomar decisões comerciais com base neles. Use essas seções para medir o impacto do evento em seus dados e determinar como você deseja continuar.

## Determine a causa de um evento

Se não tiver certeza do motivo pelo qual você vê um pico ou uma queda nos dados, consulte [Solução de problemas de picos/quedas nos dados](spikes-drops.md).

## Analisar e excluir dados usando a segmentação

O Adobe Analytics oferece uma maneira simples e eficiente de se concentrar nos dados ou excluí-los usando a segmentação. Você pode usar dimensões de intervalo de datas dentro de segmentos para filtrar ou se concentrar nessas datas específicas. Consulte [Excluir datas específicas na análise](segments.md).

## Comparar um evento a intervalos de datas anteriores

Se quiser saber mais sobre o impacto que um evento teve nos seus dados ao longo do tempo, use a comparação de datas no Analysis Workspace. Esse recurso permite comparar os dados dia a dia, semana a semana ou mês a mês para ver a comparação com os intervalos anteriores. Você pode usar essa comparação para determinar o quanto um evento afeta as tendências. Consulte [Comparar datas afetadas por um evento a intervalos anteriores](compare-dates.md).

## Derivar dados usando métricas calculadas

Depois de criar segmentos e usar a comparação de datas, você pode combinar ambos os conceitos para corrigir dados de tendência usando métricas calculadas. Inclua os segmentos em uma métrica calculada e multiplique os dias afetados pelo deslocamento encontrado ao comparar datas. Consulte [Derivar dados afetados pelos eventos](calcmetrics.md).

## Comunicar o impacto aos usuários em sua organização

Quando estiver preparado para lidar com um evento, você poderá [se comunicar com os usuários em sua organização](communicate.md). A Adobe oferece vários locais dentro do Analytics onde você pode colocar texto para comunicar aos usuários o que aconteceu e quais componentes eles podem usar.

## Vídeo

Este vídeo aborda cada uma das etapas acima.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12&captions=por_br)

* **0:27**: Excluir dados usando a segmentação
* **2:55**: Comparar um evento a intervalos anteriores
* **8:42**: Derivar dados usando métricas calculadas
* **11:46**: Comunicar o impacto aos usuários
