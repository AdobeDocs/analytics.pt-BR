---
title: getTimeToComplete
description: Meça o tempo gasto para concluir uma tarefa.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getTimeToComplete

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getTimeToComplete` rastreia o tempo que um usuário leva para concluir um processo em um site. O &quot;relógio&quot; começa quando a ação `start` é chamada e termina quando a ação `stop` é chamada. A Adobe recomenda usar esse plug-in se houver um fluxo de trabalho no site que demore algum tempo para ser concluído e você quiser saber quanto tempo os visitantes levam para concluí-lo. Não é necessário usar esse plug-in se o fluxo de trabalho do site levar um curto período de tempo (menos de 3 segundos), pois a granularidade chega a, no mínimo, um segundo completo.

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
   * Tipo de ação: inicializar getTimeToComplete
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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getTimeToComplete` aceita os seguintes argumentos:

* **`sos`** (opcional, string): defina como `"start"` quando quiser iniciar o cronômetro. Defina como `"stop"` quando quiser parar o cronômetro. O padrão é `"start"`.
* **`cn`** (opcional, string): o nome do cookie que armazenará o tempo inicial. O padrão é `"s_gttc"`.
* **`exp`** (opcional, número inteiro): o número de dias que dura o cookie (e o cronômetro). O padrão é `0`, que representa o fim da sessão do navegador.

Chamar esse método retorna uma string que contém o número de dias, horas, minutos e/ou segundos decorridos entre a ação `"start"` e a ação `"stop"`.

## Exemplos de chamadas

### Exemplo #1

Use essas chamadas para determinar o tempo decorrido entre o momento em que um visitante inicia o processo de finalização e o momento em que realiza uma compra.

Inicie o cronômetro quando o visitante iniciar a finalização:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Pare o cronômetro quando o visitante fizer a compra e defina prop1 como a diferença de tempo entre a parada e o início:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 capturará o tempo necessário para concluir o processo de compra

### Exemplo #2

Se você quiser ter vários cronômetros em execução ao mesmo tempo (para medir processos diferentes), será necessário definir manualmente o argumento de cookie cn.  Por exemplo, se você quiser medir a quantidade de tempo necessária para que uma compra seja concluída, defina o código a seguir...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

... mas se você também quiser medir (ao mesmo tempo) o tempo necessário para preencher um formulário de inscrição, execute também seguinte código:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

No segundo exemplo, event1 deve capturar o início de um processo de registro que pode levar até 7 dias para ser concluído (por qualquer motivo), e event2 deve capturar a conclusão do registro.  s.prop2 capturará o tempo necessário para concluir o processo de registro

## Histórico da versão

### 3.1 (30 de setembro de 2019)

* Foi adicionada uma lógica que requer um valor &quot;start&quot; ou &quot;stop&quot; no primeiro argumento.  Todos os outros valores passados impedem a execução do plug-in.
* Atualização do plug-in `inList 2.0` para `inList 2.1`.

### 3.0 (23 de agosto de 2018)

* Atualização do plug-in `formatTime v1.0` para `formatTime v1.1`.

### 3.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Correção de erros secundários.

### 2.0 (21 de junho de 2016)

* Eliminação da dependência do plug-in `p_fo`.
* Compatibilidade adicionada com o H-code e o AppMeasurement.
* Adicionado o registro de log do console.
