---
title: s_gi()
description: Crie e rastreie instâncias do AppMeasurement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# s_gi

A `s_gi()` função instancia ou encontra uma instância do AppMeasurement por ID de conjunto de relatórios. AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. Se uma instância não existir, uma nova instância será criada.

## s_gi() no Adobe Experience Platform Launch

A extensão do Analytics instancia e gerencia o objeto de rastreamento para você. No entanto, você também pode definir um objeto de rastreamento global no [!UICONTROL Library Management] acordeão ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Expanda o [!UICONTROL Library Management] acordeão e selecione qualquer botão de opção diferente de [!UICONTROL Manage the library for me].

O campo de texto da variável global permite definir um objeto de rastreamento personalizado. Its default value is `s`.

## s_gi() no AppMeasurement e Iniciar editor de código personalizado

Chame a `s_gi()` função para instanciar um objeto de rastreamento. Seu único argumento contém uma string delimitada por vírgulas de IDs de conjunto de relatórios. O argumento ID do conjunto de relatórios é obrigatório.

> [!TIP] A Adobe recomenda usar a `s` variável como um objeto de rastreamento. A Adobe usa `s` sua documentação, exemplos de implementação e plug-ins. No entanto, você pode usar qualquer variável desde que seja consistente em todo o site.

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!CAUTION] As seções e exemplos a seguir contêm tópicos complexos de implementação. Teste sua implementação minuciosamente e rastreie personalizações importantes no documento [de design da](../../prepare/solution-design.md)solução da sua organização.

## Gerenciar várias implementações usando diferentes objetos de rastreamento

É possível enviar dados diferentes para conjuntos de relatórios diferentes se você instanciar vários objetos de rastreamento. Esses dois objetos de rastreamento operam independentemente um do outro.

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## Restaurar variáveis do AppMeasurement após substituir o objeto s

Algumas ferramentas de terceiros também podem usar o `s` objeto JavaScript. Se você substituir acidentalmente o `s` objeto no site, poderá chamar `s_gi` com o mesmo argumento de string RSID para restaurar todas as variáveis e métodos substituídos.

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## Referência ao mesmo objeto de rastreamento com várias variáveis

Se duas variáveis referenciarem a mesma `s_gi()` função com o mesmo conjunto de relatórios, você poderá usar as variáveis alternadamente.

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
