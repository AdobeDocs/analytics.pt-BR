---
description: Os plug-ins do AppMeasurement para JavaScript são programas ou funções que executam várias funções avançadas.
keywords: Analytics Implementation
subtopic: Plug-ins
title: Usar plug-ins de implementação
topic: Developer and implementation
uuid: 7ffcfe89-b7e2-45e4-b771-942d5ae07c39
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# Usar plug-ins de implementação

Plug-ins são trechos de código que executam várias funções avançadas para ajudar na implementação do Analytics.

Esses plug-ins estendem a capacidade de seu arquivo JavaScript para fornecer a você mais funcionalidade do que a disponível com a implementação básica. A Adobe oferece diversos outros plug-ins como parte das soluções avançadas. Entre em contato com seu gerente de conta se você quiser capturar dados usando o JavaScript, mas se não tiver certeza sobre como proceder.

JavaScript plug-ins are usually called by the doPlugins function, which is executed when the `t` method is called in the Code to Paste.

Consequentemente, se você definir uma variável na função *`doPlugins`*, é possível substituir uma variável definida na página HTML. A única vez que a função*`doPlugins`* não é chamada é quando a variável [!UICONTROL usePlugins] é definida como &#39;false&#39;.

## Exemplo de código {#section_6940FD16F2E94753A1C39694D0CF5FBA}

O exemplo de código abaixo refere-se à aparência da função *`doPlugins`*no arquivo JavaScript:

AppMeasurement para JavaScript:

```js
/* Plugin Config */
s.usePlugins=true
s.doPlugins=function(s) {
 /* Add calls to plug-ins here */
}
```

Código H:

```js
/* Plugin Config */
s.usePlugins=true
function s_doPlugins(s) {
 /* Add calls to plug-ins here */
}
s.doPlugins=s_doPlugins
```

> [!NOTE] O código H e as versões anteriores usam uma sintaxe diferente para o suporte de alguns navegadores muito antigos (como IE 4 e 5).

## Renomear a função doPlugins {#section_70B7D58E057B48058E25907AB3726725}

Normalmente, a função *`doPlugins`*é chamada de*`s_doPlugins`*. Em determinadas circunstâncias (geralmente quando mais de uma versão do código pode aparecer em uma única página), o nome da função *`doPlugins`*pode ser alterado. Se for necessário renomear a função padrão*`doPlugins`* para evitar conflitos, atribua o nome de função correto a *`doPlugins`*, como mostrado no exemplo abaixo.

```js
/* Plugin Config */
s_mc.usePlugins=true
function s_mc_doPlugins(s_mc) {
 /* Add calls to plug-ins here */
}
s_mc.doPlugins=s_mc_doPlugins
```

## Utilizando doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

A função *`doPlugins`*fornece uma maneira fácil de conceder valores padrão a variáveis ou pegar valores dos[!UICONTROL parâmetros da sequência de consulta]em qualquer página do site. Muitas vezes, usar*`doPlugins`* é muito mais fácil do que preencher os valores na página HTML, porque apenas um arquivo deve ser atualizado. Tenha em mente que as alterações no arquivo JavaScript nem sempre são imediatas. Os visitantes de retorno para o site normalmente usam versões em cache do arquivo JavaScript. Ou seja, as atualização no arquivo podem não ter sido aplicadas a todos os visitantes por até um mês depois que a alteração é efetuada.

O exemplo a seguir mostra como a função  *`doPlugins`*pode ser usada para definir um valor padrão para uma variável e obter um valor na string de consulta.

```js
/* Plugin Config */
s.usePlugins=true
s.doPlugins=function(s) {
 /* Add calls to plug-ins here */
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
/* You may insert any plug-ins you wish to use here.                 */
/*
 * Plugin: getQueryParam 1.3 - Return query string parameter values
 */
s.getQueryParam=new Function("qp","d",""
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l"
//
// ... more code below ...
//
```

