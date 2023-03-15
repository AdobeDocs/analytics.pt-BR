---
title: dynamicAccountSelection
description: A variável dynamicAccountSelection ativa ou desativa a seleção de conta dinâmica.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem com a Coleção de dados da Adobe Experience Platform.

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
