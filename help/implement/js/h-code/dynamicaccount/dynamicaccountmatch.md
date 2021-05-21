---
title: dynamicAccountMatch
description: A variável dynamicAccountMatch determina o valor a ser observado nas contas dinâmicas.
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '126'
ht-degree: 100%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

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
