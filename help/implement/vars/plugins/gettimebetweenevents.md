---
title: getTimeBetweenEvents
description: Meça a quantidade de tempo entre dois eventos.
translation-type: tm+mt
source-git-commit: e8c6f4bbc72f7edfd966d698b8e4678e5eaa739e
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 99%

---


# Plug-in da Adobe: getTimeBetweenEvents

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getTimeBetweenEvents` permite rastrear a quantidade de tempo entre dois eventos do Analytics, incluindo o carrinho de compras e eventos personalizados. É útil para rastrear a quantidade de tempo que um processo de finalização leva para ser concluído, ou para qualquer outro processo que você deseja medir o tempo. Este plug-in é desnecessário se não houver nenhum processo de conversão cujo tempo de execução você queira medir.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getTimeBetweenEvents
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getTimeBetweenEvents` aceita os seguintes argumentos:

* **`ste`** (obrigatório, string): iniciar eventos de cronômetro. Uma string delimitada por vírgulas composta por eventos do Analytics para os quais deve-se &quot;iniciar o cronômetro&quot;.
* **`rt`** (obrigatório, booleano): reinicie a opção de cronômetro. Defina como `true` se você deseja reiniciar o cronômetro toda vez que a variável `events` contiver um evento de início de cronômetro. Defina como `false` se não quiser que o cronômetro seja reiniciado quando detectar um evento de início de cronômetro.
* **`stp`** (obrigatório, string): eventos de parada de cronômetro. Uma string delimitada por vírgulas composta por eventos do Analytics para os quais deve-se &quot;Parar o cronômetro&quot;.
* **`res`** (obrigatório, booleano): opção para reiniciar o cronômetro. Defina para `true` se quiser gravar o tempo corrido pelo cronômetro e reiniciá-lo depois que ele parar. Defina como `false` se você deseja gravar a hora, mas não deseja parar o cronômetro. Se estiver definido como `false`, o cronômetro continua sendo executado depois que a variável de eventos registra um evento stop.

   >[!TIP]
   >
   >Se você definir esse argumento como `false`, é altamente recomendável configurar o argumento `rte` abaixo.
* **`cn`** (opcional, string): o nome do cookie no qual a hora do primeiro evento é armazenada. O padrão é `"s_tbe"`.
* **`etd`** (opcional, número inteiro): a expiração do cookie em dias. Defina como `0` para que expire no final da sessão do navegador. O padrão é 1 dia quando não está definido.
* **`fmt`** (opcional, string): o formato de tempo em que o número de segundos é retornado (o padrão é não ter valor)
   * `"s"` para segundos
   * `"m"` para minutos
   * `"h"` para horas
   * `"d"` para dias
   * Quando não estiver definido, o formato do valor de retorno será baseado nas seguintes regras:
      * Qualquer coisa menor que um minuto é arredondada para o referencial de 5 segundos que estiver mais próximo. Por exemplo, 10 segundos, 15 segundos
      * Qualquer coisa entre um minuto e uma hora é arredondada para o referencial de 1/2 minuto que estiver mais próximo. Por exemplo, 30,5 minutos, 31 minutos
      * Qualquer coisa entre uma hora e um dia é arredondada para o referencial de 1/4 de hora que estiver mais próximo. Por exemplo, 2,25 horas, 3,5 horas
      * Qualquer coisa maior que um dia é arredondada para o valor referencial de dia que estiver mais próximo. Por exemplo, 1 dia, 3 dias, 9 dias
* **`bml`** (opcional, número): a quantidade de tempo do referencial de arredondamento de acordo com o formato do argumento `fmt`. Por exemplo, se o argumento `fmt` for `"s"` e esse argumento for `2`, o valor de retorno será arredondado para o referencial de 2 segundos que estiver mais próximo. Se o argumento `fmt` for `"m"` e esse argumento for `0.5`, o valor de retorno será arredondado para o referencial de meio minuto que estiver mais próximo.
* **`rte`** (opcional, string): string delimitada por vírgulas com eventos do Analytics que removem ou excluem o cronômetro. O padrão é não ter valor.

Chamar esse método retorna um número inteiro que representa a quantidade de tempo entre o evento de início de cronômetro e o evento de parada de cronômetro no formato desejado.

## Exemplos de chamadas

### Exemplo #1

O código a seguir...

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

... está configurado para se comportar da seguinte maneira:

* O cronômetro será iniciado quando s.events contiver event1
* O cronômetro será reiniciado sempre que s.events contiver event1
* O cronômetro parará quando s.events contiver event2
* O cronômetro será redefinido (isto é, vai para 0 segundos) sempre que s.events contiver event2
* O cronômetro também será redefinido quando s.events contiver event3 OU se o visitante fechar o navegador
* Quando um tempo real entre event1 e event2 for registrado, o plug-in definirá eVar1 como o número de segundos decorridos entre os dois eventos que estão sendo definidos, arredondado para o referencial de 2 segundos que estiver mais próximo (por exemplo, 0 segundos, 2 segundos, 4 segundos, 10 segundos, 184 segundos etc.)
* Se s.events contiver event2 antes de um cronômetro ser iniciado, a eVar1 não será definida.

### Exemplo #2

O código a seguir...

```js
s.eVar1 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

... está configurado para se comportar da seguinte maneira:

* O cronômetro será iniciado quando s.events contiver event1
* O cronômetro NÃO será reiniciado sempre que s.events contiver event1; em vez disso, o cronômetro original continuará em execução
* O cronômetro NÃO parará quando s.events contiver event2, mas o plug-in registrará o tempo decorrido desde quando a configuração original event1 foi registrada
* O cronômetro é armazenado em um cookie chamado &quot;s_20&quot;
* O cronômetro só será redefinido quando s.events contiver event3 OU se 20 dias tiverem passado desde que o cronômetro foi iniciado
* Quando um tempo decorrido entre event1 (o original) e event2 for registrado, o plug-in definirá eVar1 como o número de horas decorridas entre os dois eventos que estão sendo definidos, arredondado para o referencial de uma hora e meia que estiver mais próximo (por exemplo, 0 horas, 1,5 hora, 3 horas, 7,5 horas, 478,5 horas etc.)

### Exemplo #3

O código a seguir...

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true);
```

... produzirá resultados semelhantes ao do primeiro exemplo acima; no entanto, o valor da eVar1 é retornado em segundos, minutos, horas ou dias, dependendo do tamanho final do cronômetro.  Além disso, o cronômetro expirará 1 dia após ter sido definido pela primeira vez em vez de no momento em que o visitante fechar o navegador.

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.1 (26 de maio de 2018)

* Acomoda as alterações feitas na nova versão do plug-in `formatTime`.

### 2.0 (6 de abril de 2018)

* Reescrita/reanálise completa do plug-in.
