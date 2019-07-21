---
description: Normalmente, os plug-ins JavaScript são chamados pela função doPlugins, que é executada quando a função t() é chamada em Código para colar.
keywords: Implementação do Analytics
seo-description: Normalmente, os plug-ins JavaScript são chamados pela função doPlugins, que é executada quando a função t() é chamada em Código para colar.
seo-title: Chamada de plug-ins com a função doplugins
solution: Analytics
subtopic: Plug-ins
title: Chamada de plug-ins com a função doplugins
topic: Desenvolvedor e implementação
uuid: 95 dd 01 de -8136-4 ec 9-aac 9-4 a 3 d 5371 b 839
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Chamada de plug-ins com a função doplugins

Normalmente, os plug-ins JavaScript são chamados pela função doPlugins, que é executada quando a função t() é chamada em Código para colar.

Consequently, if you set a variable in the *`doPlugins`* function, you can overwrite a variable you set on the HTML page. The only time the *`doPlugins`* function is not called is when the [!UICONTROL usePlugins] variable is set to 'false.'

## Exemplo de código {#section_6940FD16F2E94753A1C39694D0CF5FBA}

The code example below is what the *`doPlugins`* function looks like in your JavaScript file:

AppMeasurement para JavaScript:

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

Código H:

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

>[!NOTE]
>
>O código H e as versões anteriores usam uma sintaxe diferente para suportar alguns navegadores muito antigos (como IE 4 e 5).

## Renaming the doPlugins Function {#section_70B7D58E057B48058E25907AB3726725}

The *`doPlugins`* function is typically called *`s_doPlugins`*. In certain circumstances, (usually when more than one version of code may appear on a single page) the *`doPlugins`* function name may be changed. If the standard *`doPlugins`* function needs to be renamed to avoid conflicts, ensure that *`doPlugins`* is assigned the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## Utilizando doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

The *`doPlugins`* function provides an easy way to give default values to variables or to take values from [!UICONTROL query string parameters] on any page of the site. Using *`doPlugins`* is often easier than populating the values in the HTML page because only one file must be updated. Tenha em mente que as alterações no arquivo JavaScript nem sempre são imediatas. Os visitantes de retorno para o site normalmente usam versões em cache do arquivo JavaScript. Ou seja, as atualização no arquivo podem não ter sido aplicadas a todos os visitantes por até um mês depois que a alteração é efetuada.

O exemplo a seguir mostra como a função *`doPlugins`* pode ser usada para definir um valor padrão para uma variável e obter um valor na string de consulta.

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 
```

## Plug-ins instalados {#section_C5494347D85940A78670032199787CD0}

Para descobrir se um plug-in foi incluído no seu arquivo JavaScript e está pronto para uso, consulte a [!UICONTROL Seção de plug-ins] do arquivo JavaScript. O exemplo a seguir mostra a função [!UICONTROL getQueryParam].

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

