---
title: URL da página
description: O URL da página.
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---

# URL da página

A dimensão “URL da página” lista os URLs do site.

>[!IMPORTANT]
>
>Essa dimensão só está disponível na Data Warehouse. Se quiser usar uma dimensão de URL em outras soluções do Analytics, considere copiar o valor em uma [eVar](evar.md) em cada ocorrência.

## Preencher esta dimensão com dados

Essa dimensão recupera dados de [`g` e `-g` sequências de consulta](/help/implement/validate/query-parameters.md) em [Chamadas de exibição de página (`t()`)](/help/implement/vars/functions/t-method.md). [As chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) sempre removem essa dimensão, mesmo se a sequência de consulta `g` existe.

Às vezes, os URLs têm mais de 255 bytes. O AppMeasurement usa o parâmetro da string de consulta `g` para os primeiros 255 bytes do URL em solicitações de imagem. Se um URL tiver mais de 255 bytes, o restante do URL será armazenado no parâmetro da string de consulta `-g`. As strings de protocolo e de consulta no URL são incluídas nesta variável.

O AppMeasurement coleta automaticamente esses dados com base no URL da página. Você pode substituir o valor coletado usando a variável [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Preencher uma eVar com URL

A Adobe recomenda configurar uma eVar para a sequência de caracteres associada `window.location.hostname + window.location.pathname`. Normalmente, essa sequência de caracteres funciona melhor do que `window.location.href` porque ela omite protocolos, sequências de consulta e tags de âncora.

Para a eVar corresponder exatamente à dimensão “URL da página&#39;” no Data Warehouse, é possível utilizar [variáveis dinâmicas](/help/implement/vars/page-vars/dynamic-variables.md) e definir a eVar como `D=g` em cada ocorrência.

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas no site.
