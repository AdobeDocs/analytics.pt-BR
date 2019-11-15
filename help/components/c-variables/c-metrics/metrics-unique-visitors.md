---
description: Na versão 14, um visitante único refere-se a um visitante que visita um site pela primeira vez em um período especificado. Por exemplo, o visitante único pode visitar um site dez vezes em uma semana, mas se o período é semana, um visitante único é contabilizado apenas uma vez naquela semana. Após o final daquela semana, o visitante único pode ser contabilizado novamente para um novo período.
solution: Analytics
title: Visitantes únicos
topic: Metrics
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visitantes únicos

Na versão 14, um visitante único refere-se a um visitante que visita um site pela primeira vez em um período especificado. Por exemplo, o visitante único pode visitar um site dez vezes em uma semana, mas se o período é semana, um visitante único é contabilizado apenas uma vez naquela semana. Após o final daquela semana, o visitante único pode ser contabilizado novamente para um novo período.

## Diferenças entre a versão 14 e 15

Version 14 does not remove duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics from classifications-based reports. Por exemplo, se dois clipes de vídeo compartilhavam a mesma classificação, um único visitante que visualizasse ambos os clipes gerava duas [!UICONTROL Visitas] e [!UICONTROL Visitantes únicos] no relatório baseado em classificação.

A versão 15 remove [!UICONTROL Visitas] e [!UICONTROL Visitantes únicos] do relatório com base em classificação. Essa é uma medida mais precisa de [!UICONTROL Visitas] e [!UICONTROL Visitantes], mas normalmente resulta em uma redução nas suas métricas de [!UICONTROL Visitas] e [!UICONTROL Visitantes únicos] para relatórios baseados em classificação em comparação aos dados coletados antes da atualização.

| Usos | Descrição |
|---|---|
| Tráfego | Um visitante é uma pessoa que entra no site. Não requer um cookie persistente. |
| Conversão | Um visitante é uma pessoa que entra no site. É contado quando um evento relacionado à conversão ou ação ocorre. |
| Ad Hoc Analysis | Um visitante é uma pessoa que entra no site. Não requer um cookie persistente. |

Consulte Relatório de visitantes [únicos - Versão 15 e Análise](/help/components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md)ad hoc.

>[!MORELIKETHIS]
>
>* [Visitantes únicos por dia](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

