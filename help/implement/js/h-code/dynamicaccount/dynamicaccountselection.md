---
title: dynamicAccountSelection
description: A variável dynamicAccountSelection ativa ou desativa a seleção de conta dinâmica.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas de AppMeasurements atuais ou com a Coleção de dados da Adobe Experience Platform.

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
