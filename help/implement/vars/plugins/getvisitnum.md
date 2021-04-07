---
title: getVisitNum
description: Rastreia o número da visita atual de um visitante.
translation-type: ht
source-git-commit: fb1cdcb53732be46037a79587fc2541e629496e3
workflow-type: ht
source-wordcount: '1048'
ht-degree: 100%

---


# Plug-in da Adobe: getVisitNum

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getVisitNum` retorna o número da visita para todos os visitantes que chegam ao site dentro do número desejado de dias. O Analysis Workspace oferece uma dimensão &quot;Número de visitas&quot; que fornece funcionalidade semelhante. A Adobe recomenda usar esse plug-in se você quiser mais controle sobre como o número de visitas é incrementado. Esse plug-in é desnecessário se a dimensão &quot;Número de visitas&quot; integrada no Analysis Workspace for suficiente para suas necessidades de relatórios.

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
   * Tipo de ação: inicializar getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getVisitNum` aceita os seguintes argumentos:

* **`rp`** (opcional, número inteiro OU string): o número de dias antes da redefinição do contador do número de visitas.  O valor padrão é `365` quando um valor não está definido.
   * Quando esse argumento é `"w"`, o contador é reiniciado no final da semana (neste sábado, às 23:59)
   * Quando esse argumento é `"m"`, o contador é redefinido no final do mês (o último dia deste mês)
   * Quando esse argumento é `"y"`, o contador é reiniciado no final do ano (31 de dezembro)
* **`erp`** (opcional, booleano): Quando o argumento `rp` é um número, esse argumento determina se a expiração do número de visitas deve ser estendida. Se definido como `true`, as ocorrências subsequentes do site redefinirão o contador de número de visitas. Se definido como `false`, as ocorrências subsequentes do site serão estendidas quando o contador de número de visitas é redefinido. O padrão é `true`. Esse argumento não é válido quando o argumento `rp` é uma string.

O número de visitas aumenta sempre que o visitante retorna ao site após 30 minutos de inatividade. Chamar esse método retorna um número inteiro que representa o número de visita atual do visitante.

Este plug-in define um cookie próprio chamado `"s_vnc[LENGTH]"`, onde `[LENGTH]` é o valor transmitido para o argumento `rp`. Por exemplo, `"s_vncw"`, `"s_vncm"` ou `"s_vnc365"`. O valor do cookie é uma combinação de um carimbo de data e hora de Unix que representa o momento quando o contador de visitas é redefinido, como um fim da semana, fim do mês ou após 365 dias de inatividade. Também contém o número de visitas atual. Este plug-in define outro cookie chamado `"s_ivc"`, que está definido como `true` e expira após 30 minutos de inatividade.

## Exemplos de chamadas

### Exemplo #1

Para um visitante que não esteve no site nos últimos 365 dias, o código a seguir definirá s.prop1 como 1:

```js
s.prop1=s.getVisitNum();
```

### Exemplo #2

Para um visitante que retorna ao site dentro de 364 dias após sua primeira visita, o seguinte código definirá s.prop1 como 2:

```js
s.prop1=s.getVisitNum(365);
```

Se esse visitante retornar ao site dentro de 364 dias após sua segunda visita, o código a seguir definirá s.prop1 como 3:

```js
s.prop1=s.getVisitNum(365);
```

### Exemplo #3

Para um visitante que retorna ao site dentro de 179 dias após sua primeira visita, o seguinte código definirá s.prop1 como 2:

```js
s.prop1=s.getVisitNum(180,false);
```

No entanto, se esse visitante retornar ao site um ou mais dias após sua segunda visita, o código a seguir definirá s.prop1 como 1:

```js
s.prop1=s.getVisitNum(180,false);
```

Quando o segundo argumento na chamada for igual a false, a rotina que determina quando o número de visitas deve ser &quot;redefinido&quot; para 1 fará isso durante um número &quot;x&quot; de dias - neste exemplo, 365 dias - após a primeira visita do visitante ao site.

Quando o segundo argumento for igual a true (ou não for definido), o plug-in redefinirá o número de visita para 1 somente após um número &quot;x&quot; de dias - novamente, neste exemplo, 365 dias - de inatividade do visitante.

### Exemplo #4

Para todos os visitantes que chegam ao site pela primeira vez durante a semana atual - começando no domingo - o código a seguir definirá s.prop1 como 1:

```js
s.prop1=s.getVisitNum("w");
```

### Exemplo #5

Para todos os visitantes que chegam ao site pela primeira vez durante o mês atual - começando no primeiro dia de cada mês - o código a seguir definirá s.prop1 como 1:

```js
s.prop1=s.getVisitNum("m");
```

Lembre-se que o plug-in getVisitNum não considera calendários de varejo (ou seja, 4-5-4, 4-4-5 etc.)

### Exemplo #6

Para todos os visitantes que chegam ao site pela primeira vez durante o ano atual - começando em 1º de janeiro - o código a seguir definirá s.prop1 como 1:

```js
s.prop1=s.getVisitNum("y");
```

### Exemplo #7

Se você deseja rastrear o número de visitas de um visitante naquela semana, mês e ano - tudo dentro de diferentes variáveis do Analytics - você deve usar um código semelhante ao seguinte:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

Nesse caso, o plug-in criará três cookies diferentes - um para cada um dos diferentes períodos - para rastrear o número de visitas individuais por período.

## Histórico da versão

### 4.2 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 4.11 (30 de setembro de 2019)

* Correção de um problema em que o argumento `erp` era explicitamente definido como `false`.

### 4.1 (21 de maio de 2018)

* Atualização do plug-in `endOfDatePeriod` para v1.1.

### 4.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Argumentos de cookie removidos, pois o plug-in agora gera cookies dinamicamente com base no argumento `rp`).

### 3.0 (5 de junho de 2016)

* Reformulação completa.
* Combinadas todas as soluções anteriores disponíveis em várias versões do plug-in `getVisitNum`.
