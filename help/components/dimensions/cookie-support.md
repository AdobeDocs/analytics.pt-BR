---
title: Suporte a cookies
description: Determina se o navegador aceita cookies.
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 89%

---

# Suporte a cookies

A dimensão “Suporte a cookies” informa se o navegador aceita cookies para uma determinada ocorrência. É útil determinar a proporção de visitantes que usam navegadores que aceitam cookies e aqueles que os desabilitam intencionalmente.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da [`k`sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement tenta definir um cookie chamado `s_cc`, e então detecta se o cookie existe. O resultado é o valor do parâmetro da sequência de consulta `Y` (se o navegador aceitar e tiver cookies ativados) ou `N` (se o navegador tiver cookies desativados). Se você usar o AppMeasurement (por exemplo, por meio de tags no Adobe Experience Platform), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o `k` parâmetro da sequência de consulta em cada ocorrência com um valor de `Y` ou `N`.

## Itens de dimensão

Os itens de dimensão incluem `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: o navegador aceita cookies e os habilita.
* **`Disabled`**: o navegador não aceita cookies ou o visitante os desabilitou.
* **`Unknown`**: o AppMeasurement não pôde determinar o suporte a cookies. A sequência de consulta `k` não estava presente na solicitação de imagem.
