---
title: URL da página
description: O URL da página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 92%

---


# URL da página

A dimensão “URL da página” lista os URLs do site.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse. Para utilizar uma dimensão “URL” em outras soluções do Analytics, utilize uma [eVar](evar.md).

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`g` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Preencher uma eVar com URL

A Adobe recomenda configurar uma eVar para a sequência de caracteres associada `window.location.hostname + window.location.pathname`. Normalmente, essa sequência de caracteres funciona melhor do que `window.location.href` porque ela omite protocolos, sequências de consulta e tags de âncora.

Para a eVar corresponder exatamente à dimensão “URL da página&#39;” no Data Warehouse, é possível utilizar [variáveis dinâmicas](/help/implement/vars/page-vars/dynamic-variables.md) e definir a eVar como `D=g` em cada ocorrência. Observe que esse método não funciona para ocorrências de link personalizado, pois o URL da página é removido para todas as chamadas de [`tl()`](/help/implement/vars/functions/tl-method.md).

## itens de Dimension

Os itens de Dimension incluem os URLs das páginas do site.
