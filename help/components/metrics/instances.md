---
title: Instâncias
description: O número de ocorrências a que uma variável foi definida (e não persistiu).
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '129'
ht-degree: 100%

---

# Instâncias

A métrica “Instâncias” mostra o número de vezes que uma dimensão foi explicitamente definida em uma solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem itens de dimensão após a ocorrência em que estão definidas. Essa métrica é útil quando você deseja ver o número de vezes que um item de dimensão foi definido sem as ocorrências nas quais esse valor persistiu.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua somente ocorrências que definam explicitamente um item de dimensão na solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Métricas como [Visualizações de página](page-views.md) e [Ocorrências](occurrences.md) contam valores iniciais e persistentes. Essa métrica não conta valores persistentes.
