---
title: usePlugins
description: Ative ou desative a função doPlugins().
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

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
