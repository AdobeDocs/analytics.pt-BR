---
title: eventos de página
description: O número de ações de rastreamento de link acionadas.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# eventos de página

A métrica &#39;eventos de página&#39; mostra o número de vezes que qualquer chamada de rastreamento de link foi feita. Essa métrica é útil quando você deseja entender quais páginas têm o conteúdo mais envolvente. A medição para essa métrica é mais valiosa quando um visitante pode executar uma ação na página sem navegar até uma nova página.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) em um conjunto de relatórios. Todos os tipos de links estão incluídos (links personalizados, links de download e links de saída). Ela não inclui chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparar a métricas semelhantes

* **eventos de página x visualizações[de](page-views.md)**página: Os eventos de página contam o número de chamadas de rastreamento de link (`tl()`) e excluem chamadas de rastreamento de visualização de página (`t()`). visualizações de página é o oposto; conta o número de chamadas de rastreamento de visualização da página e exclui os links.
