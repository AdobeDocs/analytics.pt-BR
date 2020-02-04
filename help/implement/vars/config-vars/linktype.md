---
title: linkType
description: Use a variável linkType para determinar a dimensão de rastreamento de link à qual a ocorrência pertence.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkType

As ocorrências de rastreamento de link podem preencher uma das três dimensões:

* links personalizados
* Links de saída
* Links de download

Use a `linkType` variável para determinar qual dimensão você deseja preencher ao executar a próxima `tl()` função.

## Tipo de link no Adobe Experience Platform Launch

Defina o tipo de link ao configurar uma regra para enviar um beacon.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone &#39;+&#39;
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como Enviar beacon.
6. Clique no botão de `s.tl()` opção que revela a lista suspensa Tipo [!UICONTROL de] link.

É possível definir essa lista suspensa como Link personalizado, Link [!UICONTROL de]download ou Link [!UICONTROL de]saída.

## s.linkType no AppMeasurement e Iniciar editor de código personalizado

A `s.linkType` variável é uma string que aceita um dos três valores de caractere único: `o`, `d`ou `e`. Se uma `tl()` função for chamada sem um tipo de link, o padrão será Link personalizado.

* `o` - links personalizados
* `d` - Links de download
* `e` - Links de saída

> [!TIP] Essa variável é o segundo parâmetro da `tl()` função e geralmente não precisa ser definida como uma variável independente. No entanto, você pode usar a `linkType` variável se não quiser definir valores como argumentos na `tl()` função.

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
