---
title: Analisar dados afetados por eventos
description: Entenda como os dados impactados por um evento contribuem para a qualidade geral dos dados.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---


# Analisar dados afetados por eventos

Às vezes, um evento pode afetar a qualidade dos dados em sua organização. São exemplos:

* Um robô enviando dados mais antigos, como milhões de dólares em receita
* Sua organização enviou uma atualização ao seu site que afetou negativamente sua implementação do Analytics
* Outros problemas que afetam a qualidade ou integridade dos dados

Se o seu site tiver algum tipo de problema de qualidade de dados, você pode excluí-lo do relatórios para evitar tomar decisões comerciais sobre ele. Use essas seções para medir o impacto do evento em seus dados e determinar como você deseja continuar.

## Determine a causa de um evento

Se não tiver certeza do motivo pelo qual você vê um pico ou uma queda nos dados, consulte [Solução de problemas de picos/quedas nos dados](spikes-drops.md).

## Analisar e excluir dados usando a segmentação

A Adobe Analytics oferta uma maneira simples e robusta de focar ou excluir dados usando a segmentação. Você pode usar dimensões de intervalo de datas dentro de segmentos para filtrar ou focar nessas datas específicas. See [Exclude specific dates in analysis](segments.md).

## Comparar um evento a intervalos de datas anteriores

Se quiser saber mais sobre o impacto que um evento teve nos seus dados ao longo do tempo, use a comparação de datas no Analysis Workspace. Esse recurso permite que você compare os dados dia a dia, semana a semana ou mês a mês para ver a comparação com os intervalos anteriores. Você pode então usar essa comparação para determinar o quanto um evento afeta as tendências. Consulte [Comparar datas afetadas por um evento a intervalos](compare-dates.md)anteriores.

## Derivar dados usando métricas calculadas

Depois de criar segmentos e usar a comparação de datas, você pode combinar ambos os conceitos para corrigir dados de tendência usando métricas calculadas. Inclua os segmentos em uma métrica calculada e multiplique os dias afetados pelo deslocamento encontrado ao comparar datas. See [Derive data impacted by events](calcmetrics.md).

## Comunicar o impacto aos usuários em sua organização

Quando estiver preparado para lidar com um evento, você poderá [se comunicar com os usuários em sua organização](communicate.md). O Adobe oferta em vários locais no Analytics onde você pode colocar o texto para comunicar aos usuários o que aconteceu e quais componentes eles podem usar.

## Vídeo

Este vídeo percorre cada uma das etapas acima.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Excluir dados usando a segmentação
* **14:55**: Comparar um evento a intervalos anteriores
* **8:42**: Derivar dados usando métricas calculadas
* **11:46**: Comunicar impacto aos usuários
