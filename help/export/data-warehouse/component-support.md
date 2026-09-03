---
title: Suporte a componentes no Data Warehouse
description: Saiba quais dimensões e métricas estão disponíveis ao criar uma solicitação do Data Warehouse, quais não estão disponíveis e quais se comportam de forma diferente.
feature: Data Warehouse
exl-id: ce7411a4-a720-47b7-90d5-4d867eff4bae
TQID: https://experienceleague.adobe.com/NhSEyPN3093B9M0SngJluJdZScI2lXvRyHkXQd8gg-4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 362
ht-degree: 11%

---

# Suporte a componentes no Data Warehouse

Esta página descreve as dimensões e métricas que você pode usar ao criar uma solicitação Data Warehouse. As seções incluem quais componentes estão disponíveis, quais não estão disponíveis e quais se comportam de forma diferente das outras ferramentas do Adobe Analytics.

## Dimensões exclusivas do Data Warehouse

As seguintes dimensões podem ser usadas no Data Warehouse, mas não estão disponíveis em outros recursos do Adobe Analytics.

* [[!UICONTROL ID de visitante da Experience Cloud]](/help/components/dimensions/experience-cloud-visitor-id.md)
* [[!UICONTROL Endereço IP]](/help/components/dimensions/ip-address.md)
* [[!UICONTROL URL da página]](/help/components/dimensions/page-url.md)
* [[!UICONTROL ID de compra]](/help/components/dimensions/purchase-id.md)
* [[!UICONTROL ID de visitante]](/help/components/dimensions/visitor-id.md)

## Dimensões não suportadas

As seguintes dimensões não estão disponíveis em relatórios ou segmentos do Data Warehouse:

* [[!UICONTROL AM/PM]](/help/components/dimensions/am-pm.md)
* Todas as dimensões de entrada, exceto [[!UICONTROL Página de entrada]](/help/components/dimensions/entry-dimensions.md) e [[!UICONTROL Página de entrada original]](/help/components/dimensions/entry-dimensions.md), que são permitidas
* Todas as dimensões de saída, exceto [[!UICONTROL Página de Saída]](/help/components/dimensions/exit-dimensions.md) e [[!UICONTROL Link de Saída]](/help/components/dimensions/exit-link.md), que são permitidas
* [[!UICONTROL Profundidade da ocorrência]](/help/components/dimensions/hit-depth.md)
* [[!UICONTROL Frequência de Retorno]](/help/components/dimensions/return-frequency.md)
* [[!UICONTROL Tempo antes do evento]](/help/components/dimensions/time-prior-to-event.md)
* [[!UICONTROL Tempo gasto na página - Classificado]](/help/components/dimensions/time-spent-on-page.md)
* [[!UICONTROL Tempo gasto por visita - Classificado]](/help/components/dimensions/time-spent-per-visit.md)
* [[!UICONTROL Toda a classificação da página de pesquisa]](/help/components/dimensions/all-search-page-rank.md)
* Variáveis de [[!UICONTROL Hierarquia]](/help/components/dimensions/overview.md#retired-dimensions)
* [[!UICONTROL Tipo de ocorrência]](/help/components/dimensions/hit-type.md)
* [[!UICONTROL Pesquisa paga]](/help/components/dimensions/paid-search.md)
* [[!UICONTROL Visitas únicas à página]](/help/components/dimensions/single-page-visits.md)
* [[!UICONTROL Motivo da desativação do rastreamento]](/help/components/dimensions/tracking-opt-out-reason.md)
* [[!UICONTROL Estados dos EUA]](/help/components/dimensions/us-states.md)

Algumas dimensões estão disponíveis em uma solicitação Data Warehouse, mas não podem ser usadas dentro de um segmento. Consulte [Compatibilidade de segmentos do Data Warehouse](segment-compatibility.md) para obter mais informações.

## Dimensões com formatação de data não padrão

As seguintes dimensões baseadas em tempo são suportadas nos relatórios do Data Warehouse, mas sua saída usa um formato não padrão:

* [[!UICONTROL Ano]](/help/components/dimensions/year.md)
* [[!UICONTROL Trimestre]](/help/components/dimensions/quarter.md)
* [[!UICONTROL Mês]](/help/components/dimensions/month.md)
* [[!UICONTROL Semana]](/help/components/dimensions/week.md)
* [[!UICONTROL Dia]](/help/components/dimensions/day.md)
* [[!UICONTROL Hora]](/help/components/dimensions/hour.md)
* [[!UICONTROL Minuto]](/help/components/dimensions/minute.md)

Os valores de data são gerados no formato `1YYMMDDHHMM`:

* **Ano (AA)**: deslocamento em 1900. Adicione `1900` aos três primeiros dígitos. Por exemplo, `125` = ano **2025**.
* **Mês**: baseado em zero. Janeiro = `00`, fevereiro = `01`, ..., dezembro = `11`.

Por exemplo, se o campo Faixa de Datas Semana mostrar `1260901`, o ano será 1900 + 126 = **2026** e o mês será 09 = **outubro**.

## Métricas definidas de forma diferente no Data Warehouse

* **[[!UICONTROL Visitas]](/help/components/metrics/visits.md)**: exclui visitas de cookies não persistentes, diferentemente da métrica Visitas em outras ferramentas do Adobe Analytics.
* **[[!UICONTROL Visitas - Todos os visitantes]](/help/components/metrics/visits.md)**: conta todos os visitantes, incluindo aqueles com cookies não persistentes, tornando-a o equivalente mais próximo da métrica padrão [!UICONTROL Visitas] usada em outro lugar no Adobe Analytics.

## Métricas não suportadas

As seguintes métricas não estão disponíveis no Data Warehouse:

* [[!UICONTROL Rejeições]](/help/components/metrics/bounces.md)
* [[!UICONTROL Entradas]](/help/components/metrics/entries.md)
* [[!UICONTROL Saídas]](/help/components/metrics/exits.md)
* [[!UICONTROL Recarregamentos]](/help/components/metrics/reloads.md)
* [[!UICONTROL Acesso único]](/help/components/metrics/single-access.md)
* Qualquer métrica [[!UICONTROL Tempo gasto]](/help/components/metrics/time-spent.md)
* Qualquer métrica usando um modelo de atribuição de [participação](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md)
