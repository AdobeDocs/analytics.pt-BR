---
title: getVisitNum
description: Rastrear o número de visita atual de um visitante.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Plug-in da Adobe: getVisitNum

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudar a obter mais valor com o uso do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `getVisitNum` plug-in retorna o número de visita para todos os visitantes que chegam ao site dentro do número desejado de dias. A Analysis Workspace oferece uma dimensão &quot;Número de visitas&quot; que fornece funcionalidade semelhante. A Adobe recomenda usar esse plug-in se você quiser mais controle sobre como o número de visitas é incrementado. Esse plug-in é desnecessário se a dimensão &quot;Número de visitas&quot; integrada na Analysis Workspace for suficiente para suas necessidades de relatórios.

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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getVisitNum` método usa os seguintes argumentos:

* **`rp`**(opcional, número inteiro OU sequência): O número de dias antes da redefinição do contador do número de visitas.  O padrão é`365`quando não está definido.
   * Quando este argumento é `"w"`reiniciado, o contador é reiniciado no final da semana (neste sábado, às 23:59)
   * Quando esse argumento é exibido, `"m"`o contador é redefinido no final do mês (o último dia deste mês)
   * Quando este argumento é apresentado, `"y"`o contador é reiniciado no final do ano (31 de dezembro)
* **`erp`**(opcional, booleano): Quando o`rp`argumento é um número, esse argumento determina se a expiração do número de visita deve ser estendida. Se definido como`true`, as ocorrências subsequentes do site redefinirão o contador de número de visitas. Se definido como`false`, as ocorrências subsequentes do site não se estendem quando o contador de número de visitas é redefinido. O padrão é`true`. Esse argumento não é válido quando o`rp`argumento é uma string.

O número de visitas aumenta sempre que o visitante retorna ao site após 30 minutos de inatividade. Chamar esse método retorna um número inteiro que representa o número de visita atual do visitante.

Este plug-in define um cookie primário chamado `"s_vnc[LENGTH]"` onde `[LENGTH]` é o valor passado para o `rp` argumento. Por exemplo, `"s_vncw"`, `"s_vncm"`ou `"s_vnc365"`. O valor do cookie é uma combinação de um carimbo de data e hora Unix que representa quando o contador de visitas é redefinido, como fim da semana, fim do mês ou após 365 dias de inatividade. Também contém o número de visita atual. Este plug-in define outro cookie chamado `"s_ivc"` que é definido como `true` e expira após 30 minutos de inatividade.

## Exemplos de chamadas

### Exemplo nº 1

Para um visitante que não esteve no site nos últimos 365 dias, o código a seguir definirá s.prop1 igual ao valor de 1:

```js
s.prop1=s.getVisitNum();
```

### Exemplo nº 2

Para um visitante que retorna ao site dentro de 364 dias após sua primeira visita, o seguinte código definirá s.prop1 igual a 2:

```js
s.prop1=s.getVisitNum(365);
```

Se esse visitante retornar ao site dentro de 364 dias após sua segunda visita, o código a seguir definirá s.prop1 igual a 3:

```js
s.prop1=s.getVisitNum(365);
```

### Exemplo 3

Para um visitante que retorna ao site dentro de 179 dias após sua primeira visita, o seguinte código definirá s.prop1 igual a 2:

```js
s.prop1=s.getVisitNum(180,false);
```

No entanto, se esse visitante retornar ao site 1 ou mais dias após sua segunda visita, o código a seguir definirá s.prop1 igual a 1:

```js
s.prop1=s.getVisitNum(180,false);
```

Quando o segundo argumento na chamada for igual a false, a rotina que determina quando o número da visita deve ser &quot;redefinido&quot; para 1 fará isso com o número &quot;x&quot; de dias - neste exemplo, 365 dias - após a primeira visita do visitante ao site.

Quando o segundo argumento for igual a true (ou não definido), o plug-in redefinirá o número de visita para 1 somente após o número &quot;x&quot; de dias - novamente, neste exemplo, 365 dias - de inatividade do visitante.

### Exemplo nº 4

Para todos os visitantes que chegam ao site pela primeira vez durante a semana atual - começando no domingo - o seguinte código definirá s.prop1 igual a 1:

```js
s.prop1=s.getVisitNum("w");
```

### Exemplo nº 5

Para todos os visitantes que chegam ao site pela primeira vez durante o mês atual - começando no primeiro dia de cada mês - o código a seguir definirá s.prop1 igual a 1:

```js
s.prop1=s.getVisitNum("m");
```

Lembre-se de que o plug-in getVisitNum não considera calendários baseados em varejo (ou seja, 4-5-4, 4-4-5 etc.)

### Exemplo nº 6

Para todos os visitantes que acessam o site pela primeira vez durante o ano atual - começando em 1° de janeiro - o código a seguir definirá s.prop1 igual a 1:

```js
s.prop1=s.getVisitNum("y");
```

### Exemplo nº 7

Se você deseja rastrear o número de visita de um visitante para a semana, o número de visita de um visitante para o mês e o número de visita de um visitante para o ano - tudo dentro de diferentes variáveis do Analytics - você deve usar um código semelhante ao seguinte:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

Nesse caso, o plug-in criará três cookies diferentes - um para cada um dos diferentes períodos - para rastrear o número de visitas individuais por período.

## Histórico da versão

### 4.11 (30 de setembro de 2019)

* Correção de um problema em que o `erp` argumento era explicitamente definido como `false`.

### 4.1 (21 de maio de 2018)

* Atualização do plug- `endOfDatePeriod` -in para v1.1.

### 4.0 (17 de abril de 2018)

* Lançamento de ponto (recompilado, tamanho de código menor).
* Argumentos de cookie removidos, pois o plug-in agora gera dinamicamente cookies com base no `rp` argumento)

### 3.0 (5 de junho de 2016)

* Revisão completa
* Combinadas todas as soluções anteriores disponíveis em várias versões do `getVisitNum` plug-in.
