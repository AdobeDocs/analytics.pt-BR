---
title: Eventos de página
description: O número de ações de rastreamento de link acionadas.
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---


# Eventos de página

A métrica “Eventos de página” exibe o número de vezes que qualquer chamada de rastreamento de link foi feita. Essa métrica é útil para entender quais páginas têm o conteúdo mais envolvente. A medição dessa métrica é mais útil quando há a possibilidade de um visitante executar uma ação na página sem navegar até uma nova página.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) em um conjunto de relatórios. Todos os tipos de links estão incluídos (links personalizados, links de download e links de saída). Ela não inclui chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparar a métricas semelhantes

* **Eventos de página versus[Visualizações de página](page-views.md)**: a métrica Eventos de página conta o número de chamadas de rastreamento de link (`tl()`) e excluem chamadas de rastreamento de visualização de página (`t()`). A métrica Visualizações de página é o oposto; ela conta o número de chamadas de rastreamento de visualização da página e exclui as de links.
