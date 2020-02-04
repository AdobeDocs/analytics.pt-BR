---
title: dynamicAccountSelection
description: A variável dynamicAccountSelection ativa ou desativa a seleção de conta dinâmica.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] As contas dinâmicas só são suportadas com implementações JavaScript herdadas (Código H). Essas variáveis não são suportadas nas bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

A `dynamicAccountSelection` variável é um booliano que determina se a seleção dinâmica da conta é usada.

Se definido como `true`, o arquivo JavaScript procurará `dynamicAccountMatch` e `dynamicAccountList`.

Se definida como `false`, ou se essa variável não estiver definida, as variáveis `dynamicAccountMatch` e `dynamicAccountList` serão ignoradas.

Se essa variável não estiver definida, o valor padrão será `false`.

## Sintaxe

```js
s.dynamicAccountSelection = [boolean];
```

## Exemplo

```js
s.dynamicAccountSelection = true;
```
