---
title: getQueryParam
description: Extraia o valor de um parâmetro de string de consulta do URL.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 74%

---

# Plug-in da Adobe: getQueryParam

{{plug-in}}

O plug-in `getQueryParam` permite que você extraia o valor de qualquer parâmetro de string de consulta contido em um URL. É útil para extrair códigos de campanha, internos e externos, de URLs de páginas iniciais. Também é importante ao extrair termos de pesquisa ou outros parâmetros da string de consulta.

Esse plug-in fornece recursos robustos para a análise de URLs complexos, incluindo hashes e URLs que contêm vários parâmetros de string de consulta. Se você precisa apenas de parâmetros de string de consulta simples, o Adobe recomenda usar os recursos de parâmetros de URL usando o SDK da Web, a extensão do Adobe Analytics ou o [`Util.getQueryParam()`](../functions/util-getqueryparam.md) método incluído no AppMeasurement.

## Instale o plug-in usando a extensão SDK da Web

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o SDK da Web.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Tags]** à esquerda e clique na propriedade de tag desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda e, em seguida, clique na guia **[!UICONTROL Catálogo]** guia
1. Localize e instale o **[!UICONTROL Plug-ins comuns do SDK da Web]** extensão.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda e, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: plug-ins comuns do SDK da Web
   * Elemento de dados: `getQueryParam`
1. Defina os parâmetros desejados à direita.
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
   * Tipo de ação: inicializar getQueryParam
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão de plug-in de plug-ins comuns do Analytics, poderá usar o editor de código personalizado.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getQueryParam` usa os seguintes argumentos:

* **`qsp`** (obrigatório): uma lista delimitada por vírgulas com parâmetros da string de consulta a serem procurados no URL. Não diferencia maiúsculas e minúsculas.
* **`de`** (opcional): o delimitador a ser usado se vários parâmetros da string de consulta corresponderem. O padrão é uma string vazia.
* **`url`** (opcional): um URL, string ou variável personalizados usados para extrair os valores de parâmetro da string de consulta. O padrão é `window.location`.

Chamar essa função retorna um valor diferente dependendo dos argumentos acima e da URL:

* Se um parâmetro de string de consulta correspondente não for encontrado, a função retornará uma string vazia.
* Se um parâmetro de string de consulta correspondente for encontrado, a função retornará o valor do parâmetro da string de consulta.
* Se um parâmetro de string de consulta correspondente for encontrado, mas o valor estiver vazio, a função retornará `true`.
* Se vários parâmetros de string de consulta correspondentes forem encontrados, a função retornará uma string com cada valor de parâmetro delimitado pela string no argumento `de`.

## Exemplos

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## Histórico da versão

### 4.0.1 (26 de março de 2021)

* Atualização do problema em que indefinido era retornado em vez de &quot;&quot; se o parâmetro de consulta não estivesse presente na sequência de consulta.

### 4.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.
* Remoção de dependências no plug-in pt.

### 3.3 (24 de setembro de 2019)

* Lógica desnecessária ignorada para reduzir o tamanho do código

### 3.2 (15 de maio de 2018)

* Funções `findParameterValue` e `getParameterValue` movidas para a função `getQueryParam`

### 3.1 (10 de maio de 2018)

* Correção de um problema na captura de parâmetros sem valor da string de consulta

### 3.0 (16 de abril, 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Funções auxiliares renomeadas para `findParameterValue` e `getParameterValue` para fins de legibilidade.
* Foi removida a necessidade de adicionar um argumento para localização de parâmetros contidos no hash do URL

### 2.5 (8 de janeiro de 2016)

* Compatível com H-code e AppMeasurement (requer `s.pt` com o AppMeasurement).

### 2.4

* Foi adicionado o parâmetro `h`, permitindo que o código localize os parâmetros da string de consulta que estão após o hash (`#`)

### 2.3

* Correção de um problema de regressão em que o plug-in funcionava somente quando o hash estava presente após o código de rastreamento

### 2.2

* Agora remove os caracteres de hash (e tudo depois) do valor de retorno

### 2.1

* Compatível com o H.10 code
