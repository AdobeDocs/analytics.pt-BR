---
title: dynamicAccountSelection
description: A variável dynamicAccountSelection ativa ou desativa a seleção de conta dinâmica.
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '85'
ht-degree: 100%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

A variável `dynamicAccountSelection` é um booleano que determina se a seleção dinâmica da conta é usada.

Se definida como `true`, o arquivo JavaScript procurará `dynamicAccountMatch` e `dynamicAccountList`.

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
