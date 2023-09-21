---
title: Instâncias
description: O número de ocorrências a que uma variável foi definida (e não persistiu).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 57%

---

# Instâncias

As &quot;Instâncias&quot; [métrica](overview.md) mostra o número de vezes que uma dimensão foi explicitamente definida em uma solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem itens de dimensão após a ocorrência em que estão definidas. Essa métrica é útil quando você deseja ver o número de vezes que um item de dimensão foi definido sem as ocorrências nas quais esse valor persistiu.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua somente ocorrências que definam explicitamente um item de dimensão na solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Métricas como [Visualizações de página](page-views.md) e [Ocorrências](occurrences.md) contam valores iniciais e persistentes. Essa métrica não conta valores persistentes.

Por exemplo, um visitante chega ao seu site e usa pesquisa interna. Você rastreia a pesquisa interna em eVar 1. Depois de usar a pesquisa interna uma vez, eles visitam mais cinco páginas antes de sair.

Ao visualizar um relatório no Espaço de trabalho, você veria uma instância do eVar1 e seis ocorrências. A instância acionada na página de resultados da pesquisa, enquanto as ocorrências contavam o valor inicial, bem como os valores persistentes.
