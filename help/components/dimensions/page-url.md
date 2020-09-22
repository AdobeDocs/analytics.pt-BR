---
title: URL da página
description: O URL da página.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 69%

---


# URL da página

A dimensão “URL da página” lista os URLs do site.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse. Se você quiser usar uma dimensão de URL em outras soluções do Analytics, considere copiar o valor em um [eVar](evar.md) em cada ocorrência.

## Preencher esta dimensão com dados

This dimension retrieves data from the [`g` and `-g` query strings](/help/implement/validate/query-parameters.md) in [Page view calls (`t()`)](/help/implement/vars/functions/t-method.md). [As chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) sempre removem essa dimensão, mesmo se a sequência de caracteres do `g` query existir.

Às vezes, os URLs têm mais de 255 bytes. O AppMeasurement usa o parâmetro da string de consulta `g` para os primeiros 255 bytes do URL em solicitações de imagem. Se um URL tiver mais de 255 bytes, o restante do URL será armazenado no parâmetro da string de consulta `-g`. As strings de protocolo e de consulta no URL são incluídas nesta variável.

O AppMeasurement coleta automaticamente esses dados com base no URL da página. Você pode substituir o valor coletado usando a [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variável.

## Preencher uma eVar com URL

A Adobe recomenda configurar uma eVar para a sequência de caracteres associada `window.location.hostname + window.location.pathname`. Normalmente, essa sequência de caracteres funciona melhor do que `window.location.href` porque ela omite protocolos, sequências de consulta e tags de âncora.

Para a eVar corresponder exatamente à dimensão “URL da página&#39;” no Data Warehouse, é possível utilizar [variáveis dinâmicas](/help/implement/vars/page-vars/dynamic-variables.md) e definir a eVar como `D=g` em cada ocorrência.

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas no site.
