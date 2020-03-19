---
title: linkType
description: Use a variável linkType para determinar a dimensão de rastreamento de link à qual a ocorrência pertence.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkType

As ocorrências de rastreamento de link podem preencher uma das três dimensões:

* links personalizados
* Links de saída
* Links de download

Use a `linkType` variável para determinar qual dimensão você deseja preencher ao executar a próxima [`tl()`](../functions/tl-method.md) função.

## Tipo de link no Adobe Experience Platform Launch

Defina o tipo de link ao configurar uma regra para enviar um beacon.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique no ícone &#39;+&#39;
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e a opção [!UICONTROL Action Type] Enviar beacon.
6. Clique no botão de `s.tl()` opção que revela a [!UICONTROL Link Type] lista suspensa.

Você pode definir essa lista suspensa como [!UICONTROL Custom Link], [!UICONTROL Download Link]ou [!UICONTROL Exit Link].

## s.linkType no AppMeasurement e Iniciar editor de código personalizado

A `s.linkType` variável é uma string que aceita um dos três valores de caractere único: `o`, `d`ou `e`. Se um `tl()` método for chamado sem um tipo de link, o padrão será Link personalizado.

* `o` - links personalizados
* `d` - Links de download
* `e` - Links de saída

> [!TIP] Essa variável é o segundo parâmetro do `tl()` método e geralmente não precisa ser definida como uma variável independente. No entanto, você pode usar a `linkType` variável se não quiser definir valores como argumentos no `tl()` método.

```js
s.linkType = "e";
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
