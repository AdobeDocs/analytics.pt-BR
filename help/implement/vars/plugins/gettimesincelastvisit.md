---
title: getTimeSinceLastVisit
description: Meça a quantidade de tempo decorrido entre duas visitas.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getTimeSinceLastVisit

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getTimeSinceLastVisit` permite rastrear quanto tempo um visitante levou para retornar ao site após sua última visita.

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
   * Tipo de ação: inicializar getTimeSinceLastVisit
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
/* Adobe Consulting Plugin: getTimeSinceLastVisit v1.0 (Requires formatTime and inList plug-ins) */
s.getTimeSinceLastVisit=function(){var s=this,a=new Date,b=a.getTime(),c=s.c_r("s_tslv")||0,d=Math.round((b-c)/1E3);a.setTime(b+63072E6);s.c_w("s_tslv",b,a);return c?1800<d&&s.formatTime?s.formatTime(d):"":"New Visitor"};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
 /******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getTimeSinceLastVisit` não usa nenhum argumento. Ele retorna o tempo decorrido desde o último acesso do visitante, simplificado no seguinte formato:

* O tempo entre 30 minutos e uma hora desde a última visita é definido para o referencial de meio minuto que estiver mais próximo. Por exemplo, `"30.5 minutes"`, `"53 minutes"`.
* O tempo entre uma hora e um dia é arredondado para o referencial de 1/4 de hora que estiver mais próximo. Por exemplo, `"2.25 hours"`, `"7.5 hours"`.
* O tempo maior que um dia é arredondado para o valor referencial de dia que estiver mais próximo. Por exemplo, `"1 day"`, `"3 days"`, `"9 days"`, `"372 days"`.
* Se um visitante não tiver visitado antes ou o se tempo decorrido for superior a dois anos, o valor será definido como `"New Visitor"`.

>[!NOTE] Esse plug-in retorna apenas um valor na primeira ocorrência de uma visita.

Esse plug-in cria um cookie primário chamado `"s_tslv"`, definido como um carimbo de data e hora de Unix com a hora atual. O cookie expira após dois anos de inatividade.

## Exemplos de chamadas

### Exemplo #1

Se um visitante novinho em folha chegar ao site e o código a seguir for executado na primeira página da visita...

```javascript
s.prop1 = s.getTimeSinceLastVisit();
s.linkTrackVars = s.apl(s.linkTrackVars, "prop1") //ensures that prop1 will be included on the first hit of the visit
```

... o valor de s.prop1 será definido como &quot;Novo visitante&quot;.

Se o mesmo código for executado no mesmo domínio após 35 minutos de inatividade, o valor de s.prop1 será definido como &quot;35 minutos&quot;.

Se o mesmo código for executado no mesmo domínio após 4 dias de inatividade o valor de s.prop1 será definido como &quot;4 dias&quot;.

## Histórico da versão

### 1.0 (16 de abril de 2018)

* Versão pontual (código recompilado e de menor tamanho).
* Código derivado do plug-in `getDaysSinceLastVisit` (agora obsoleto e renomeado).
* Agora usa os plug-ins `formatTime` e `inList` no valor de retorno.
