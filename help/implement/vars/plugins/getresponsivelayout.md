---
title: getResponsiveLayout
description: Determine qual layout de um site está sendo exibido no momento.
translation-type: tm+mt
source-git-commit: 16d2bc13a71dfe0b9106dea03da5eaa9da4d704c
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 98%

---


# Plug-in da Adobe: getResponsiveLayout

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getResponsiveLayout` permite que você rastreie a versão do seu site com design responsivo que um visitante está visualizando no momento. A Adobe recomenda usar esse plug-in se o seu site usar um design responsivo e se você quiser rastrear a versão do site exibida por um visitante. Esse plug-in é desnecessário se o site não usar design responsivo.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getResponsiveLayout
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
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

O método `getResponsiveLayout` aceita os seguintes argumentos:

* **`ppw`** (obrigatório, número inteiro): a largura máxima de pixels que uma janela do navegador pode ter antes que a página alterne do layout no modo retrato de telefone para o layout no modo paisagem de telefone
* **`plw`** (obrigatório, número inteiro): a largura máxima de pixels que uma janela de navegador pode ter antes que a página alterne de um layout no modo paisagem para um layout de tablet
* **`tw`** (obrigatório, booleano): a largura máxima de pixels que uma janela de navegador pode ter antes que a página alterne de um layout de tablet para um layout de desktop

Chamar esse método retorna uma string que contém duas partes. A primeira parte usa um dos seguintes valores a depender da largura do navegador e dos argumentos acima:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (para sites que não têm layouts no modo retrato e paisagem)
* `"tablet layout"`
* `"desktop layout"`

A segunda parte da string retornada é a largura e a altura do navegador. Por exemplo, `"desktop layout:1243x700"`.

## Exemplos de chamadas

### Exemplo #1

Se...

* Seu site muda do modo retrato do telefone para o modo paisagem do telefone quando a largura do navegador é superior a 500 pixels
* Seu site muda do modo paisagem de telefones para o modo tablet quando a largura do navegador é superior a 700 pixels
* Seu site muda do modo tablet para o modo desktop quando a largura do navegador é maior que 1000 pixels

... o código a seguir definirá a eVar10 como o layout de design responsivo atual experimentado pelo visitante, além de definir a largura e as dimensões do navegador

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Exemplo #2

Se...

* Seu site tem apenas um modo telefone, um modo tablet e um modo desktop
* Seu site muda do modo telefone para o modo tablet quando a largura do navegador é superior a 500 pixels
* Seu site muda do modo tablet para o modo desktop quando a largura do navegador é maior que 1.100 pixels

... o código a seguir definirá a eVar10 como o layout de design responsivo atual experimentado pelo visitante, além de definir a largura e as dimensões do navegador

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Histórico da versão

### 1.1 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (2 de maio de 2018)

* Versão inicial.
