---
description: Normalmente, os plug-ins JavaScript são chamados pela função doPlugins, que é executada quando a função t() é chamada em Código para colar.
keywords: Analytics Implementation
subtopic: Plug-ins
title: Função doPlugins
topic: Developer and implementation
uuid: 367d5550-f8e2-477d-8681-18ae9665d699
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Função doPlugins

Normalmente, os plug-ins JavaScript são chamados pela função doPlugins, que é executada quando a função t() é chamada em Código para colar.

Consequentemente, se você definir uma variável na função `doPlugins`, é possível substituir uma variável definida na página HTML. A única vez que a função `doPlugins` não é chamada é quando a variável *`usePlugins`* é definida como `false`.

**Exemplo de código**

Normalmente, a função `doPlugins` é chamada de `s_doPlugins`. No entanto, em determinadas circunstâncias (normalmente quando mais de uma versão do código do [!DNL Analytics] pode aparecer em uma única página), é possível alterar o nome da função `doPlugins`. Se for necessário renomear a função padrão `doPlugins` para evitar conflitos, atribua o nome de função correto a `doPlugins`, como mostrado no exemplo abaixo.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**Utilizando doPlugins**

Essa função fornece uma maneira fácil de conceder valores padrão a variáveis ou pegar valores dos parâmetros da sequência de caracteres de consulta em qualquer página do site. É mais fácil utilizar `doPlugins` do que preencher os valores na página HTML porque apenas um arquivo deve ser atualizado. As alterações no arquivo JavaScript nem sempre são imediatas. Os visitantes de retorno para o site normalmente usam versões em cache do arquivo JavaScript. Ou seja, as atualização no arquivo podem não ter sido aplicadas a todos os visitantes por até um mês depois que a alteração é efetuada.

Os seguintes exemplos mostram como é possível usar a função `doPlugins` para definir um valor padrão para uma variável e obter um valor da sequência de caracteres de consulta.

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**Plug-ins instalados**

Para descobrir se um plug-in foi incluído no seu arquivo JavaScript e está pronto para uso, consulte a [!UICONTROL Seção de plug-ins] do arquivo JavaScript. O seguinte exemplo mostra como a função `getQueryParam` se parece na [!UICONTROL Seção de plug-ins].

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ...
// 
```

