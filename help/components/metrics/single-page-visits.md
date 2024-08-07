---
title: Visitas em única página (métricas)
description: O número de vezes que o item de dimensão “Página” não foi alterado em uma visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 84%

---

# Visitas em única página

*Esta página de ajuda descreve como a dimensão “Visitas em única página” funciona como uma métrica. Consulte a dimensão [Visitas em única página](../dimensions/single-page-visits.md) para obter mais informações.*

A [!UICONTROL Visitas em única página] [métrica](overview.md) mostra o número de visitas em que o item de dimensão [Página](../dimensions/page.md) continha apenas um único valor único para toda a visita. Essa métrica é útil no contexto de dimensões em que você deseja ver as visitas curtas, mas não tem regras tão rigorosas quanto [[!UICONTROL Rejeições]](bounces.md).

## Como essa métrica é calculada

Essa métrica conta o número de visitas em que o item de dimensão [!UICONTROL Página] continha apenas um valor único exclusivo para toda a visita. Se um visitante recarregar a página ou acionar chamadas de rastreamento de link, ainda será contado como uma visita de página única. Assim que a dimensão Página mudar para um segundo valor único, a visita não se qualificará mais como uma visita de página única.

Consulte [Acesso único](single-access.md) para obter uma comparação entre as métricas.

## Contar instâncias repetidas

Esta definição especifica se as instâncias repetidas são contadas nos relatórios. Para obter mais informações, consulte [Contar instâncias repetidas](/help/components/metrics/count-repeat-instances.md).
