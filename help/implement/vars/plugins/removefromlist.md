---
title: rfl
description: Remova um valor específico de uma string delimitada por caracteres.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: rfl (Remover da lista)

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O pug-in `rfl` permite que você remova com &quot;segurança&quot; valores de strings delimitadas, como [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md),  e outras. [`list`](../page-vars/list.md) Esse plug-in é útil se você deseja remover valores específicos de uma string delimitada sem se preocupar com delimitadores. Vários outros plug-ins dependem desse código para serem executados corretamente. Esse plug-in não é necessário se você não precisar executar uma função específica em mais de uma variável do Analytics por vez ou se não estiver usando plug-ins dependentes.

O plug-in usa a seguinte lógica:

* Se o valor que você deseja remover existir, o plug-in manterá tudo na variável, exceto o valor a ser removido.
* Se o valor que você deseja remover não existir, o plug-in manterá a string original como está.

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
   * Tipo de ação: inicializar RFP (Remover da lista)
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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `rfl` aceita os seguintes argumentos:

* **`lv`** (obrigatório, string): uma variável (ou string) que contém uma lista de valores delimitados
* **`vr`** (obrigatório, string): o valor que você deseja remover do argumento `lv`. A Adobe recomenda a remoção de vários valores durante uma única chamada do `rfl`.
* **`d1`** (opcional, string): o delimitador usado pelo argumento `lv`. O padrão é uma vírgula (`,`).
* **`d2`** (opcional, string): o delimitador que você deseja que a string de retorno use. O padrão é o mesmo valor do argumento `d1`.
* **`df`** (opcional, booleano): se `true`, força apenas instâncias duplicadas do argumento `vr` a partir do argumento `lv` em vez de todas as instâncias. O valor padrão é `false` quando um valor não está definido.

Chamar esse método retorna uma string modificada que contém o argumento `lv`, mas sem nenhuma instância (ou instâncias duplicadas) do valor especificado no argumento `vr`.

## Exemplos de chamadas

### Exemplo #1

Se...

```js
s.events = "event22,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = s.rfl(s.events,"event24");
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
s.events = s.rfl(s.events,"event26");
```

... o valor final de s.events será...

```js
s.events = "event22,event24,event25";
```

Neste exemplo, a chamada rfl não fez alterações em s.events, pois s.events não continham &quot;event26&quot;

### Exemplo #3

Se...

```js
s.events = "event22,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = s.rfl(s.events);
```

... o valor final de s.events será...

```js
s.events = "";
```

Se o argumento lv ou vr estiver em branco em uma chamada s.rfl, o plug-in não retornará nada

### Exemplo #4

Se...

```js
s.prop4 = "hello|people|today";
```

... e o código a seguir for executado...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people|today";
```

... mas o valor final de s.eVar5 será:

```js
s.eVar5 = "hello|today";
```

Lembre-se que o plug-in retorna apenas um valor; na verdade, ela não &quot;redefine&quot; a variável transmitida pelo argumento lv.

### Exemplo #5

Se...

```js
s.prop4 = "hello|people|today";
```

... e o código a seguir for executado...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people|today";
```

Certifique-se de definir o argumento d1 nos casos em que o valor do argumento lv contém um delimitador diferente do valor padrão (ou seja, vírgula).

### Exemplo #6

Se...

```js
s.events = "event22,event23,event25";
```

... e o código a seguir for executado...

```js
s.events = s.rfl(s.events,"EVenT23");
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
s.events = s.rfl(s.events,"event23");
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
s.events = s.rfl(s.events,"event23:12345");
```

... o valor final de s.events será...

```js
s.events = "event22,event23:12345,event25";
```

Quando for necessário remover um evento que use serialização e/ou sintaxe numérica/de moeda, você deverá especificar somente o próprio evento (ou seja, sem os valores serialização/numérico/de moeda) na chamada de s.rfl.

### Exemplo #9

Se...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = s.rfl(s.events,"event23");
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
s.events = s.rfl(s.events,"event23", "", "",true);
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
s.events = s.rfl(s.events,"event23", "", "|",true);
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
s.events = s.rfl(s.events,"event23,event24");
```

... o valor final de s.events será...

```js
s.events = "event22,event23,event24,event25";
```

Não há suporte para a configuração de vários valores no argumento vr. A lógica do rfl no exemplo acima dividiria primeiro os valores no argumento lv (ou seja, s.events) e, em seguida, tentaria corresponder cada valor delimitado ao valor do argumento vr completo (ou seja, &quot;event23,event24&quot;).

### Exemplo #13

Se...

```js
s.events = "event22,event23,event24,event25";
```

... e o código a seguir for executado...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

... o valor final de s.events será...

```js
s.events = "event22,event25");
```

Cada valor a ser removido da lista deve estar contido em sua própria chamada s.rfl.

### Exemplo #14

Se...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

... e o código a seguir for executado...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

... o valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Os três últimos argumentos (ou seja, &quot;,&quot;,&quot;,&quot;,false) no final desta chamada de s.rfl não são necessários, mas também não estão &quot;prejudicando nada&quot; por estarem presentes, pois correspondem às configurações padrão.

### Exemplo #15

Se...

```js
s.events = "event22,event23,event24";
```

... e o código a seguir for executado...

```js
s.rfl(s.events,"event23");
```

... o valor final de s.events ainda será:

```js
s.events = "event22,event23,event24";
```

Novamente, lembre-se de que o plug-in retorna apenas um valor; na verdade, ela não &quot;redefine&quot; a variável transmitida pelo argumento lv.

## Histórico da versão

### 2.01 (17 de setembro de 2019)

* Correção de pequeno erro no valor padrão do delimitador

### 2.0 (16 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Foi removida a necessidade do plug-in `join`.

### 1.0 (18 de julho de 2016)

* Versão inicial.
