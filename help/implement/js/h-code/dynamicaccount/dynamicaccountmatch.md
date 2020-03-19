---
title: dynamicAccountMatch
description: A variável dynamicAccountMatch determina o valor a ser observado nas contas dinâmicas.
translation-type: ht
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] As contas dinâmicas só compatíveis com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

A variável `dynamicAccountMatch` é o valor que `dynamicAccountList` observa e compara seus valores. Se `dynamicAccountSelection` não estiver definida como `true`, essa variável será ignorada.

Se essa variável não estiver definida, o valor padrão será `window.location.host`.

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

* As páginas salvas em um disco rígido não têm várias variáveis `location` definidas (por exemplo, `location.host` está em branco). Verifique se `s_account` contém um conjunto de relatórios padrão.
* Quando a página é traduzida por um mecanismo de tradução baseado na Web, como o Google, a Seleção de conta dinâmica não funciona conforme projetado. Para obter um rastreamento mais preciso, preencha o lado do servidor da variável `s_account`.
