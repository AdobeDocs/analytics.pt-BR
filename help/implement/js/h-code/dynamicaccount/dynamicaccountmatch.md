---
title: dynamicAccountMatch
description: A variável dynamicAccountMatch determina o valor a ser observado nas contas dinâmicas.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] As contas dinâmicas só são suportadas com implementações JavaScript herdadas (Código H). Essas variáveis não são suportadas nas bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

A `dynamicAccountMatch` variável é o valor que `dynamicAccountList` observa e compara seus valores. Se não `dynamicAccountSelection` estiver definida como `true`, essa variável será ignorada.

Se essa variável não estiver definida, seu valor padrão será `window.location.host`.

## Sintaxe

```js
s.dynamicAccountMatch=[DOM object]
```

## Exemplos

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Observações adicionais

* As páginas salvas em um disco rígido não têm várias `location` variáveis definidas (por exemplo, `location.host` está em branco). Verifique se `s_account` contém um conjunto de relatórios padrão.
* Quando uma página é traduzida por um mecanismo de tradução baseado na Web, como o Google, a seleção de conta dinâmica não funciona conforme projetado. For more precise tracking, populate the `s_account` variable server-side.
