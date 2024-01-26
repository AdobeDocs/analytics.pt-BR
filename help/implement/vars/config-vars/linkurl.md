---
title: linkURL
description: Substitua o URL de link gerado automaticamente que o AppMeasurement usa nas chamadas de rastreamento de link.
feature: Variables
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 75%

---

# linkURL

Sempre que uma chamada de rastreamento de link é enviada para a Adobe, os servidores de coleta de dados detectam automaticamente o URL. Use a variável `linkURL` para substituir o URL detectado.

## Vincular URL usando o SDK da Web

O URL do link é [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) no campo XDM `web.webInteraction.URL`.

## Vincular URL usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.linkURL no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkURL` é uma string que contém o URL do navegador de quando o link foi clicado. Essa variável não preenche nenhuma dimensão disponível no relatório.

```js
s.linkURL = "https://example.com";
```

Se o terceiro argumento do método [tl()](../functions/tl-method.md) não estiver definido, a variável `linkURL` será usada.
