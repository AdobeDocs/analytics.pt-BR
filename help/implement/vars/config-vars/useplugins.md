---
title: usePlugins
description: Ative ou desative a função doPlugins().
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# usePlugins

Se `usePlugins` estiver ativada, a `doPlugins()` função será executada antes da compilação do AppMeasurement e enviará uma ocorrência para a Adobe. Ative essa variável se você usar a `doPlugins()` função.

## Usar plug-ins no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.usePlugins no editor de código personalizado do AppMeasurement e Launch

A `s.usePlugins` variável é um booliano que determina se o AppMeasurement chama a `doPlugins()` função. Its default value is `false`. Defina essa variável para `true` se você usar a `doPlugins()` função na implementação.

```js
s.usePlugins = true;
```
