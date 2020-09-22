---
title: Suporte a cookies
description: Determina se o navegador aceita cookies.
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '187'
ht-degree: 100%

---


# Suporte a cookies

A dimensão “Suporte a cookies” informa se o navegador aceita cookies para uma determinada ocorrência. É útil determinar a proporção de visitantes que usam navegadores que aceitam cookies e aqueles que os desabilitam intencionalmente.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`k`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement tenta definir um cookie chamado `s_cc`, e então detecta se o cookie existe. O resultado é o valor do parâmetro da sequência de consulta `Y` (se o navegador aceitar e tiver cookies ativados) ou `N` (se o navegador tiver cookies desativados). Se você utilizar o AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará automaticamente. Se você utilizar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o `k` parâmetro da sequência de consulta em cada ocorrência com um valor de `Y` ou `N`.

## Itens de dimensão

Os itens de dimensão incluem `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: o navegador aceita cookies e os habilita.
* **`Disabled`**: o navegador não aceita cookies ou o visitante os desabilitou.
* **`Unknown`**: o AppMeasurement não pôde determinar o suporte a cookies. A sequência de consulta `k` não estava presente na solicitação de imagem.
