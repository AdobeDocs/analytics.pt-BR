---
title: linkType
description: Use a variável linkType para determinar a dimensão de rastreamento de link à qual a ocorrência pertence.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

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
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e Enviar beacon no [!UICONTROL Tipo de ação].
6. Clique no botão de opção `s.tl()`, que revela a lista suspensa [!UICONTROL Tipo de link].

É possível definir essa lista suspensa como [!UICONTROL Link personalizado], [!UICONTROL Link de download] ou [!UICONTROL Link de saída].

## s.linkType no AppMeasurement e editor de código personalizado do Launch

A variável `s.linkType` é uma string que aceita um de três valores com um caractere: `o`, `d` ou `e`. Se um método `tl()` for chamado sem um tipo de link, o padrão será Link personalizado.

* `o` - Links personalizados
* `d` - Links de download
* `e` - Links de saída

>[!TIP]
>
>Essa variável é o segundo parâmetro do método `tl()` e geralmente não precisa ser definida como uma variável independente. No entanto, você pode usar a variável `linkType` se não quiser definir valores como argumentos no método `tl()`.

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
