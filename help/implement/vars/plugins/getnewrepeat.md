---
title: getNewRepeat
description: Acompanhe a atividade de visitantes novos e repetidos.
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 74%

---

# Plug-in da Adobe: getNewRepeat

{{plug-in}}

O plug-in `getNewRepeat` permite determinar se um visitante do site é um novo visitante ou um visitante repetido dentro de um número desejado de dias. A Adobe recomenda usar esse plug-in se você quiser identificar os visitantes como &quot;novos&quot; usando um número personalizado de dias. Esse plug-in é desnecessário se as dimensões Novo/Repetir do visitante no Analysis Workspace atenderem às necessidades da sua organização.

## Instale o plug-in usando a extensão SDK da Web

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o SDK da Web.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Marcas]** à esquerda e clique na propriedade de marca desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda e na guia **[!UICONTROL Catálogo]**
1. Localize e instale a extensão **[!UICONTROL Plug-ins comuns do SDK da Web]**.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda e, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: plug-ins comuns do SDK da Web
   * Elemento de Dados: `getNewRepeat`
1. Defina o parâmetro `daysBeforeReset` à direita.
1. Salve e publique as alterações no elemento de dados.

## Instale o plug-in implementando manualmente o SDK da Web

Este plug-in ainda não é compatível com uma implementação manual do SDK da Web.

## Instale o plug-in usando a extensão Adobe Analytics.

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getNewRepeat
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão de plug-in de plug-ins comuns do Analytics, poderá usar o editor de código personalizado.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getNewRepeat` usa os seguintes argumentos:

* **`d`** (número inteiro, opcional): o número mínimo de dias necessários entre visitas que redefine os visitantes novamente como `"New"`. Se esse argumento não for definido, o padrão será 30 dias.

Essa função retornará o valor de `"New"` se o cookie definido pelo plug-in não existir ou tiver expirado. Ele retorna o valor `"Repeat"` se o cookie definido pelo plug-in existe e o se tempo desde a ocorrência atual e o tempo definido no cookie forem maiores que 30 minutos. Essa função retorna o mesmo valor para uma visita inteira.

Esse plug-in usa um cookie chamado `"s_nr[LENGTH]"`, onde `[LENGTH]` é igual ao argumento `d`. O cookie contém um carimbo de data e hora Unix que representa a hora atual e o status atual do visitante (`"New"` ou `"Repeat"`).

## Exemplos

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.1 (30 de setembro de 2019)

* Reorganização da lógica do JavaScript para reduzir o tamanho do plug-in

### 2.0 (16 de abril de 2018)

* Recompilado com menor tamanho de código
* Removida a capacidade de nomear o cookie para armazenar as informações de visita. O plug-in agora nomeia dinamicamente o cookie com base no valor passado para o argumento `d`.
