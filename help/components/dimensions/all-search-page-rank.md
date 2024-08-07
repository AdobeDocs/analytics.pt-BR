---
title: Toda a classificação da página de pesquisa
description: Determine em qual página de um mecanismo de pesquisa um visitante clicou para acessar seu site.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 85%

---

# Toda a classificação da página de pesquisa

A [dimensão](overview.md) de &quot;Toda classificação da página de pesquisa&quot; fornece informações sobre em qual página de resultados de pesquisa um visitante clicou para acessar seu site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será “Página de pesquisa 2”.

## Preencher esta dimensão com dados

Para que essa dimensão funcione, é necessário que seu conjunto de relatórios tenha [Filtros de URL internos](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) configurados corretamente. O AppMeasurement preenche automaticamente essa dimensão sem qualquer alteração no código de implementação.

## Itens de dimensão

Se um visitante clica em seu site a partir de um mecanismo de pesquisa, o valor dessa dimensão é “Página de pesquisa” seguido pelo número da página em que ele clicou. Se uma ocorrência não se originar de um mecanismo de pesquisa, o valor dessa dimensão será “Não especificado”.
