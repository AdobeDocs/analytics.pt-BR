---
title: URL da página
description: O URL da página.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# URL da página

A dimensão &#39;URL da página&#39; lista os URLs do site.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data warehouse. Se quiser usar uma dimensão de URL em outras soluções Analytics, use uma [eVar](evar.md).

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`g` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variável.

## Preencher uma eVar com URL

A Adobe recomenda configurar uma eVar para a string concatenada `window.location.hostname + window.location.pathname`. Normalmente, essa string funciona melhor do que `window.location.href` porque omite tags de protocolo, sequências de query e âncora.

Se desejar que a eVar corresponda exatamente à dimensão &#39;URL da página&#39; na Data warehouse, você pode usar variáveis [](/help/implement/vars/page-vars/dynamic-variables.md) dinâmicas e definir a eVar como `D=g` em cada ocorrência. Observe que esse método não funciona para ocorrências de link personalizado, pois o URL da página é removido para todas as [`tl()`](/help/implement/vars/functions/tl-method.md) chamadas.

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas do site.
