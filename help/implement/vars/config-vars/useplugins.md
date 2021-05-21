---
title: usePlugins
description: Ative ou desative a função doPlugins().
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '95'
ht-degree: 100%

---

# usePlugins

Se `usePlugins` estiver ativada, a função [`doPlugins()`](../functions/doplugins.md) será executada antes da compilação do AppMeasurement e enviará uma ocorrência para a Adobe. Ative essa variável se você usar a função `doPlugins()`.

## Usar plug-ins no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.usePlugins no AppMeasurement e no editor de código personalizado do Launch

A variável `s.usePlugins` é do tipo booleano e determina se o AppMeasurement chama a função `doPlugins()`. O valor padrão é `false`. Defina essa variável como `true` se você usar a função `doPlugins()` na implementação.

```js
s.usePlugins = true;
```
