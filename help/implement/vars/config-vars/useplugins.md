---
title: usePlugins
description: Ative ou desative a função doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 100%

---

# usePlugins

Se `usePlugins` estiver ativada, a função [`doPlugins()`](../functions/doplugins.md) será executada antes da compilação do AppMeasurement e enviará uma ocorrência para a Adobe. Ative essa variável se você usar a função `doPlugins()`.

## Usar plug-ins com tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.usePlugins no AppMeasurement e no editor de código personalizado do 

A variável `s.usePlugins` é do tipo booleano e determina se o AppMeasurement chama a função `doPlugins()`. O valor padrão é `false`. Defina essa variável como `true` se você usar a função `doPlugins()` na implementação.

```js
s.usePlugins = true;
```
