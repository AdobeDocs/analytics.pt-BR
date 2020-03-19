---
title: linkName
description: Defina o nome da ocorrência do link personalizado.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkName

Use a `linkName` variável para determinar o valor da dimensão de links personalizados, links de download ou links de saída ao executar o próximo [`tl()`](../functions/tl-method.md) método.

Se essa variável estiver em branco, o AppMeasurement reverterá para a [`linkURL`](linkurl.md) variável.

## Nome do link no Adobe Experience Platform Launch

Você pode definir o campo de nome do link ao configurar uma regra para enviar um beacon.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique no ícone &#39;+&#39;
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e a opção [!UICONTROL Action Type] Enviar beacon.
6. Clique no botão de `s.tl()` opção que revela o [!UICONTROL Link Name] campo.

## s.linkName no AppMeasurement e Iniciar editor de código personalizado

A `s.linkName` variável é uma string que determina o valor da dimensão para links personalizados, links de download ou links de saída (dependendo do que [`s.linkType`](linktype.md) está). Pode conter até 100 bytes.

> [!TIP] Essa variável é o terceiro parâmetro do `tl()` método e geralmente não precisa ser definida como uma variável independente. No entanto, você pode usar a `linkName` variável se não quiser definir valores como argumentos no `tl()` método.

```js
s.linkName = "Example custom link";
```

## Exemplo

As duas chamadas de rastreamento de link de exemplo a seguir são funcionalmente idênticas. São métodos diferentes para realizar a mesma ocorrência de rastreamento de link.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
