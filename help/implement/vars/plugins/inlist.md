---
title: inList
description: Verifique se um valor está contido em outro valor delimitado por caracteres.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Plug-in da Adobe:inList

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudar a obter mais valor com o uso do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `inList` plug-in permite verificar se um valor já existe em uma string delimitada ou em um objeto de matriz JavaScript. Vários outros plug-ins dependem do `inList` plug-in para funcionar. Esse plug-in oferece uma vantagem distinta sobre o método JavaScript `indexOf()` no qual você não corresponde a sequências parciais. Por exemplo, se você usou este plug-in para verificar se `"event2"`, ele não corresponderá a uma string que contém `"event25"`. Este plug-in não é necessário se você não precisa verificar valores em sequências delimitadas ou matrizes, ou se deseja usar sua própria `indexOf()` lógica.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Para qualquer Regra de inicialização em que você deseja usar o plug-in, adicione uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar addProductEvar
1. Salvar e publicar as alterações na regra

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código] personalizado, que revela o botão [!UICONTROL Abrir editor] .
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando `s_gi`). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `inList` método usa os seguintes argumentos:

* **`lv`**(obrigatório, sequência de caracteres ou matriz): Uma lista delimitada de valores ou um objeto de matriz JavaScript a ser pesquisado
* **`vtc`**(obrigatório, string): O valor a ser pesquisado
* **`d`**(opcional, string): O delimitador usado para separar valores individuais no`lv`argumento. O padrão é uma vírgula (`,`) quando não está definida.
* **`cc`**(opcional, booleano): Se definido como`true`, é feita uma verificação que diferencia maiúsculas de minúsculas. Se definido como`false`ou omitido, então é feita uma verificação que não diferencia maiúsculas de minúsculas. O padrão é`false`.

Chamar esse método retornará `true` se encontrar uma correspondência e `false` se não encontrar uma correspondência.

## Exemplos de chamadas

### Exemplo nº 1

Se o status...

```js
s.events="event22,event24";
```

...e o código a seguir é executado...

```js
if(s.inList(s.events,"event22"))
```

...a declaração condicional if será verdadeira

### Exemplo nº 2

Se o status...

```js
s.events="event22,event24";
```

...e o código a seguir é executado...

```js
if(s.inList(s.events,"event2"))
```

...a declaração condicional if será falsa porque a chamada inList não fez uma correspondência exata entre event2 e qualquer um dos valores delimitados em s.events

### Exemplo 3

Se o status...

```js
s.events="event22,event24";
```

...e o código a seguir é executado...

```js
if(!s.inList(s.events,"event23"))
```

...a declaração condicional if será verdadeira porque a chamada inList não fez uma correspondência exata entre event23 e qualquer um dos valores delimitados em s.events (observe o operador &quot;NOT&quot; no início da chamada de variável inList).

### Exemplo nº 4

Se o status...

```js
s.events = "event22,event23";
```

...e o código a seguir é executado...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...a declaração condicional if será falsa.  Embora esse exemplo não seja prático, demonstra a necessidade de usar cautela ao usar o sinalizador que diferencia maiúsculas de minúsculas.

### Exemplo nº 5

Se o status...

```js
s.linkTrackVars = "events,eVar1";
```

...e o código a seguir é executado...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...a declaração condicional if será falsa.  O valor do argumento d passado para a chamada (ou seja, &quot;|&quot;) presume que os valores individuais em s.linkTrackVars são delimitados por um caractere de barra vertical, enquanto na realidade, os valores são delimitados por uma vírgula.  Nesse caso, o plug-in tentará fazer uma correspondência entre o valor inteiro de s.linkTrackVars (ou seja, &quot;events,eVar1&quot;) e o valor a ser procurado (ou seja, &quot;eVar1&quot;).

## Histórico da versão

### v2.1 (26 de setembro de 2019)

* Adicionada a opção para que o `cc` argumento não seja booleano. Por exemplo, `1` é um valor de verificação de letras maiúsculas e minúsculas válido.

### v2.0 (17 de abril de 2018)

* Lançamento de ponto (recompilado, tamanho de código menor).

### v1.01 (27 de setembro de 2017)

* Código otimizado para reduzir o tamanho

### v1.0 (2009)

* Versão inicial.


