---
title: Analisar dados afetados por eventos
description: Entenda como os dados impactados por um evento contribuem para a qualidade geral dos dados.
translation-type: tm+mt
source-git-commit: 09c7c1f4b4a6f67243cc72c642fd83a75406fb76

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

## Usar um evento de calendário no Relatórios e análises

Se você usar o Relatórios e análises, poderá usar um evento [de](/help/components/t-calendar-event.md) calendário para realçar os dias afetados em qualquer relatório de tendências. Este método não se aplica à área de trabalho de Análise.

1. Navegue até **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**.
2. Insira o título desejado, o intervalo de datas e o texto da nota.
3. Clique em **[!UICONTROL Save]**.

![evento do calendário](assets/exclude_calendar_event.jpg)
