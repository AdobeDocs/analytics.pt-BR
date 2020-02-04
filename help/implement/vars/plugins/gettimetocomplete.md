---
title: getTimeToComplete
description: Meça o tempo gasto para concluir uma tarefa.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe: getTimeToComplete

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getTimeToComplete` plug-in rastreia o tempo que um usuário leva para concluir um processo em um site. O &quot;relógio&quot; começa quando a `start` ação é chamada e termina quando a `stop` ação é chamada. A Adobe recomenda usar esse plug-in se houver um fluxo de trabalho no site que demore algum tempo para ser concluído e você quiser saber quanto tempo os visitantes levam para concluí-lo. Não é necessário usar esse plug-in se o fluxo de trabalho do site levar um curto período de tempo (menos de 3 segundos), pois a granularidade está apenas em um segundo completo.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar getTimeToComplete
1. Salve e publique as alterações na regra.

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
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getTimeToComplete` método usa os seguintes argumentos:

* **`sos`**(opcional, string): Defina para`"start"`quando quiser iniciar o timer. Defina para`"stop"`quando quiser parar o timer. O padrão é`"start"`.
* **`cn`**(opcional, string): O nome do cookie para armazenar a hora de início. O padrão é`"s_gttc"`.
* **`exp`**(opcional, número inteiro): O número de dias em que o cookie (e o timer) expira. O padrão é`0`, que representa o fim da sessão do navegador.

Chamar esse método retorna uma string que contém o número de dias, horas, minutos e/ou segundos que levou entre a ação `"start"` e a ação `"stop"` .

## Exemplos de chamadas

### Exemplo nº 1

Use essas chamadas para determinar o tempo entre o momento em que um visitante inicia o processo de checkout e o momento em que realiza uma compra.

Inicie o temporizador quando o visitante iniciar o check-out:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Pare o timer quando o visitante fizer a compra e definir prop1 para a diferença de tempo entre parar e iniciar:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 capturará o tempo necessário para concluir o processo de compra

### Exemplo nº 2

Se quiser ter vários temporizadores em execução ao mesmo tempo (para medir processos diferentes), será necessário definir manualmente o argumento de cookie cn.  Por exemplo, se você quiser medir a quantidade de tempo necessária para que uma compra seja concluída, defina o seguinte código...

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...mas se você também quiser medir (ao mesmo tempo) o tempo necessário para preencher um formulário de inscrição, execute o seguinte código também:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

No segundo exemplo, event1 deve capturar o início de um processo de registro que pode levar até 7 dias para ser concluído, por qualquer motivo, e event2 deve capturar a conclusão do registro.  s.prop2 capturará o tempo necessário para concluir o processo de registro

## Histórico da versão

### 3.1 (30 de setembro de 2019)

* Foi adicionada uma lógica que requer um valor de &quot;start&quot; ou &quot;stop&quot; no primeiro argumento.  Todos os outros valores passados impedem a execução do plug-in.
* Atualização do `inList 2.0` plug-in para `inList 2.1`.

### 3.0 (23 de agosto de 2018)

* Atualização do plug- `formatTime v1.0` -in para `formatTime v1.1`.

### 3.0 (17 de abril de 2018)

* Lançamento de ponto (recompilado, tamanho de código menor).
* Correção de erros secundários.

### 2.0 de junho de 2016)

* Eliminação da dependência do `p_fo` plug-in.
* Compatibilidade adicionada com o código H e o AppMeasurement.
* Adicionado o registro do console.
