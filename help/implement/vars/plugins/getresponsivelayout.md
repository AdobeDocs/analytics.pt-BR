---
title: getResponsiveLayout
description: Determine qual layout de um site está sendo exibido no momento.
feature: Appmeasurement Implementation
exl-id: 5b192d02-fc3c-4b82-acb4-42902202ab5f
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 86%

---

# Plug-in da Adobe: getResponsiveLayout

{{plug-in}}

O plug-in `getResponsiveLayout` permite que você rastreie a versão do seu site com design responsivo que um visitante está visualizando no momento. A Adobe recomenda usar esse plug-in se o seu site usar um design responsivo e se você quiser rastrear a versão do site exibida por um visitante. Esse plug-in é desnecessário se o site não usar design responsivo.

## Instale o plug-in usando a extensão Web SDK ou Web SDK

Este plug-in ainda não é compatível com o Web SDK.

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
   * Tipo de ação: inicializar getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.1 (Requires AppMeasurement) */
var getResponsiveLayout=function(ppw,plw,tw){var c=ppw,b=plw,e=tw;if("-v"===c)return{plugin:"getResponsiveLayout",version:"1.1"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getResponsiveLayout="1.1");if(!(isNaN(c)||isNaN(b)||isNaN(e)||b<c||e<b))return a=window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,(c<b&&a<=b?a<=c?"phone portrait layout":"phone landscape layout":a<=b?"phone layout":a<=e?"tablet layout":"desktop layout")+":"+a+"x"+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `getResponsiveLayout` usa os seguintes argumentos:

* **`ppw`** (obrigatório, número inteiro): a largura máxima de pixels que uma janela do navegador pode ter antes que a página alterne do layout no modo retrato de telefone para o layout no modo paisagem de telefone
* **`plw`** (obrigatório, número inteiro): a largura máxima de pixels que uma janela de navegador pode ter antes que a página alterne de um layout no modo paisagem para um layout de tablet
* **`tw`** (obrigatório, inteiro): a largura máxima em pixels que uma janela de navegador pode ter antes que a página mude de um layout de tablet para um layout de desktop

Chamar essa função retorna uma string que contém duas partes delimitadas por dois pontos (`:`). Dependendo da largura do navegador e dos argumentos acima, a primeira parte da string conterá um dos seguintes valores:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (para sites que não têm layouts no modo retrato e paisagem)
* `"tablet layout"`
* `"desktop layout"`

A segunda parte da string retornada é a largura e a altura do navegador. Por exemplo, `"desktop layout:1243x700"`.

## Exemplos

```js
// A visitor accesses your site on their laptop. The browser window is maximized.
// * Your site switches from phone portrait mode to phone landscape mode when the browser width is greater than 500 pixels
// * Your site switches from phone landscape mode to tablet mode when the browser width is greater than 700 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1000 pixels
// Sets eVar10 to "desktop layout:1920x937".
s.eVar10 = getResponsiveLayout(500, 700, 1000);

// A visitor accesses your site on their phone.
// * Your site has only a phone mode, a tablet mode, and a desktop mode
// * Your site switches from phone mode to tablet mode when the browser width is greater than 800 pixels
// * Your site switches from tablet mode to desktop mode when the browser width is greater than 1,100 pixels
// Sets eVar10 to "phone portrait layout:720x1280"
s.eVar10 = getResponsiveLayout(800, 800, 1100);
```

## Histórico da versão

### 1.1 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (2 de maio de 2018)

* Versão inicial.
