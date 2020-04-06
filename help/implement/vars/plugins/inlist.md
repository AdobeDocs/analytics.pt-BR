---
title: inList
description: Verifique se um valor está contido em outro valor delimitado por caracteres.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: inList

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `inList` permite verificar se um valor já existe em uma string delimitada ou em um objeto de matriz JavaScript. Vários outros plug-ins dependem do plug-in `inList` para funcionar. Esse plug-in oferece uma vantagem distinta em relação ao método JavaScript `indexOf()`, no qual não é possível corresponder strings parciais. Por exemplo, se você usou este plug-in para verificar `"event2"`, ele não corresponderá a uma string que contém `"event25"`. Este plug-in não é necessário se você não precisa verificar valores em strings delimitadas ou matrizes, ou se deseja usar sua própria lógica de `indexOf()`.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar inList
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `inList` aceita os seguintes argumentos:

* **`lv`** (obrigatório, string ou array): uma lista delimitada de valores ou um objeto de matriz JavaScript que passará por pesquisa
* **`vtc`** (obrigatório, string): o valor a ser pesquisado
* **`d`** (opcional, string): o delimitador usado para separar valores individuais no argumento `lv`. O padrão é uma vírgula (`,`) quando um valor não está definido.
* **`cc`** (opcional, booleano): se definido como `true`, é feita uma verificação que diferencia maiúsculas de minúsculas. Se definido como `false` ou omitido, então é feita uma verificação que não diferencia maiúsculas de minúsculas. O padrão é `false`.

Chamar esse método retornará `true` se encontrar uma correspondência e `false` se não encontrar uma correspondência.

## Exemplos de chamadas

### Exemplo #1

Se...

```js
s.events="event22,event24";
```

... e o código a seguir for executado...

```js
if(s.inList(s.events,"event22"))
```

...a declaração condicional if será verdadeira

### Exemplo #2

Se...

```js
s.events="event22,event24";
```

... e o código a seguir for executado...

```js
if(s.inList(s.events,"event2"))
```

...a declaração condicional if será falsa porque a chamada do inList não fez uma correspondência exata entre event2 e qualquer um dos valores delimitados em s.events

### Exemplo #3

Se...

```js
s.events="event22,event24";
```

... e o código a seguir for executado...

```js
if(!s.inList(s.events,"event23"))
```

...a declaração condicional if será verdadeira porque a chamada do inList não fez uma correspondência exata entre event23 e qualquer um dos valores delimitados em s.events (observe o operador &quot;NOT&quot; no início da chamada de variáveis do inList).

### Exemplo #4

Se...

```js
s.events = "event22,event23";
```

... e o código a seguir for executado...

```js
if(s.inList(s.events,"EVenT23","",1))
```

... a declaração condicional if será falsa.  Embora esse exemplo não seja prático, ele demonstra a necessidade de ter cautela ao usar o sinalizador que diferencia maiúsculas de minúsculas.

### Exemplo #5

Se...

```js
s.linkTrackVars = "events,eVar1";
```

... e o código a seguir for executado...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

... a declaração condicional if será falsa.  O valor do argumento d transmitido para a chamada (ou seja, &quot;|&quot;) presume que os valores individuais em s.linkTrackVars são delimitados por um caractere de barra vertical, enquanto na realidade, os valores são delimitados por uma vírgula.  Nesse caso, o plug-in tentará fazer uma correspondência entre o valor inteiro de s.linkTrackVars (ou seja, &quot;events,eVar1&quot;) e o valor a ser procurado (ou seja, &quot;eVar1&quot;).

## Histórico da versão

### v2.1 (26 de setembro de 2019)

* Adicionada a opção para que o argumento `cc` não seja booleano. Por exemplo, `1` é um valor válido de verificação de letras maiúsculas e minúsculas.

### v2.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).

### v1.01 (27 de setembro de 2017)

* Código otimizado para reduzir o tamanho

### v1.0 (2009)

* Versão inicial.


