---
title: dynamicAccountMatch
description: A variável dynamicAccountMatch determina o valor a ser observado nas contas dinâmicas.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 100%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem com as tags na Adobe Experience Platform.

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
