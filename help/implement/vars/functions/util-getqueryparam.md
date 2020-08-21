---
title: Util.getQueryParam
description: Retorna o valor de um parâmetro da string de consulta.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '256'
ht-degree: 100%

---


# Util.getQueryParam

Parâmetros de string de consulta em um URL do navegador frequentemente contêm dados importantes para o Analytics. Use o método `Util.getQueryParam()` para recuperar dados da string de consulta.

## Obter dados de parâmetro da string de consulta no Adobe Experience Platform Launch

É possível obter dados de parâmetro da string de consulta definindo valores em elementos de dados.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Elementos de dados] e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina a lista suspensa [!UICONTROL Extensão] como [!UICONTROL Principal] e o [!UICONTROL Tipo de elemento de dados] como [!UICONTROL Parâmetro de string de consulta].
5. Insira o parâmetro da string de consulta no campo de texto.

O valor do parâmetro da string de consulta é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir variáveis do Analytics.

## s.Util.getQueryParam() no AppMeasurement e no editor de código personalizado do Launch

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
