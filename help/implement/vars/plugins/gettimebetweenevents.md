---
title: getTimeBetweenEvents
description: Meça a quantidade de tempo entre dois eventos.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getTimeBetweenEvents

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getTimeBetweenEvents` permite rastrear a quantidade de tempo entre dois eventos do Analytics, incluindo o carrinho de compras e eventos personalizados. É útil para rastrear a quantidade de tempo que um processo de finalização leva para ser concluído, ou para qualquer outro processo que você deseja medir o tempo. Este plug-in é desnecessário se não houver nenhum processo de conversão cujo tempo de execução você queira medir.

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
   * Tipo de ação: inicializar getTimeBetweenEvents
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
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getTimeBetweenEvents` aceita os seguintes argumentos:

* **`ste`** (obrigatório, string): iniciar eventos de cronômetro. Uma string delimitada por vírgulas composta por eventos do Analytics para os quais deve-se &quot;iniciar o cronômetro&quot;.
* **`rt`** (obrigatório, booleano): reinicie a opção de cronômetro. Defina como `true` se você deseja reiniciar o cronômetro toda vez que a variável `events` contiver um evento de início de cronômetro. Defina como `false` se não quiser que o cronômetro seja reiniciado quando detectar um evento de início de cronômetro.
* **`stp`** (obrigatório, string): eventos de parada de cronômetro. Uma string delimitada por vírgulas composta por eventos do Analytics para os quais deve-se &quot;Parar o cronômetro&quot;.
* **`res`** (obrigatório, booleano): opção para reiniciar o cronômetro. Defina para `true` se quiser gravar o tempo corrido pelo cronômetro e reiniciá-lo depois que ele parar. Defina como `false` se você deseja gravar a hora, mas não deseja parar o cronômetro. Se estiver definido como `false`, o cronômetro continua sendo executado depois que a variável de eventos registra um evento stop.
   > [!TIP] Se você definir esse argumento como `false`, é altamente recomendável configurar o argumento `rte` abaixo.
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
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

... está configurado para se comportar da seguinte maneira:

* O cronômetro será iniciado quando s.events contiver event1.
* O cronômetro será reiniciado sempre que s.events contiver event1
* O cronômetro parará quando s.events contiver event2
* O cronômetro será redefinido (isto é, vai para 0 segundos) sempre que s.events contiver event2
* O cronômetro também será redefinido quando s.events contiver event3 OU se o visitante fechar o navegador
* Quando um tempo real entre event1 e event2 for registrado, o plug-in definirá eVar1 como o número de segundos decorridos entre os dois eventos que estão sendo definidos, arredondado para o referencial de 2 segundos que estiver mais próximo (por exemplo, 0 segundos, 2 segundos, 4 segundos, 10 segundos, 184 segundos etc.)
* Se s.events contiver event2 antes de um cronômetro ser iniciado, a eVar1 não será definida.

### Exemplo #2

O código a seguir...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

... está configurado para se comportar da seguinte maneira:

* O cronômetro será iniciado quando s.events contiver event1.
* O cronômetro NÃO será reiniciado sempre que s.events contiver event1; em vez disso, o cronômetro original continuará em execução
* O cronômetro NÃO parará quando s.events contiver event2, mas o plug-in registrará o tempo decorrido desde quando a configuração original event1 foi registrada
* O cronômetro é armazenado em um cookie chamado &quot;s_20&quot;
* O cronômetro só será redefinido quando s.events contiver event3 OU se 20 dias tiverem passado desde que o cronômetro foi iniciado
* Quando um tempo decorrido entre event1 (o original) e event2 for registrado, o plug-in definirá eVar1 como o número de horas decorridas entre os dois eventos que estão sendo definidos, arredondado para o referencial de uma hora e meia que estiver mais próximo (por exemplo, 0 horas, 1,5 hora, 3 horas, 7,5 horas, 478,5 horas etc.)

### Exemplo #3

O código a seguir...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

... produzirá resultados semelhantes ao do primeiro exemplo acima; no entanto, o valor da eVar1 é retornado em segundos, minutos, horas ou dias, dependendo do tamanho final do cronômetro.  Além disso, o cronômetro expirará 1 dia após ter sido definido pela primeira vez em vez de no momento em que o visitante fechar o navegador.

## Histórico da versão

### 2.1 (26 de maio de 2018)

* Acomoda as alterações feitas na nova versão do plug-in `formatTime`.

### 2.0 (6 de abril de 2018)

* Reescrita/reanálise completa do plug-in.
