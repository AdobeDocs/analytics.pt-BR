---
title: usePlugins
description: Ative ou desative a função doPlugins().
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 34%

---

# usePlugins

Se `usePlugins` estiver ativada, a função [`doPlugins()`](../functions/doplugins.md) será executada antes da compilação do AppMeasurement e enviará uma ocorrência para a Adobe. Ative essa variável se você usar a função `doPlugins()`.

## Usar o retorno de chamada `onBeforeEventSend` usando o SDK da Web

Embora o SDK da Web não tenha um booliano para lidar com a execução de lógica adicional antes que os dados sejam enviados para o Adobe, você pode registrar a chamada de retorno `onBeforeEventSend` para modificar dados. Consulte [Modificando eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=pt-BR#modifying-events-globally) na documentação do SDK da Web para obter mais informações.

## Usar plug-ins usando a extensão Adobe Analytics

O Adobe fornece uma extensão chamada &#39;Plug-ins comuns do Analytics&#39;, que permite que você chame a maioria dos [Plug-ins](../plugins/impl-plugins.md). Instale a extensão e chame o plug-in desejado em uma regra.

Se o plug-in desejado não estiver incluído na extensão Adobe, use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.usePlugins no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.usePlugins` é do tipo booleano e determina se o AppMeasurement chama a função `doPlugins()`. O valor padrão é `false`. Defina essa variável como `true` se você usar a função `doPlugins()` na implementação.

```js
s.usePlugins = true;
```
