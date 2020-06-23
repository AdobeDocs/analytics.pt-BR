---
title: linkName
description: Defina o nome de ocorrência do link personalizado.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkName

Use a variável `linkName` para determinar o valor da dimensão de links personalizados, links de download ou links de saída ao executar o próximo método [`tl()`](../functions/tl-method.md).

Se essa variável estiver em branco, o AppMeasurement reverterá para a variável [`linkURL`](linkurl.md).

## Nome do link no Adobe Experience Platform Launch

Você pode definir o campo Nome do link ao configurar uma regra para enviar um beacon.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e Enviar beacon como [!UICONTROL Tipo de ação].
6. Clique no botão de opção `s.tl()`, que revela o campo [!UICONTROL Nome do link].

## s.linkName no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkName` é uma cadeia de caracteres que determina o valor da dimensão de links personalizados, links de download ou links de saída (dependendo do que é o [`s.linkType`](linktype.md)). Pode conter até 100 bytes.

>[!TIP] Essa variável é o terceiro parâmetro do método `tl()` e geralmente não precisa ser definida como uma variável independente. No entanto, você pode usar a variável `linkName` se não quiser definir valores como argumentos no método `tl()`.

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
