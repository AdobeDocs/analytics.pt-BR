---
title: Analisar dados afetados por eventos
description: Entenda como os dados impactados por um evento contribuem para a qualidade geral dos dados.
translation-type: tm+mt
source-git-commit: 6cca683836480f707fe18b5ee8d70b26ee5f54b0

---


# Analisar dados afetados por eventos

Às vezes, um evento pode afetar a qualidade dos dados em sua organização. São exemplos:

* Um robô enviando dados mais antigos, como milhões de dólares em receita
* Sua organização enviou uma atualização ao seu site que afetou negativamente a implementação do Analytics
* Outros problemas que afetam a qualidade ou integridade dos dados

Se o site detectou problemas de qualidade de dados, problemas de implementação ou outras lacunas nos dados, você pode excluí-lo do relatórios para evitar tomar decisões sobre dados parciais. Use essas seções para medir o impacto do evento em seus dados e determinar como você deseja continuar.

## Analisar e excluir dados usando a segmentação

O Adobe Analytics oferta uma maneira simples e robusta de focar ou excluir dados usando a segmentação. Você pode usar dimensões de intervalo de datas dentro de segmentos para filtrar ou focar nessas datas específicas. Consulte [Excluir datas específicas na análise](/help/components/c-segmentation/use-cases/exclude-date-range.md) no guia do usuário Componentes.

## Comparar um evento a intervalos de datas anteriores

Se quiser saber mais sobre o impacto que um evento teve nos seus dados ao longo do tempo, use a comparação de datas na área de trabalho da Análise. Esse recurso permite que você compare os dados dia a dia, semana a semana ou mês a mês para ver a comparação com os intervalos anteriores. Você pode então usar essa comparação para determinar o quanto um evento afeta as tendências. Consulte [Comparar datas afetadas por um evento a intervalos](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) anteriores no guia do usuário Analisar.

## Derivar dados usando métricas calculadas

Depois de criar segmentos e usar a comparação de datas, você pode combinar ambos os conceitos para corrigir dados de tendência usando métricas calculadas. Inclua os segmentos em uma métrica calculada e multiplique os dias afetados pelo deslocamento encontrado ao comparar datas. Consulte [Derivar dados afetados pelos eventos](/help/components/c-calcmetrics/cm-events.md) no guia do usuário Componentes.

## Comunicar o impacto aos usuários em sua organização

Quando estiver preparado para lidar com um evento, você poderá [se comunicar com os usuários em sua organização](event/event-communicate.md). A Adobe oferta vários locais no Analytics onde você pode colocar o texto para comunicar aos usuários o que aconteceu e quais componentes eles podem usar.

## Vídeo

Este vídeo percorre cada uma das etapas acima.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)
