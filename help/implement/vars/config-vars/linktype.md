---
title: linkType
description: Use a variável linkType para determinar a dimensão de rastreamento de link à qual a ocorrência pertence.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkType

As ocorrências de rastreamento de link podem preencher uma das três dimensões:

* links personalizados
* Links de saída
* Links de download

Use a variável `linkType` para determinar qual dimensão você deseja preencher ao executar a próxima função [`tl()`](../functions/tl-method.md).

## Tipo de link no Adobe Experience Platform Launch

Defina o tipo de link ao configurar uma regra para enviar um beacon.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Type] dropdown.

Você pode definir essa lista suspensa como [!UICONTROL Custom Link], [!UICONTROL Download Link]ou [!UICONTROL Exit Link].

## s.linkType no AppMeasurement e editor de código personalizado do Launch

A variável `s.linkType` é uma string que aceita um de três valores com um caractere: `o`, `d` ou `e`. If a `tl()` method is called without a link type, it defaults to Custom link.

* `o` - Links personalizados
* `d` - Links de download
* `e` - Links de saída

>[!TIP] Essa variável é o segundo parâmetro do `tl()` método e geralmente não precisa ser definida como uma variável independente. However, you can use the `linkType` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkType = "e";
```

## Exemplo

As duas chamadas de rastreamento de link de exemplo a seguir são funcionalmente idênticas. São métodos diferentes para disparar a mesma ocorrência de rastreamento de link.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
