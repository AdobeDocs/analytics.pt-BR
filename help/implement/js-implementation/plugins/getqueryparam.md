---
description: Retorna o valor de um parâmetro especificado da string de consulta, se for encontrado no URL da página atual. Como os dados importantes (tais como códigos de rastreamento de campanha, palavras-chave de pesquisa interna etc.) estão disponíveis na sequência de caracteres de consulta em uma página, o getQueryParam ajuda a capturar os dados nas variáveis do Analytics.
keywords: Implementação do Analytics
seo-description: Retorna o valor de um parâmetro especificado da string de consulta, se for encontrado no URL da página atual. Como os dados importantes (tais como códigos de rastreamento de campanha, palavras-chave de pesquisa interna etc.) estão disponíveis na sequência de caracteres de consulta em uma página, o getQueryParam ajuda a capturar os dados nas variáveis do Analytics.
seo-title: getQueryParam
solution: Analytics
subtopic: Plug-ins
title: ' getQueryParam'
topic: Desenvolvedor e implementação
uuid: ba 202756-c 728-4 ebc -8 fd 9-5 bc 29 a 9 f 673 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getQueryParam

Retorna o valor de um parâmetro especificado da string de consulta, se for encontrado no URL da página atual. Como os dados importantes (tais como códigos de rastreamento de campanha, palavras-chave de pesquisa interna etc.) estão disponíveis na sequência de caracteres de consulta em uma página, o getQueryParam ajuda a capturar os dados nas variáveis do Analytics.

>[!IMPORTANT]
>
>Esse plug-in é usado somente pelo código H. [O appmeasurement para javascript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) fornece essa funcionalidade nativa usando [Util. getqueryparam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

Once installed in your [!DNL AppMeasurement] for JavaScript code, the plug-in is configured by selecting a [!DNL Analytics] variable to populate using data found in the query string, and specifying which query string values to capture. O plug-in detecta a string de consulta especificada, se houver, e preenche a variável escolhida com seu valor. Se nenhum parâmetro de string de consulta for encontrado com esse valor, uma string vazia é retornada. If a query string parameter exists but does not have a value (such as param1 in `?param1&param2=value`), the word *`true`* is returned.

>[!NOTE]
>
>The base code for the plug-in must be installed in your [!DNL AppMeasurement] for JavaScript code before the examples below will work.

If you wanted to use *`s.campaign`* to capture campaign tracking codes available as values of the *`cid`* query parameter, you would enter the following in the *`doPlugins()`* function in your [!DNL AppMeasurement] for JavaScript code:

`s.campaign=s.getQueryParam('cid')`

In this example, if the user arrived at a landing page on your site where the URL was [!DNL https://www.yoursite.com/index.html?cid=123456], then *`s.campaign`* would receive a value of *123456*. Isso pode ser visto usando o Depurador [!DNL DigitalPulse], que deve mostrar *v0=123456* como parte da solicitação de imagem.

>[!NOTE]
>
>The parameter *`cid`* and others are used here as examples. É possível substituí-los por qualquer parâmetro da string de consulta que existe no site.

O plug-in *`getQueryParam`* tem dois argumentos adicionais (opções) que podem ser usados para capturar dados nas variáveis do Analytics:

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

Se *p* é uma lista de parâmetros da string de consulta e mais de um parâmetro da string de consulta for encontrado no URL, todos os valores são retornados em uma lista separada pelo delimitador, *d*, que pode ser um único caractere ou uma string, como " : " (espaço-dois-pontos-espaço). Se *d* for omitido, então nenhuma delimitador será usado entre os valores. Se um parâmetro de string de consulta deve ter prioridade sobre outro, quando ambos forem encontrados, use uma instrução *if* como mostrado abaixo.

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

Na versão *`getQueryParam`* v2.0, o plug-in aceita um terceiro argumento opcional, *u*, que permite especificar a URL da qual você deseja extrair parâmetros de string de consulta. Por padrão (ou seja, se esse terceiro argumento for omitido ou deixado em branco), o plug-in usa a URL da página. Por exemplo, se você deseja extrair uma string de consulta do referenciador, é possível usar o seguinte código:

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

O sinalizador "f" deve ser usado nesse terceiro argumento com quadros, quando o parâmetro da string de consulta necessária é encontrado na barra de endereços, em vez do URL do quadro atual:

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

Quando você usar quadros e o parâmetro *f*, é recomendável usar o plug-in *`getValOnce`* para impedir que o código de rastreamento da campanha seja enviado com cada exibição de página.

>[!NOTE]
>
>As instruções a seguir exigem que você altere o código de coleta de dados do site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

**Código do plug-in**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 None
```

