---
title: getVisitDuration
description: Rastreia por quanto tempo um visitante esteve no site até o momento.
translation-type: ht
source-git-commit: ca8e563118dcc74dfa718bd203db295faf4e9aa6
workflow-type: ht
source-wordcount: '585'
ht-degree: 100%

---


# Plug-in da Adobe: getVisitDuration

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getVisitDuration` rastreia o tempo em minutos do visitante no site até o momento. A Adobe recomenda usar esse plug-in se você deseja rastrear o tempo cumulativo no site até o momento ou rastrear o tempo necessário para executar uma atividade. Esse plug-in não rastreia o tempo entre eventos; se essa funcionalidade for a desejada, use o plug-in [`getTimeBetweenEvents`](gettimebetweenevents.md).

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
   * Tipo de ação: inicializar getVisitDuration
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
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getVisitDuration` não usa nenhum argumento. Ele retorna um dos valores a seguir:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (onde `[x]` é o número de minutos passados desde que o visitante chegou ao site)

Esse plug-in cria um cookie próprio chamado `"s_dur"`, que é o número de milissegundos decorridos desde que o visitante chegou ao site. O cookie expira após 30 minutos de inatividade.

## Exemplos de chamadas

### Exemplo #1

O código a seguir...

```js
s.eVar10 = s.getVisitDuration();
```

...sempre definirá a eVar10 como o número de minutos passados desde que o visitante chegou ao site.

### Exemplo #2

O código a seguir...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...usa o plug-in inList para verificar se a variável de eventos contém o evento de compra.  Em caso positivo, a eVar10 será definida como o número de minutos entre o início da visita do visitante e o momento da compra.

### Exemplo #3

O código a seguir...

```js
s.prop10 = s.getVisitDuration();
```

...sempre definirá a prop10 como o número de minutos passados desde que o visitante chegou ao site.  Isso será útil se prop10 tiver a definição de caminho ativada.  Adicionar a métrica &quot;saídas&quot; ao relatório prop10 mostrará um relatório granular e dispersivo da duração de uma visita em minutos antes de um visitante sair do site.

## Histórico da versão

### 2.1 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.0 (2 de maio de 2018)

* Lançamento pontual (reanálise/reescrita completa do plug-in).
