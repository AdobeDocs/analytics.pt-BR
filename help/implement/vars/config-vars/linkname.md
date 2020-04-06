---
title: linkName
description: Defina o nome de ocorrência do link personalizado.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use the `linkName` variable to determine the dimension value of custom links, download links, or exit links when running the next [`tl()`](../functions/tl-method.md) method.

Se essa variável estiver em branco, o AppMeasurement reverterá para a variável [`linkURL`](linkurl.md).

## Nome do link no Adobe Experience Platform Launch

Você pode definir o campo Nome do link ao configurar uma regra para enviar um beacon.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Under [!UICONTROL Actions], click the &#39;+&#39; icon
5. Set the [!UICONTROL Extension] dropdown to Adobe Analytics, and the [!UICONTROL Action Type] to Send Beacon.
6. Click the `s.tl()` radio button which reveals the [!UICONTROL Link Name] field.

## s.linkName no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkName` é uma cadeia de caracteres que determina o valor da dimensão de links personalizados, links de download ou links de saída (dependendo do que é o [`s.linkType`](linktype.md)). Pode conter até 100 bytes.

>[!TIP] Essa variável é o terceiro parâmetro do `tl()` método e geralmente não precisa ser definida como uma variável independente. However, you can use the `linkName` variable if you do not want to set values as arguments in the `tl()` method.

```js
s.linkName = "Example custom link";
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
