---
title: Toda a classificação da página de pesquisa
description: Determine em qual página de um mecanismo de pesquisa um visitante clicou até seu site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Toda a classificação da página de pesquisa

A dimensão &#39;Toda classificação de página de pesquisa&#39; fornece informações sobre qual página de resultados de pesquisa um visitante clicou no site. Por exemplo, se o site for exibido na segunda página dos resultados de pesquisa de um mecanismo de pesquisa, o item de dimensão para essa variável será &quot;Página de pesquisa 2&quot;.

## Preencher esta dimensão com dados

Para que essa dimensão funcione apenas, é necessário que seu conjunto de relatórios tenha filtros [de URL](/help/admin/admin/internal-url-filter-admin.md) internos configurados corretamente. O AppMeasurement preenche automaticamente essa dimensão sem qualquer alteração no código de implementação.

## Itens de dimensão

Se um visitante clicar até seu site a partir de um mecanismo de pesquisa, o valor dessa dimensão será &quot;Página de pesquisa&quot; seguido do número de página pelo qual ele clicou. Se uma ocorrência não se originar de um mecanismo de pesquisa, o valor dessa dimensão será &quot;Não especificado&quot;.
