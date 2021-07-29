---
title: sa
description: Altere o conjunto de relatórios a qualquer momento em sua implementação.
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 94%

---

# sa

O método `sa()` permite alterar dinamicamente e a qualquer momento um conjunto de relatórios na página. Se desejar enviar dados para conjuntos de relatórios diferentes sem um recarregamento de página, você pode usar esse método.

## Usar o método sa usando tags no Adobe Experience Platform

Não há uma maneira flexível de alterar o conjunto de relatórios na interface. É possível definir o conjunto de relatórios na opção [!UICONTROL Gerenciamento de biblioteca] ao configurar a extensão do Adobe Analytics. No entanto, não é possível alterar ou atualizar o conjunto de relatórios usando regras. Se desejar atualizar os valores do conjunto de relatórios depois de definidos, use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.sa() no AppMeasurement e no editor de código personalizado do 

Chame o método `s.sa()` para alterar o conjunto de relatórios de destino. Seu único argumento é uma string contendo uma ID de conjunto de relatórios ou várias IDs de conjuntos de relatórios delimitadas por uma vírgula. O argumento ID de conjunto de relatórios é obrigatório. Não use espaços no argumento em string.

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
