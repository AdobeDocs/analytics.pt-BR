---
title: usePlugins
description: Ative ou desative a função doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 41154580c272514e504c5478215bb67795488de3
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 33%

---

# usePlugins

Se `usePlugins` estiver ativada, a função [`doPlugins()`](../functions/doplugins.md) será executada antes da compilação do AppMeasurement e enviará uma ocorrência para a Adobe. Ative essa variável se você usar a função `doPlugins()`.

## Use o `onBeforeEventSend` retorno de chamada usando o SDK da Web

Embora o SDK da Web não tenha um booleano para lidar com a execução de lógica adicional antes que os dados sejam enviados para o Adobe, você pode registrar a variável `onBeforeEventSend` retorno de chamada para modificar dados. Consulte [Modificação global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do SDK da Web para obter mais informações.

## Usar plug-ins usando a extensão Adobe Analytics

O Adobe fornece uma extensão chamada &quot;Plug-ins comuns do Analytics&quot; que permite que você chame a maioria das vezes [Plug-ins](../plugins/impl-plugins.md). Instale a extensão e chame o plug-in desejado em uma regra.

Se o plug-in desejado não estiver incluído na extensão do Adobe, use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.usePlugins no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.usePlugins` é do tipo booleano e determina se o AppMeasurement chama a função `doPlugins()`. O valor padrão é `false`. Defina essa variável como `true` se você usar a função `doPlugins()` na implementação.

```js
s.usePlugins = true;
```
