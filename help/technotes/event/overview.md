---
title: Analisar dados afetados por eventos
description: Entenda como os dados afetados por um evento contribuem para a qualidade geral dos dados.
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Curate and Share
TQID: https://experienceleague.adobe.com/DJoJwtp9CkgrCfA1DwW8rKX2x3ssfzLCo7vCfhdLusg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 91%

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

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analisar e comunicar variações nos seus dados](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

* **0:27**: excluir dados usando a segmentação
* **2:55**: Comparar um evento a intervalos anteriores
* **8:42**: derivar dados usando métricas calculadas
* **11:46**: Comunicar o impacto aos usuários

>[!ENDSHADEBOX]


