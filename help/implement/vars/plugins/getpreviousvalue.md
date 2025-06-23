---
title: getPreviousValue
description: Obtenha o último valor transmitido a uma variável.
feature: Appmeasurement Implementation
exl-id: 235c504b-ba97-4399-a07b-b0bfc764f1ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 77%

---

# Plug-in da Adobe: getPreviousValue

{{plug-in}}

O plug-in `getPreviousValue` permite que você defina uma variável como um valor definido em uma ocorrência anterior. Esse plug-in não é necessário se sua implementação já contiver todos os valores desejados na ocorrência atual.

## Instale o plug-in usando a extensão Web SDK

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Web SDK.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Marcas]** à esquerda e clique na propriedade de marca desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda e na guia **[!UICONTROL Catálogo]**
1. Localize e instale a extensão **[!UICONTROL Plug-ins Comuns do Web SDK]**.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda e, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: Plug-ins comuns do Web SDK
   * Elemento de Dados: `getPreviousValue`
1. Defina os parâmetros desejados à direita.
1. Salve e publique as alterações no elemento de dados.

## Instale o plug-in de implementação manual do Web SDK

Este plug-in ainda não é compatível com uma implementação manual do Web SDK.

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
   * Tipo de ação: inicializar getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v3.0 */
function getPreviousValue(v,c){var k=v,d=c;if("-v"===k)return{plugin:"getPreviousValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getPreviousValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};var l;d=d||"s_gpv";a=new Date;a.setTime(a.getTime()+18E5);window.cookieRead(d)&&(l=window.cookieRead(d));k?window.cookieWrite(d,k,a):window.cookieWrite(d,l,a);return l};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getPreviousValue` usa os seguintes argumentos:

* **`v`** (string, obrigatório): a variável que tem o valor que você deseja transmitir para a próxima solicitação de imagem. Uma variável comumente usada para recuperar o valor da página anterior é `s.pageName`.
* **`c`** (string, opcional): o nome do cookie que armazena o valor.  Se esse argumento não estiver definido, ele assumirá `"s_gpv"` como padrão.

Quando essa função é chamada, ela retorna o valor da string contido no cookie. Em seguida, o plug-in redefine a expiração do cookie e atribui a ele o valor de variável no argumento `v`. O cookie expira após 30 minutos de inatividade.

## Exemplos

```js
// 1. Sets prop7 to the cookie value contained in gpv_Page
// 2. Resets the gpv_Page cookie value to the page variable
// 3. If the page variable is not set, reset the gpv_Page cookie expiration
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if event1 is in the events variable.
if(inList(s.events,"event1")) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets prop7 to the cookie value contained in gpv_Page, but only if the page variable is currently set on the page
if(s.pageName) s.prop7 = getPreviousValue(s.pageName,"gpv_Page");

// Sets eVar10 equal to the cookie value contained in s_gpv, then sets the s_gpv cookie to the current value of eVar1.
s.eVar10 = getPreviousValue(s.eVar1);
```

## Peculiaridades improváveis

Se a variável associada ao argumento `v` estiver definida com um novo valor e o plug-in `getPreviousValue` for executado, MAS uma chamada de servidor do Analytics NÃO for enviada ao mesmo tempo, o novo valor do argumento `v` ainda será considerado como o “valor anterior” na próxima vez que o plug-in for executado.
Por exemplo, suponha que o código a seguir seja executado na primeira página da visita:

```js
s.pageName = "Home";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Esse código produz uma chamada de servidor, em que `pageName` é “Início” e prop7 não está definido.  No entanto, a chamada para `getPreviousValue` armazena o valor do `pageName` no cookie `gpv_Page`. Suponha que, logo em seguida, na mesma página, o seguinte código seja executado:

```js
s.pageName = "New value";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
```

Como a função `t()` não é executada nesse bloco de código, outra solicitação de imagem não será enviada.  No entanto, dessa vez, quando o código da função `getPreviousValue` é executado, `prop7` é definido como o valor anterior do `pageName` (“Início”) e, em seguida, armazena o novo valor do `pageName` (“Novo valor”) no cookie `gpv_Page`. Agora, suponha que o visitante navegue para uma página diferente e o seguinte código seja executado nessa página:

```js
s.pageName = "Page 2";
s.prop7 = getPreviousValue(s.pageName,"gpv_Page");
s.t();
```

Quando a função `t()` é executada, ela cria uma solicitação de imagem onde `pageName` é “Página 2” e `prop7` é o “Novo valor”, que era o valor do `pageName` quando a última chamada para `getPreviousValue` ocorreu. O valor `prop7` de `"Home"` nunca esteve contido em uma solicitação de imagem, mesmo que “Início” fosse o primeiro valor passado para `pageName`.

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### v2.0 (7 de outubro de 2019)

* Versão pontual (reescrita completa da lógica).
