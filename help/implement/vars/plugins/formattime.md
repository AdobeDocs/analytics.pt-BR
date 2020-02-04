---
title: formatTime
description: Converta um número de segundos em seu equivalente em minutos, horas etc.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Plug-in da Adobe:formatTime

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `formatTime` in permite que você leve qualquer número de segundos e os apresente em um formato segmentado, arredondado para um valor de benchmark desejado. A Adobe recomenda usar esse plug-in se você quiser capturar um valor de tempo em segundos e convertê-lo em um formato de período (como minutos, dias ou semanas). Esse plug-in é desnecessário se você não quiser agrupar valores com base em segundo em um formato arredondado para o tempo.

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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `formatTime` método usa os seguintes argumentos:

* **`ns`**(obrigatório, número inteiro): O número de segundos para converter ou formatar
* **`tf`**(opcional, string): O tipo de formato em que os segundos devem ser retornados; padrão para segundos
   * Defina como `"d"` se desejar o tempo em dias (arredondado para o benchmark de 1/4 dias mais próximo por padrão)
   * Defina como `"h"` se desejar o tempo em horas (arredondado para o benchmark de 1/4 horas mais próximo por padrão)
   * Defina como `"m"` se desejar o tempo em minutos (arredondado para o benchmark de 1/2 minutos mais próximo por padrão)
   * Defina como `"s"` se desejar o tempo em segundos (arredondado para o benchmark de 5 segundos mais próximo por padrão)
* **`bml`**(opcional, número): A duração dos referenciais de arredondamento. Padrões para os benchmarks listados no`tf`argumento

O método retorna o número de segundos formatados usando a unidade especificada no `tf` argumento. Se o `tf` argumento não estiver definido:

* Qualquer coisa menor que um minuto é arredondada para o benchmark de 5 segundos mais próximo
* Qualquer coisa entre um minuto e uma hora é arredondada para o benchmark de 1/2 minutos mais próximo
* Qualquer coisa entre uma hora e um dia é arredondada para o benchmark de trimestre mais próximo
* Qualquer coisa maior que um dia é arredondada para o valor de referência de dia mais próximo

## Exemplos

### Exemplo nº 1

O seguinte código...

```js
s.eVar1 = s.formatTime(38242);
```

...definirá s.eVar1 igual a &quot;10,5 horas&quot;

O argumento transmitido - 38242 segundos - é igual a 10 horas, 37 minutos e 22 segundos.  Como o argumento tf não está definido nesta chamada e o número de segundos passados está entre uma hora e um dia, o plug-in retornará o número de segundos convertidos para o benchmark de trimestre mais próximo.

### Exemplo nº 2

O seguinte código...

```js
s.eVar1 = s.formatTime(38250);
```

...definirá s.eVar1 igual a &quot;10,75 horas&quot;O argumento transmitido - 38250 segundos - é igual a 10 horas, 37 minutos e 30 segundos.  Arredondamento do número de segundos passados para o benchmark de trimestre-hora mais próximo nesse caso definirá o valor final como 10,75 horas

### Exemplo 3

O seguinte código...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...definirá s.eVar1 igual a &quot;637,5 minutos&quot;

Neste caso, o argumento &quot;m&quot; força o plug-in a converter os segundos para o benchmark de ½ minuto mais próximo

### Exemplo nº 4

O seguinte código...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...definirá s.eVar1 igual a &quot;640 minutos&quot;

O valor do argumento tf (&quot;m&quot;) força o plug-in a converter os segundos em minutos, mas o valor do argumento bml (20) também força o plug-in a arredondar a conversão de minutos para o benchmark de 20 minutos mais próximo.

### Exemplo nº 5

O seguinte código...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...definirá s.eVar1 igual a &quot;126 segundos&quot;, que é o benchmark de 2 segundos mais próximo a 125 segundos

### Exemplo nº 6

O seguinte código...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...definirá s.eVar1 igual a &quot;3 minutos&quot;, que é o benchmark mais próximo de 3 minutos a 125 segundos

### Exemplo nº 7

O seguinte código...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...definirá s.eVar1 igual a &quot;2,4 minutos&quot;, que é o benchmark de 2/5 minutos mais próximo (por exemplo, .4 = 2/5) a 145 segundos

## Histórico da versão

### 1.1 (21 de maio de 2018)

* Adição do `bml` argumento para permitir mais flexibilidade no arredondamento

### 1.0 (15 de abril de 2018)

* Versão inicial.
