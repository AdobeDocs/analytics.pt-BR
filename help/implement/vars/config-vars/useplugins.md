---
title: usePlugins
description: Ative ou desative a função doPlugins().
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# usePlugins

Se `usePlugins` estiver ativada, a [`doPlugins()`](../functions/doplugins.md) função será executada antes da compilação do AppMeasurement e enviará uma ocorrência para a Adobe. Ative essa variável se você usar a `doPlugins()` função.

## Usar plug-ins no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.usePlugins no editor de código personalizado do AppMeasurement e Launch

A `s.usePlugins` variável é um booliano que determina se o AppMeasurement chama a `doPlugins()` função. Its default value is `false`. Defina essa variável para `true` se você usar a `doPlugins()` função na implementação.

```js
s.usePlugins = true;
```
