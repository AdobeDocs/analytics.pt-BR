---
title: apl (appendToList)
description: Anexe valores a variáveis que suportam vários valores.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: apl (appendToList)

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `apl` permite adicionar com segurança novos valores a variáveis delimitadas por lista, como [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md),  e outras.[`list`](../page-vars/list.md)

* Se o valor que você deseja adicionar não existir na variável, então o código adiciona o valor ao final da string.
* Se o valor que você deseja adicionar já existir na variável, esse plug-in não altera o valor. Esses recursos permitem que sua implementação evite valores duplicados.
* Se a variável que você deseja adicionar estiver vazia, o plug-in atribuirá à variável o novo valor.

A Adobe recomenda usar esse plug-in se você desejar adicionar novos valores às variáveis existentes que contenham uma string de valores delimitados. Esse plug-in não é necessário se você preferir concatenar strings para variáveis que contêm valores delimitados.

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
   * Tipo de ação: inicializar apl (Anexar à lista)
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `apl` aceita os seguintes argumentos:

* **`lv`** (obrigatório, string): a variável que contém uma lista delimitada de itens aos quais será adicionado um novo valor
* **`vta`** (obrigatório, string): uma lista delimitada por vírgulas com novos valores a serem adicionados ao valor do argumento `lv`.
* **`d1`** (opcional, string): o delimitador usado para separar os valores individuais já contidos no argumento `lv`.  O padrão é uma vírgula (`,`) quando um valor não está definido.
* **`d2`** (opcional, string): o delimitador de saída. O padrão é o mesmo valor de `d1` quando não está definido.
* **`cc`** (opcional, booleano): um sinalizador que indica se uma verificação que diferencia maiúsculas e minúsculas é usada. Se `true`, a verificação de duplicação faz distinção entre maiúsculas e minúsculas. Se definida `false` ou não definida, a verificação de duplicação não diferencia maiúsculas de minúsculas. O padrão é `false`.

O método `apl` retorna o valor do argumento `lv` somado a quaisquer valores não duplicados no argumento `vta`.

## Exemplos de chamadas

### Exemplo #1

Se...

```js
s.events = "event22,event24";
```

... e o código a seguir for executado...

```js
s.events = s.apl(s.events, "event23");
```

... o valor final de s.events será:

```js
s.events = "event22,event24,event23";
```

### Exemplo #2

Se...

```js
s.events = "event22,event23";
```

... e o código a seguir for executado...

```js
s.events = s.apl(s.events, "event23");
```

... o valor final de s.events ainda será:

```js
s.events = "event22,event23";
```

Neste exemplo, a chamada do apl não fez alterações em s.events, pois s.events já continha &quot;event23&quot;

### Exemplo #3

Se...

```js
s.events = ""; //blank value
```

... e o código a seguir for executado...

```js
s.events = s.apl(s.events, "event23");
```

... o valor final de s.events será...

```js
s.events = "event23";
```

### Exemplo #4

Se...

```js
s.prop4 = "hello|people";
```

... e o código a seguir for executado...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people";
```

... mas o valor final de s.eVar5 será

```js
s.eVar5 = "hello|people|today";
```

Lembre-se que o plug-in retorna apenas um valor; ela não &quot;redefine&quot; necessariamente a variável transmitida pelo argumento lv.

### Exemplo #5

Se...

```js
s.prop4 = "hello|people";
```

... e o código a seguir for executado...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... o valor final de s.prop4 será...

```js
s.prop4 = "hello|people,today";
```

Certifique-se de manter o delimitador consistente entre o que está no valor do argumento lv e o que está nos argumentos d1/d2

### Exemplo #6

Se...

```js
s.events = "event22,event23";
```

... e o código a seguir for executado...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... o valor final de s.events será:

```js
s.events = "event22,event23,EVentT23";
```

Embora esse exemplo não seja prático, ele demonstra a necessidade de ter cautela ao usar o sinalizador que diferencia maiúsculas de minúsculas.

### Exemplo #7

Se...

```js
s.events = "event22,event23";
```

... e o código a seguir for executado...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... o valor final de s.events será:

```js
s.events = "event22,event23,event24,event25");
```

O plug-in não adicionará &quot;event23&quot; a s.events porque ele já existe em s.events.  No entanto, ele adicionará event24 e event25 a s.events porque nenhum deles estava contido anteriormente em s.events.

### Exemplo #8

Se...

```js
s.linkTrackVars = "events,eVar1";
```

... e o código a seguir for executado...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... o valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Os três últimos argumentos (ou seja, &quot;,&quot;, &quot;,&quot;, false) no final desta chamada apl não são necessários, mas defini-los não &quot;prejudica&quot;, pois correspondem aos valores padrão do argumento.

### Exemplo #9

Se...

```js
s.events = "event22,event24";
```

... e o código a seguir for executado...

```js
s.apl(s.events, "event23");
```

... o valor final de s.events ainda será:

```js
s.events = "event22,event24";
```

Executar o plug-in por si só (sem atribuir o valor de retorno a uma variável) não &quot;redefine&quot; a variável transmitida pelo argumento lv.

### Exemplo #10

Se...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

... e o código a seguir for executado...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... o valor final de s.list2 será:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Como os dois argumentos delimitadores são diferentes, o valor transmitido será delimitado pelo primeiro argumento delimitador (&quot;|&quot;) e unido pelo segundo argumento delimitador (&quot;-&quot;)

## Histórico da versão

### 3.2 (25 de setembro, 2019)

* Correção de problemas de compatibilidade com chamadas de `apl` que usavam versões anteriores do plug-in
* Remoção de avisos do console para redução do tamanho
* Adição de `inList 2.1`

### 3.1 (22 de abril, 2018)

* Agora, o padrão do argumento `d2`, quando não definido, é o valor do argumento `d1`

### 3.0 (16 de abril, 2018)

* Reanálise/reescrita completa do plug-in
* Foi adicionada a verificação avançada de erros
* O argumento `vta` agora aceita vários valores de uma vez
* Adição do argumento `d2` para formatar o valor de retorno
* Alteração do tipo do argumento `cc` para booleano

### 2.5 (18 de fevereiro de 2016)

* Agora usa o método `inList` para processamento de comparação

### 2.0 (26 de janeiro de 2016)

* O argumento `d` (delimitador) agora é opcional (o padrão é uma vírgula)
* O argumento `u` (sinalizador de diferenciação entre maiúsculas e minúsculas) agora é opcional (o padrão é não diferenciar maiúsculas de minúsculas)
* Independentemente do argumento `u` (sinalizador de diferenciação entre maiúsculas e minúsculas), o plug-in não anexa mais um valor a uma lista se o valor já existir na lista