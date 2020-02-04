---
title: rfl
description: Remova um valor específico de uma string delimitada por caracteres.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Plug-in da Adobe: rfl (Remover da lista)

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudar a obter mais valor com o uso do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `rfl` plug-in permite que você remova com &quot;segurança&quot; valores de strings delimitadas, como `events`, `products`, list vars e outras. Esse plug-in é útil se você deseja remover valores específicos de uma string delimitada sem se preocupar com delimitadores. Vários outros plug-ins dependem desse código para serem executados corretamente. Esse plug-in não é necessário se você não precisar executar uma função específica em mais de uma variável do Analytics por vez ou se não estiver usando plug-ins dependentes.

O plug-in usa a seguinte lógica:

* Se o valor que você deseja remover existir, o plug-in manterá tudo na variável, exceto o valor a ser removido.
* Se o valor que você deseja remover não existir, o plug-in manterá a string original como está.

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
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `rfl` método usa os seguintes argumentos:

* **`lv`**(obrigatório, string): Uma variável (ou string) que contém uma lista de valores delimitados
* **`vr`**(obrigatório, string): O valor que você deseja remover do`lv`argumento. A Adobe recomenda a remoção de vários valores durante uma única`rfl`chamada.
* **`d1`**(opcional, string): O delimitador usado pelo`lv`argumento. O padrão é uma vírgula (`,`).
* **`d2`**(opcional, string): O delimitador que você deseja que a string de retorno use. O padrão é o mesmo valor do`d1`argumento.
* **`df`**(opcional, booleano): Se`true`, força apenas instâncias duplicadas do`vr`argumento do`lv`argumento em vez de todas as instâncias. O padrão é`false`quando não está definido.

Chamar esse método retorna uma string modificada contendo o `lv` argumento, mas sem nenhuma instância (ou instâncias duplicadas) do valor especificado no `vr` argumento.

## Exemplos de chamadas

### Exemplo nº 1

Se o status...

```js
s.events = "event22,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event24");
```

... o valor final de s.events será:

```js
s.events = "event22,event25";
```

### Exemplo nº 2

Se o status...

```js
s.events = "event22,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event26");
```

... o valor final de s.events será:

```js
s.events = "event22,event24,event25";
```

Neste exemplo, a chamada rfl não fez alterações em s.events, pois s.events não continham &quot;event26&quot;

### Exemplo 3

Se o status...

```js
s.events = "event22,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events);
```

... o valor final de s.events será:

```js
s.events = "";
```

Se o argumento lv ou vr estiver em branco em uma chamada s.rfl, o plug-in não retornará nada

### Exemplo nº 4

Se o status...

```js
s.prop4 = "hello|people|today";
```

...e o código a seguir é executado...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people|today";
```

...mas o valor final de s.eVar5 será:

```js
s.eVar5 = "hello|today";
```

Lembre-se de que o plug-in retorna apenas um valor; na verdade, ela não &quot;redefine&quot; a variável transmitida pelo argumento lv.

### Exemplo nº 5

Se o status...

```js
s.prop4 = "hello|people|today";
```

...e o código a seguir é executado...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

... o valor final de s.prop4 ainda será...

```js
s.prop4 = "hello|people|today";
```

Certifique-se de definir o argumento d1 nos casos em que o valor do argumento lv contém um delimitador diferente do valor padrão (ou seja, vírgula).

### Exemplo nº 6

Se o status...

```js
s.events = "event22,event23,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"EVenT23");
```

... o valor final de s.events será:

```js
s.events = "event22,event23,event25";
```

Embora esse exemplo não seja prático, demonstra a necessidade de passar em valores sensíveis a maiúsculas e minúsculas.

### Exemplo nº 7

Se o status...

```js
s.events = "event22,event23:12345,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23");
```

... o valor final de s.events será:

```js
s.events = "event22,event25";
```

### Exemplo nº 8

Se o status...

```js
s.events = "event22,event23:12345,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23:12345");
```

... o valor final de s.events será:

```js
s.events = "event22,event23:12345,event25";
```

Quando for necessário remover um evento que use a serialização e/ou a sintaxe numérica/de moeda, você deverá especificar somente o próprio evento (ou seja, sem os valores serialização/numérico/de moeda) na chamada s.rfl.

### Exemplo nº 9

Se o status...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23");
```

... o valor final de s.events será:

```js
s.events = "event22,event24,event25");
```

### Exemplo #10

Se o status...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

... o valor final de s.events será:

```js
s.events = "event22,event23,event24,event25");
```

### Exemplo #11

Se o status...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

... o valor final de s.events será:

```js
s.events = "event22|event23|event24|event25");
```

### Exemplo nº 12

Se o status...

```js
s.events = "event22,event23,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23,event24");
```

... o valor final de s.events será:

```js
s.events = "event22,event23,event24,event25";
```

Não há suporte para a configuração de vários valores no argumento vr. A lógica rfl no exemplo acima dividiria primeiro os valores no argumento lv (ou seja, s.events) e, em seguida, tentaria corresponder cada valor delimitado ao valor do argumento vr completo (ou seja, &quot;event23,event24&quot;).

### Exemplo #13

Se o status...

```js
s.events = "event22,event23,event24,event25";
```

...e o código a seguir é executado...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

... o valor final de s.events será:

```js
s.events = "event22,event25");
```

Cada valor a ser removido da lista deve estar contido em sua própria chamada s.rfl.

### Exemplo nº 14

Se o status...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...e o código a seguir é executado...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

... o valor final de s.linkTrackVars será:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Os três últimos argumentos (ou seja, &quot;,&quot;,&quot;,&quot;,false) no final desta chamada s.rfl não são necessários, mas também não estão &quot;prejudicando nada&quot; por estarem presentes, pois correspondem às configurações padrão.

### Exemplo nº 15

Se o status...

```js
s.events = "event22,event23,event24";
```

...e o código a seguir é executado...

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

* Correção de bug secundária para o valor do delimitador padrão

### 2.0 (16 de abril de 2018)

* Lançamento de ponto (recompilado, tamanho de código menor).
* Foi removida a necessidade do plug- `join` -in.

### 1.0 (18 de julho de 2016)

* Versão inicial.
