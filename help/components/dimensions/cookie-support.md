---
title: Suporte a cookies
description: Determina se o navegador suporta cookies.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---


# Suporte a cookies

A dimensão &#39;Suporte a cookies&#39; relata se o navegador oferece suporte a cookies para uma determinada ocorrência. É útil determinar a proporção de visitantes que usam navegadores que suportam cookies e aqueles que os desabilitam intencionalmente.

## Preencher esta dimensão com dados

Essa dimensão coleta dados da string [`k` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement tenta definir um cookie chamado `s_cc`, e então detecta se o cookie existe. O resultado é o valor do parâmetro da string de query `Y` (se o navegador suportar e tiver cookies ativados) ou `N` (se o navegador tiver cookies desativados). Se você usar o AppMeasurement (por exemplo, através do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `k` query em cada ocorrência com o valor `Y` ou `N`.

## Valores de dimensão

Os valores de dimensão incluem `Enabled`, `Disabled`e `Unknown`.

* **`Enabled`**: O navegador oferece suporte a cookies e os habilita.
* **`Disabled`**: O navegador não oferece suporte a cookies ou o visitante os desabilitou.
* **`Unknown`**: O AppMeasurement não pôde determinar o suporte a cookies. A cadeia de caracteres do `k` query não estava presente na solicitação de imagem.
