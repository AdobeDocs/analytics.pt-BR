---
title: sa
description: Altere o conjunto de relatórios a qualquer momento em sua implementação.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# sa

O `sa` método permite alterar dinamicamente um conjunto de relatórios a qualquer momento na página. Se desejar enviar dados para conjuntos de relatórios diferentes sem um recarregamento de página, você pode usar esse método.

## Usar o método sa no Adobe Experience Platform Launch

Não há uma maneira flexível de alterar o conjunto de relatórios na interface. Você pode definir o conjunto de relatórios na opção Gerenciamento [!UICONTROL de] biblioteca ao configurar a extensão do Adobe Analytics. No entanto, não é possível alterar ou atualizar o conjunto de relatórios usando regras. Se desejar atualizar os valores do conjunto de relatórios depois de definidos, use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.sa() no AppMeasurement e Iniciar editor de código personalizado

Chame o `s.sa()` método para alterar o conjunto de relatórios de destino. Seu único argumento é uma string contendo uma ID de conjunto de relatórios ou várias IDs de conjunto de relatórios delimitadas por uma vírgula. O argumento ID do conjunto de relatórios é obrigatório. Não use espaços no argumento de string.

```js
s.sa("examplersid");
```

## Exemplo

Você pode alterar o conjunto de relatórios se o usuário executar uma ação específica em seu site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
