---
title: Util.getQueryParam
description: Retorna o valor de um parâmetro da string de consulta.
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Util.getQueryParam

Parâmetros de string de consulta em um URL do navegador frequentemente contêm dados importantes para o Analytics. Use o `Util.getQueryParam` método para recuperar dados da string de consulta.

## Obter dados de parâmetro da string de consulta no Adobe Experience Platform Launch

É possível obter dados de parâmetro da string de consulta definindo valores em elementos de dados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia Elementos [!UICONTROL de] dados e clique no elemento de dados desejado (ou crie um elemento de dados).
4. Defina a lista suspensa [!UICONTROL Extensão] como [!UICONTROL Principal]e o Tipo [!UICONTROL de elemento de] dados como Parâmetro [!UICONTROL de string de]consulta.
5. Insira o parâmetro da string de consulta no campo de texto.

O valor do parâmetro da string de consulta é armazenado no elemento de dados. Você pode fazer referência ao elemento de dados nas regras para atribuir variáveis do Analytics.

## s.Util.getQueryParam() no AppMeasurement e Iniciar editor de código personalizado

Chame o `s.Util.getQueryParam()` método para recuperar um valor de string de consulta a partir do URL do navegador. O argumento de string que contém um parâmetro de string de consulta é obrigatório. Esse método retorna uma string, que pode ser atribuída às variáveis do Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Um segundo argumento opcional permite que você especifique a string para verificar os parâmetros da string de consulta. Por padrão, o utilitário consulta o URL do navegador.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Um terceiro argumento opcional permite personalizar o delimitador da string de consulta. Its default value is `&`. É possível alterar esse valor se a sequência de caracteres de consulta usar um delimitador diferente.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!NOTE] As versões anteriores do AppMeasurement tinham um plug-in chamado `s.getQueryParam` disponível. Esse plug-in não é mais necessário, pois agora está incluído no AppMeasurement por padrão.
