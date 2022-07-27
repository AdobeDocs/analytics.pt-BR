---
title: rfl
description: Remova um valor específico de uma string delimitada por caracteres.
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 98%

---

# Plug-in da Adobe: rfl (Remover da lista)

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `rfl` permite que você remova com &quot;segurança&quot; valores de strings delimitadas, como [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md) e outras. Esse plug-in é útil se você deseja remover valores específicos de uma string delimitada sem se preocupar com delimitadores. Vários outros plug-ins dependem desse código para serem executados corretamente. Esse plug-in não é necessário se você não precisar executar uma função específica em mais de uma variável do Analytics por vez ou se não estiver usando plug-ins dependentes.

O plug-in usa a seguinte lógica:

* Se o valor que você deseja remover existir, o plug-in manterá tudo na variável, exceto o valor a ser removido.
* Se o valor que você deseja remover não existir, o plug-in manterá a string original como está.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize RFP (Remove From List)
1. Save and publish the changes to the rule.-->

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `rfl` usa os seguintes argumentos:

* **`lv`** (obrigatório, string): uma variável (ou string) que contém uma lista de valores delimitados.
* **`vr`** (obrigatório, string): o valor que você deseja remover do argumento `lv`. A Adobe recomenda a remoção de vários valores durante uma única chamada do `rfl`.
* **`d1`** (opcional, string): o delimitador usado pelo argumento `lv`. O padrão é uma vírgula (`,`).
* **`d2`** (opcional, string): o delimitador que você deseja que a string de retorno use. O padrão é o mesmo valor do argumento `d1`.
* **`df`** (opcional, booleano): se `true`, força apenas instâncias duplicadas do argumento `vr` a partir do argumento `lv` em vez de todas as instâncias. O valor padrão é `false` quando um valor não está definido.

Chamar essa função retorna uma string modificada que contém o argumento `lv`, porém, sem nenhuma instância (ou instâncias duplicadas) do valor especificado no argumento `vr`.

## Exemplos de chamadas

### Exemplo #1

Se...

```js
s.events = "event22,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event24");
```

... o valor final de s.events será...

```js
s.events = "event22,event25";
```

### Exemplo #2

Se...

```js
s.events = "event22,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event26");
```

... o valor final de s.events será...

```js
s.events = "event22,event24,event25";
```

Neste exemplo, a chamada rfl não fez alterações em s.events, pois s.events não continham &quot;event26&quot;.

### Exemplo #3

Se...

```js
s.events = "event22,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events);
```

... o valor final de s.events será...

```js
s.events = "";
```

Se o argumento `lv` ou `vr` estiver em branco em uma chamada `rfl`, o plug-in não retornará nada.

### Exemplo #4

Se...

```js
s.prop4 = "hello|people|today";
```

... e o código a seguir for executado...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people|today";
```

... mas o valor final de s.eVar5 será:

```js
s.eVar5 = "hello|today";
```

Lembre-se que o plug-in retorna apenas um valor; na verdade, ele não “redefine” a variável transmitida pelo argumento `lv`.

### Exemplo #5

Se...

```js
s.prop4 = "hello|people|today";
```

... e o código a seguir for executado...

```js
s.prop4 = rfl(s.prop4,"people");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people|today";
```

Defina o argumento `d1` nos casos em que o valor do argumento `lv` contém um delimitador diferente do valor padrão (ou seja, vírgula).

### Exemplo #6

Se...

```js
s.events = "event22,event23,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"EVenT23");
```

... o valor final de s.events será...

```js
s.events = "event22,event23,event25";
```

Embora esse exemplo não seja prático, demonstra a necessidade de transmitir valores que diferenciam maiúsculas e minúsculas.

### Exemplo #7

Se...

```js
s.events = "event22,event23:12345,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23");
```

... o valor final de s.events será...

```js
s.events = "event22,event25";
```

### Exemplo #8

Se...

```js
s.events = "event22,event23:12345,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23:12345");
```

... o valor final de s.events será...

```js
s.events = "event22,event23:12345,event25";
```

Quando for necessário remover um evento que use serialização e/ou sintaxe numérica/de moeda, você deverá especificar somente o evento em si (ou seja, sem os valores de serialização/numérico/de moeda) na chamada `rfl`.

### Exemplo #9

Se...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23");
```

... o valor final de s.events será...

```js
s.events = "event22,event24,event25");
```

### Exemplo #10

Se...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23", "", "",true);
```

... o valor final de s.events será...

```js
s.events = "event22,event23,event24,event25");
```

### Exemplo #11

Se...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23", "", "|",true);
```

... o valor final de s.events será...

```js
s.events = "event22|event23|event24|event25");
```

### Exemplo #12

Se...

```js
s.events = "event22,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23,event24");
```

... o valor final de s.events será...

```js
s.events = "event22,event23,event24,event25";
```

Não há suporte para a configuração de vários valores no argumento `vr` A lógica do `rfl` no exemplo acima dividiria primeiro os valores no argumento `lv` (ou seja, s.events) e, em seguida, tentaria corresponder cada valor delimitado ao valor completo do argumento `vr` (ou seja, `"event23,event24"`).

### Exemplo #13

Se...

```js
s.events = "event22,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = rfl(s.events,"event23");
s.events = rfl(s.events,"event24");
```

... o valor final de s.events será...

```js
s.events = "event22,event25");
```

Cada valor a ser removido da lista deve estar contido em sua própria chamada `rfl`.

### Exemplo #14

Se...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

... e o código a seguir for executado...

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

... o valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Os três últimos argumentos (ou seja, &quot;,&quot;,&quot;,&quot;,false) no final desta chamada `rfl` não são necessários, mas também não estão “prejudicando em nada” por estarem presentes, pois correspondem às configurações padrão.

### Exemplo #15

Se...

```js
s.events = "event22,event23,event24";
```

... e o código a seguir for executado...

```js
rfl(s.events,"event23");
```

... o valor final de s.events ainda será:

```js
s.events = "event22,event23,event24";
```

Novamente, lembre-se de que o plug-in retorna apenas um valor; na verdade, ele não “redefine” a variável transmitida pelo argumento `lv`.

## Histórico da versão

### 2.1 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.01 (17 de setembro de 2019)

* Correção de pequeno erro no valor padrão do delimitador.

### 2.0 (16 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Foi removida a necessidade do plug-in `join`.

### 1.0 (18 de julho de 2016)

* Versão inicial.
