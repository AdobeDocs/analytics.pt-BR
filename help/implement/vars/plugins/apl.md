---
title: ' apl (appendToList)'
description: Anexar valores a variáveis que suportam vários valores.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe: apl (appendToList)

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `apl` -in permite adicionar com segurança novos valores a variáveis delimitadas por lista, como `events`, `linkTrackVars`, list vars e outras.

* Se o valor que você deseja adicionar não existir na variável, então o código adiciona o valor ao final da string.
* Se o valor que você deseja adicionar já existir na variável, esse plug-in não altera o valor. Esses recursos permitem que sua implementação evite valores duplicados.
* Se a variável que você deseja adicionar estiver vazia, o plug-in definirá a variável para o novo valor.

A Adobe recomenda usar esse plug-in se desejar adicionar novos valores às variáveis existentes que contenham uma sequência de valores delimitados. Esse plug-in não é necessário se você preferir concatenar strings para variáveis que contêm valores delimitados.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar APL (Anexar à lista)
1. Salve e publique as alterações na regra.

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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `apl` método usa os seguintes argumentos:

* **`lv`**(obrigatório, string): A variável que contém uma lista delimitada de itens para adicionar um novo valor a
* **`vta`**(obrigatório, string): Uma lista delimitada por vírgulas dos novos valores a serem adicionados ao valor do`lv`argumento.
* **`d1`**(opcional, string): O delimitador usado para separar os valores individuais já contidos no`lv`argumento.  O padrão é uma vírgula (`,`) quando não está definida.
* **`d2`**(opcional, string): O delimitador de saída. O padrão é o mesmo valor que`d1`quando não está definido.
* **`cc`**(opcional, booleano): Um sinalizador que indica se uma verificação que diferencia maiúsculas e minúsculas é usada. Se`true`, a verificação de duplicação faz distinção entre maiúsculas e minúsculas. Se definida`false`ou não, a verificação de duplicação não diferencia maiúsculas de minúsculas. O padrão é`false`.

O `apl` método retorna o valor do `lv` argumento mais quaisquer valores não duplicados no `vta` argumento.

## Exemplos de chamadas

### Exemplo #1

Se o status...

```js
s.events = "event22,event24";
```

...e o código a seguir é executado...

```js
s.events = s.apl(s.events, "event23");
```

... o valor final de s.events será:

```js
s.events = "event22,event24,event23";
```

### Exemplo #2

Se o status...

```js
s.events = "event22,event23";
```

...e o código a seguir é executado...

```js
s.events = s.apl(s.events, "event23");
```

... o valor final de s.events ainda será:

```js
s.events = "event22,event23";
```

Neste exemplo, a chamada de aplicativo não fez alterações em s.events, pois s.events já continha &quot;event23&quot;

### Exemplo 3

Se o status...

```js
s.events = ""; //blank value
```

...e o código a seguir é executado...

```js
s.events = s.apl(s.events, "event23");
```

... o valor final de s.events será...

```js
s.events = "event23";
```

### Exemplo #4

Se o status...

```js
s.prop4 = "hello|people";
```

...e o código a seguir é executado...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people";
```

...mas o valor final de s.eVar5 será

```js
s.eVar5 = "hello|people|today";
```

Lembre-se de que o plug-in retorna apenas um valor; ela não &quot;redefine&quot; necessariamente a variável transmitida pelo argumento lv.

### Exemplo #5

Se o status...

```js
s.prop4 = "hello|people";
```

...e o código a seguir é executado...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... o valor final de s.prop4 será...

```js
s.prop4 = "hello|people,today";
```

Certifique-se de manter o delimitador consistente entre o que está no valor do argumento lv e o que está nos argumentos d1/d2

### Exemplo #6

Se o status...

```js
s.events = "event22,event23";
```

...e o código a seguir é executado...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... o valor final de s.events será:

```js
s.events = "event22,event23,EVentT23";
```

Embora esse exemplo não seja prático, demonstra a necessidade de usar cautela ao usar o sinalizador que diferencia maiúsculas de minúsculas.

### Exemplo #7

Se o status...

```js
s.events = "event22,event23";
```

...e o código a seguir é executado...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... o valor final de s.events será:

```js
s.events = "event22,event23,event24,event25");
```

O plug-in não adicionará &quot;event23&quot; a s.events porque ele já existe em s.events.  No entanto, ele adicionará event24 e event25 a s.events porque nenhum deles estava anteriormente contido em s.events.

### Exemplo #8

Se o status...

```js
s.linkTrackVars = "events,eVar1";
```

...e o código a seguir é executado...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... o valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Os três últimos argumentos (ou seja, &quot;,&quot;, &quot;,&quot;, false) no final desta chamada de aplicativo não são necessários, mas também não estão &quot;prejudicando nada&quot; ao serem definidos, pois correspondem aos valores padrão do argumento.

### Exemplo #9

Se o status...

```js
s.events = "event22,event24";
```

...e o código a seguir é executado...

```js
s.apl(s.events, "event23");
```

... o valor final de s.events ainda será:

```js
s.events = "event22,event24";
```

Executar o plug-in sozinho (sem atribuir o valor de retorno a uma variável) não &quot;redefine&quot; a variável transmitida pelo argumento lv.

### Exemplo #10

Se o status...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...e o código a seguir é executado...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... o valor final de s.list2 será:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Como os dois argumentos delimitadores são diferentes, o valor passado será delimitado pelo primeiro argumento delimitador (&quot;|&quot;) e unido pelo segundo argumento delimitador (&quot;-&quot;)

## Histórico da versão

### 3.2 (25 de setembro de 2019)

* Correção de problemas de compatibilidade com `apl` chamadas que usavam versões anteriores do plug-in
* Remoção de avisos do console para reduzir o tamanho
* Adição de `inList 2.1`

### 3.1 (22 de abril de 2018)

* `d2` agora, o padrão do argumento é o valor do `d1` argumento quando não definido

### 3.0 (16 de abril de 2018)

* Reanálise/regravação completa do plug-in
* Adicionada a verificação avançada de erros
* O `vta` argumento agora aceita vários valores de uma vez
* Adição do `d2` argumento para formatar o valor de retorno
* Alteração do `cc` argumento para um booleano

### 2.5 (18 de fevereiro de 2016)

* Agora usa o `inList` método para processamento de comparação

### 2.0 (26 de janeiro de 2016)

* `d` Argumento (delimitador) agora opcional (o padrão é uma vírgula)
* `u` (Sinalizador de diferenciação entre maiúsculas e minúsculas) agora opcional (o padrão não diferencia maiúsculas e minúsculas)
* Independentemente do argumento `u` (indicador de diferenciação entre maiúsculas e minúsculas), o plug-in não anexa mais um valor a uma lista se o valor já existir na lista