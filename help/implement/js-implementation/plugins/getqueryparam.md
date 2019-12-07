---
description: Retorna o valor de um parâmetro especificado da string de consulta, se for encontrado no URL da página atual. Como os dados importantes (tais como códigos de rastreamento de campanha, palavras-chave de pesquisa interna etc.) estão disponíveis na sequência de caracteres de consulta em uma página, o getQueryParam ajuda a capturar os dados nas variáveis do Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getQueryParam
topic: Developer and implementation
uuid: ba202756-c728-4ebc-8fd9-5bc29a9f673b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getQueryParam

Retorna o valor de um parâmetro especificado da string de consulta, se for encontrado no URL da página atual. Como os dados importantes (tais como códigos de rastreamento de campanha, palavras-chave de pesquisa interna etc.) estão disponíveis na sequência de caracteres de consulta em uma página, o getQueryParam ajuda a capturar os dados nas variáveis do Analytics.

>[!IMPORTANT]
>
>Este plugin é usado somente pelo código H. O [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) oferece essa funcionalidade nativamente ao usar o [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md).

Depois de instalado no [!DNL AppMeasurement] para código JavaScript, o plug-in é configurado ao selecionar uma variável do [!DNL Analytics] para preencher, usando os dados encontrados na sequência de consulta e especificando os valores da sequência de consulta que devem ser capturados. O plug-in detecta a string de consulta especificada, se houver, e preenche a variável escolhida com seu valor. Se nenhum parâmetro de string de consulta for encontrado com esse valor, uma string vazia é retornada. Se um parâmetro da sequência de consulte existe, mas não tem um valor (como param1 em `?param1&param2=value`), a palavra *`true`* é retornada.

> [!NOTE] O código base do plug-in deve ser instalado no [!DNL AppMeasurement] para código JavaScript, antes que os exemplos abaixo funcionem.

Se você quiser usar *`s.campaign`* para capturar os códigos de rastreamento de campanha disponíveis como valores do parâmetro de consulta *`cid`*, insira o seguinte na função *`doPlugins()`* em seu [!DNL AppMeasurement] para o código JavaScript:

`s.campaign=s.getQueryParam('cid')`

Nesse exemplo, se o usuário chegou a uma página de aterrissagem no site, onde o URL era [!DNL https://www.yoursite.com/index.html?cid=123456], então *`s.campaign`* receberia um valor de *123456*. Isso pode ser visto usando o [!DNL DigitalPulse] [!UICONTROL Depurador ], que deve mostrar *v0=123456* como parte da solicitação de imagem.

> [!NOTE]O parâmetro *`cid`* e outros são usados aqui como exemplos. É possível substituí-los por qualquer parâmetro da string de consulta que existe no site.

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

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

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

