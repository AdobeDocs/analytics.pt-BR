---
title: Util.getQueryParam
description: Retorna o valor de um parâmetro da string de consulta.
feature: Variables
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 80%

---

# Util.getQueryParam

Parâmetros de string de consulta em um URL do navegador frequentemente contêm dados importantes para o Analytics. Use o método `Util.getQueryParam()` para recuperar dados da string de consulta.

## Obter dados de parâmetro da string de consulta usando a extensão Adobe Analytics e a extensão Web SDK

É possível obter dados de parâmetro da string de consulta definindo valores em elementos de dados.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Elementos de dados] e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina as [!UICONTROL Extensão] lista suspensa para **[!UICONTROL Núcleo]** e o [!UICONTROL Tipo de elemento de dados] para **[!UICONTROL Parâmetro da string de consulta]**.
5. Insira o parâmetro da string de consulta no campo de texto.

O valor do parâmetro da string de consulta é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir as variáveis desejadas.

## s.Util.getQueryParam() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `s.Util.getQueryParam()` para recuperar um valor de string de consulta do URL do navegador. O argumento de string que contém um parâmetro de string de consulta é obrigatório. Esse método retorna uma string, que pode ser atribuída às variáveis do Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Um segundo argumento opcional permite que você especifique a string na qual serão verificados os parâmetros da string de consulta. Por padrão, o utilitário consulta o URL do navegador.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Um terceiro argumento opcional permite personalizar o delimitador da string de consulta. O valor padrão é `&`. É possível alterar esse valor se a string de consulta usar um delimitador diferente.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>Um plug-in semelhante com o nome [`s.getQueryParam`](../plugins/getqueryparam.md) está disponível. Esse plug-in contém recursos mais avançados, mas também é mais complexo e não faz parte do AppMeasurement por padrão.
