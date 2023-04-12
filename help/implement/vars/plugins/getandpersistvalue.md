---
title: getAndPersistValue
description: Armazene um valor que pode ser recuperado posteriormente a qualquer momento.
feature: Variables
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 70%

---

# Plug-in da Adobe: getAndPersistValue

{{plug-in}}

O plug-in `getAndPersistValue` permite armazenar um valor em um cookie que pode ser recuperado posteriormente durante uma visita. Ela desempenha um papel semelhante ao do [!UICONTROL Duração do armazenamento] na extensão Adobe Analytics na Coleta de dados do Adobe Experience Platform. A Adobe recomenda usar esse plug-in se você quiser manter automaticamente uma variável do Analytics com o mesmo valor em ocorrências subsequentes à definição da variável. Esse plug-in não é necessário se a variável [!UICONTROL Duração do armazenamento] na extensão do Analytics é suficiente. Também não é necessário usar esse plug-in se você não precisar definir e manter variáveis com o mesmo valor em ocorrências subsequentes. A persistência integrada das eVars não requer o uso desse plug-in, pois essas eVars persistem no lado do servidor por ação da Adobe.

## Instalar o plug-in usando a extensão Web SDK

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o SDK da Web.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Tags]** à esquerda, em seguida, clique na propriedade de tag desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda, em seguida, clique no botão **[!UICONTROL Catálogo]** guia
1. Localize e instale o **[!UICONTROL Plug-ins comuns de SDK da Web]** extensão.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: Plug-ins comuns de SDK da Web
   * Elemento de dados: `getAndPersistValue`
1. Defina os parâmetros desejados à direita.
1. Salve e publique as alterações no elemento de dados.

## Instalar o plug-in implementando manualmente o SDK da Web

Este plug-in ainda não é compatível com o uso em uma implementação manual do SDK da Web.

## Instalar o plug-in usando a extensão Adobe Analytics

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
   * Tipo de ação: inicializar getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getAndPersist` usa os seguintes argumentos:

* **`vtp`** (obrigatório): o valor a ser persistido de página em página
* **`cn`** (opcional): o nome do cookie que armazenará o valor. Se este argumento não estiver definido, o cookie é nomeado como `"s_gapv"`
* **`ex`** (opcional): o número de dias antes do cookie expirar. Se esse argumento for `0` ou não estiver definido, o cookie expirará no final da visita (após 30 minutos de inatividade).

Se a variável no argumento `vtp` estiver definida, o plug-in definirá o cookie e retornará o valor do cookie. Se a variável no argumento `vtp` não estiver definida, o plug-in apenas retornará o valor do cookie.

## Exemplos

```js
// Sets eVar21 to "raccoon", and sets the ev21gapv cookie to "raccoon" (which expires in 28 days).
s.eVar21 = "raccoon";
s.eVar21 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Checks the "ev21gapv" cookie for a value and assigns it to eVar21. It does not set a cookie value or reset an existing cookie's expiration since the value is not set on the page.
// If there is a cookie, assigns eVar21 to that value. Otherwise, eVar21 is blank.
s.eVar21 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Checks the "ev21gapv" cookie for a value and assigns it to prop35. It does not set a cookie value or reset an existing cookie's expiration since eVar21 is not set on the page.
s.prop35 = getAndPersistValue(s.eVar21,"ev21gapv",28);

// Sets eVar21 to "panda", and sets the ev21gapv cookie to "panda" (which expires in 14 days). It then sets prop35 to the value contained in the ev21gapv cookie.
// Ultimately both eVar21 and prop35 contain the value "panda".
s.eVar21 = "panda";
s.prop35 = getAndPersistValue(s.eVar21,"ev21gapv",14);

// Sets eVar30 to "shopping", and sets the s_gapv cookie to "shopping" (which expires at the end of the browser session).
s.eVar30 = "shopping";
s.eVar30 = getAndPersistValue(s.eVar30);
```

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.0 (16 de abril de 2018)

* Lançamento pontual (tamanho de código menor)
* Transmitir 0 para o argumento `ex` agora força a expiração após 30 minutos de inatividade em vez de no final da sessão do navegador.

### 1.0 (18 de janeiro de 2016)

* Versão inicial.
