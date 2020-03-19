---
title: getTimeBetweenEvents
description: Meça a quantidade de tempo entre dois eventos.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Plug-in da Adobe: getTimeBetweenEvents

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getTimeBetweenEvents` plug-in permite rastrear a quantidade de tempo entre dois eventos do Analytics, incluindo carrinho de compras e eventos personalizados. É útil para rastrear a quantidade de tempo que um processo de finalização leva para ser concluído, ou qualquer outro processo que você deseja medir o tempo. Este plug-in é desnecessário se você não tiver nenhum processo de conversão que você queira medir quanto tempo eles levam.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Catalog] botão
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar getTimeBetweenEvents
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão na extensão do Adobe Analytics.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

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

O `getTimeBetweenEvents` método usa os seguintes argumentos:

* **`ste`** (obrigatório, string): Iniciar eventos de temporizador. Uma string delimitada por vírgulas de eventos do Analytics para &quot;iniciar o timer&quot;.
* **`rt`** (obrigatório, booleano): Reinicie a opção de temporizador. Defina como `true` se você deseja reiniciar o timer toda vez que a `events` variável contiver um evento de temporizador de início. Defina como `false` se não quiser que o temporizador seja reiniciado quando ele visualizar um evento de temporizador de início.
* **`stp`** (obrigatório, string): Pare os eventos de temporizador. Uma string delimitada por vírgulas de eventos do Analytics que &quot;interrompem o timer&quot;.
* **`res`** (obrigatório, booleano): Opção Redefinir temporizador. Defina para `true` se quiser gravar o tempo desde que o timer começou E redefina o timer depois que ele parar. Defina como `false` se você deseja gravar a hora, mas não parar o timer. Se definido como `false`, o temporizador continua sendo executado depois que a variável events registra um evento stop.
   > [!TIP] Se você definir esse argumento como `false`, é altamente recomendável configurar o `rte` argumento abaixo.
* **`cn`** (opcional, string): O nome do cookie no qual a hora do primeiro evento é armazenada. O padrão é `"s_tbe"`.
* **`etd`** (opcional, número inteiro): A hora de expiração do cookie em dias. Defina para `0` expirar no final da sessão do navegador. O padrão é 1 dia quando não está definido.
* **`fmt`** (opcional, string): O formato do tempo em que o número de segundos é retornado (o padrão é nada)
   * `"s"` por segundos
   * `"m"` por minutos
   * `"h"` por horas
   * `"d"` durante dias
   * Quando não estiver definido, o formato do valor de retorno será baseado nas seguintes regras:
      * Qualquer coisa menor que um minuto é arredondada para o valor de referência de 5 segundos mais próximo. Por exemplo, 10 segundos, 15 segundos
      * Qualquer coisa entre um minuto e uma hora é arredondada para o benchmark de 1/2 minutos mais próximo. Por exemplo, 30,5 minutos, 31 minutos
      * Qualquer coisa entre uma hora e um dia é arredondada para o benchmark de trimestre mais próximo. Por exemplo, 2,25 horas, 3,5 horas
      * Qualquer coisa maior que um dia é arredondada para o valor de referência de dia mais próximo. Por exemplo, 1 dia, 3 dias, 9 dias
* **`bml`** (opcional, número): A duração do referencial de arredondamento de acordo com o formato do `fmt` argumento. Por exemplo, se o `fmt` argumento for `"s"` e esse argumento for `2`, o valor de retorno será arredondado para o benchmark de 2 segundos mais próximo. Se o `fmt` argumento for `"m"` e esse argumento for `0.5`, o valor de retorno será arredondado para o benchmark de meio minuto mais próximo.
* **`rte`** (opcional, string): Sequência de caracteres delimitada por vírgulas de eventos do Analytics que removem ou excluem o timer. O padrão é nada.

Chamar esse método retorna um número inteiro que representa a quantidade de tempo entre o evento de temporizador de início e o evento de temporizador de parada no formato desejado.

## Exemplos de chamadas

### Exemplo nº 1

O seguinte código...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...está configurado para se comportar da seguinte maneira:

* O timer iniciará quando s.events contiver event1.
* O temporizador será reiniciado sempre que s.events contiver event1
* O timer parará quando s.events contiver event2
* O temporizador será redefinido (isto é, vai para 0 segundos) sempre que s.events contiver event2
* O temporizador também será redefinido quando s.events contiver event3 OU se o visitante fechar seu navegador
* Quando um tempo real entre event1 e event2 for registrado, o plug-in definirá eVar1 igual ao número de segundos entre os dois eventos que estão sendo definidos, arredondado para o benchmark mais próximo de 2 segundos (por exemplo, 0 segundos, 2 segundos, 4 segundos, 10 segundos, 184 segundos etc.)
* Se s.events contiver event2 antes de um timer ser iniciado, a eVar1 não será definida.

### Exemplo nº 2

O seguinte código...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...está configurado para se comportar da seguinte maneira:

* O timer iniciará quando s.events contiver event1.
* O timer NÃO será reiniciado sempre que s.events contiver event1, em vez disso, o timer original continuará em execução
* O timer NÃO parará quando s.events contiver event2, mas o plug-in registrará o tempo desde que a configuração original event1 foi registrada
* O temporizador é armazenado em um cookie chamado &quot;s_20&quot;
* O temporizador só será redefinido quando s.events contiver event3 OU se 20 dias tiverem passado desde que o temporizador foi iniciado
* Quando um tempo entre (o original) event1 e event2 for registrado, o plug-in definirá eVar1 igual ao número de horas entre os dois eventos que estão sendo definidos, arredondado para o benchmark mais próximo de 1/2 horas (por exemplo, 0 horas, 1,5 horas, 3 horas, 7,5 horas, 478,5 horas, etc.)

### Exemplo 3

O seguinte código...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...produzirão resultados semelhantes ao do primeiro exemplo acima; no entanto, o valor da eVar1 é retornado em segundos, minutos, horas ou dias, dependendo do comprimento final do timer.  Além disso, o timer expirará 1 dia após ter sido definido pela primeira vez em vez de no momento em que o visitante fechar seu navegador.

## Histórico da versão

### 2.1 (26 de maio de 2018)

* Acomoda as alterações feitas na nova versão do `formatTime` plug-in.

### 2.0 (6 de abril de 2018)

* Reescrita/reanálise completa do plug-in.
