---
title: formatTime
description: Converta um número de segundos para seu equivalente em minutos, horas etc.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: formatTime

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `formatTime` permite que você trate qualquer número de segundos e o apresente em um formato reduzido, arredondado para um valor referencial desejado. A Adobe recomenda usar esse plug-in se você quiser capturar um valor de tempo em segundos e convertê-lo em um formato simplificado (como minutos, dias ou semanas). Esse plug-in é desnecessário se você não quiser agrupar valores com em segundos em um formato arredondado por tempo.

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
   * Tipo de ação: inicializar formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `formatTime` aceita os seguintes argumentos:

* **`ns`** (obrigatório, número inteiro): o número de segundos a ser convertido ou formatado
* **`tf`** (opcional, string): o tipo de formato em que os segundos devem ser retornados; o padrão é segundos
   * Defina como `"d"` se desejar tempo em dias (arredondado para o referencial de 1/4 de dia que estiver mais próximo, por padrão)
   * Defina como `"h"` se desejar tempo em horas (arredondado para o referencial de 1/4 de hora que estiver mais próximo, por padrão)
   * Defina como `"m"` se desejar tempo em minutos (arredondado para o referencial de 1/2 minuto que estiver mais próximo, por padrão)
   * Defina como `"s"` se desejar tempo em segundos (arredondado para o referencial de 5 segundos que estiver mais próximo, por padrão)
* **`bml`** (opcional, número): a quantidade de tempo dos referenciais de arredondamento. Padrões para os referenciais listados no argumento `tf`

O método retorna o número de segundos formatados na unidade especificada no argumento `tf`. Se o argumento `tf` não estiver definido:

* Qualquer coisa menor que um minuto é arredondada para o referencial de 5 segundos que estiver mais próximo
* Qualquer coisa entre um minuto e uma hora é arredondada para o referencial de 1/2 minuto que estiver mais próximo
* Qualquer coisa entre uma hora e um dia é arredondada para o referencial de 1/4 de hora que estiver mais próximo
* Qualquer coisa maior que um dia é arredondada para o valor referencial de dia que estiver mais próximo

## Exemplos

### Exemplo #1

O código a seguir...

```js
s.eVar1 = s.formatTime(38242);
```

... definirá s.eVar1 como &quot;10,5 horas&quot;

O argumento transmitido, 38242 segundos, é igual a 10 horas, 37 minutos e 22 segundos.  Como o argumento tf não está definido nesta chamada e o número de segundos transmitidos está entre uma hora e um dia, o plug-in retornará o número de segundos convertidos para o referencial de 1/4 de hora que estiver mais próximo.

### Exemplo #2

O código a seguir...

```js
s.eVar1 = s.formatTime(38250);
```

...definirá s.eVar1 como &quot;10,75 horas&quot;
O argumento transmitido, 38250 segundos, é igual a 10 horas, 37 minutos e 30 segundos.  Nesse caso, arredondar o número de segundos transmitidos para o referencial de 1/4 de hora que estiver mais próximo definirá o valor final como 10,75 horas

### Exemplo #3

O código a seguir...

```js
s.eVar1 = s.formatTime(38242, "m");
```

... definirá s.eVar1 como &quot;637,5 minutos&quot;

Nesse caso, o argumento &quot;m&quot; força o plug-in a converter os segundos para o referencial de meio minuto que estiver mais próximo

### Exemplo #4

O código a seguir...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

... definirá s.eVar1 como &quot;640 minutos&quot;

O valor do argumento tf (&quot;m&quot;) força o plug-in a converter os segundos em minutos, mas o valor do argumento bml (20) também força o plug-in a arredondar a conversão de minutos para o referencial de 20 minutos que estiver mais próximo.

### Exemplo #5

O código a seguir...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...definirá s.eVar1 como &quot;126 segundos&quot;, que é o referencial de 2 segundos mais próximo a 125 segundos

### Exemplo #6

O código a seguir...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...definirá s.eVar1 como &quot;3 minutos&quot;, que é o referencial de 3 minutos mais próximo a 125 segundos

### Exemplo #7

O código a seguir...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...definirá s.eVar1 como &quot;2,4 minutos&quot;, que é o referencial de 2/5 minutos mais próximo (por exemplo, .4 = 2/5) a 145 segundos

## Histórico da versão

### 1.1 (21 de maio de 2018)

* Adição do argumento `bml` para permitir mais flexibilidade no arredondamento

### 1.0 (15 de abril de 2018)

* Versão inicial.
