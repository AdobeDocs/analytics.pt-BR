---
title: Eventos de página
description: O número de ações de rastreamento de link acionadas.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
TQID: https://experienceleague.adobe.com/tOEidVQjv4ynokjH53SEdKeOHiqwZn02WZDalUESsAs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 210
ht-degree: 33%

---

# Eventos de página

A [métrica](overview.md) de &#39;Eventos de página&#39; mostra o número de vezes que qualquer chamada de rastreamento de link foi feita. Essa métrica é útil para entender quais páginas têm o conteúdo mais envolvente. A medição dessa métrica é mais útil quando há a possibilidade de um visitante executar uma ação na página sem navegar até uma nova página.

Por exemplo, em uma jornada típica de um site de comércio eletrônico, um visitante pode ter várias interações em uma única página. Uma implementação típica do Analytics tem essas interações configuradas como uma chamada de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)), enquanto uma chamada de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)) é reservada para o carregamento da página inicial. Esse método de implementação fornece um rastreamento de eventos aprimorado que fornece à insight informações sobre quais interações ocorrem antes de um visitante continuar sua jornada.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) em um conjunto de relatórios. Todos os tipos de links estão incluídos nesta métrica, especificamente [Links personalizados](../dimensions/custom-link.md), [Links de download](../dimensions/download-link.md) e [Links de saída](../dimensions/exit-link.md). Ela não inclui chamadas de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparar a métricas semelhantes

* **Eventos de página vs. [Exibições de página](page-views.md)**: a métrica Eventos de página conta o número de chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) e excluem chamadas de rastreamento de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)). As exibições de página são o oposto; conta o número de chamadas de rastreamento de exibição de página e exclui os links.
