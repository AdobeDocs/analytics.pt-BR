---
title: addProductEvar
description: Adiciona eVars de merchandising à variável products.
feature: Variables
exl-id: 6be94a15-78c9-4cbc-8b33-4a16f1b73b96
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 97%

---

# Plug-in da Adobe: addProductEvar

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `addProductEvar` permite adicionar facilmente uma eVar de merchandising do Adobe Analytics que usa a sintaxe do produto na variável products sem se preocupar se o conteúdo já existente da variável products será alterado/movido/excluído. A Adobe recomenda usar esse plug-in se você quiser adicionar com facilidade eVars de merchandising com sintaxe de produto à variável [`products`](../page-vars/products.md). Você não precisa usar o plug-in `addProductEvar` se não usar eVars de merchandising com sintaxe de produto.

>[!NOTE]
>
>Esse plug-in não substitui eVars que já existem em uma entrada de produto. Ele anexa apenas valores que você define usando o plug-in. Tenha cuidado ao anexar eVars que já existem para esse produto.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize addProductEvar
1. Save and publish the changes to the rule.-->

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: addProductEvar v2.0 */
function addProductEvar(en,ev,ap){var e=en,f=ev,d=ap;if("-v"===e)return{plugin:"addProductEvar",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}if("undefined"!==typeof b&&(b.contextData.addProductEvar="2.0","string"===typeof e&&"string"===typeof f&&""!==f))if(d=d||!1,b.products){c=b.products.split(",");var g=c.length;d=d?0:g-1;for(var a;d<g;d++)a=c[d].split(";"),a[5]&&-1<a[5].toLowerCase().indexOf("evar")?a[5]=a[5]+"|"+e+"="+f:a[5]?a[5]=e+"="+f:a[5]||(a[4]||(a[4]=""),a[3]||(a[3]=""),a[2]||(a[2]=""),a[1]||(a[1]=""),a[5]=e+"="+f),c[d]=a.join(";");b.products=c.join(",")}else b.products=";;;;;"+e+"="+f};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O plug-in `addProductEvar` aceita os seguintes argumentos:

* **`en`** (obrigatório, string): eVar usada para adicionar à última entrada atualmente contida na variável products. Se a variável products estiver em branco, o plug-in criará uma entrada de produto &quot;em branco&quot; com o valor da eVar anexado ao final da entrada.
* **`ev`** (obrigatório, string): o valor atribuído à eVar.
* **`ap`** (opcional, booleano): se a variável products contiver mais de uma entrada de produto no momento, um valor true (ou 1) fará a eVar ser adicionada a **todas** as entradas de produto.  O padrão é false (ou 0), o que faz a eVar ser adicionada somente à **última** entrada contida na variável products.

O plug-in `addProductEvar` não retorna nada. Em vez disso, ele adiciona a eVar (e o valor da eVar) especificada nos argumentos `en` e `ev` à variável `products`.

## Exemplos

```js
// Set a merchandising eVar to blue on the last product. The output for the products variable is ";product1;3;300,;product2;2;122,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvar("eVar1", "blue");

// Set a merchandising eVar to blue on all products. The output for the products variable is ";product1;3;300;;eVar1=blue,;product2;2;122;;eVar1=blue,;product3;1;25;;eVar1=blue"
s.products=";product1;3;300,;product2;2;122,;product3;1;25";
addProductEvar("eVar1", "blue", true);

// Set multiple merchandising eVars to the last product in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
addProductEvar("eVar23", "medium");
addProductEvar("eVar24", "women");
addProductEvar("eVar1", "red");

// Set multiple merchandising eVars to all products in the string. The output for the products variable is ";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue|eVar23=medium|eVar24=women|eVar1=red,;product2;2;122;;eVar23=medium|eVar24=women|eVar1=red,;product3;1;25;;eVar23=medium|eVar24=women|eVar1=red"
s.products=";product1;3;300;event2=10;eVar23=large|eVar24=men|eVar1=blue,;product2;2;122,;product3;1;25";
addProductEvar("eVar23", "medium", true);
addProductEvar("eVar24", "women", true);
addProductEvar("eVar1", "red", true);

// If the products variable is not set, the plug-in creates an empty product string correctly delimited to the merchandising eVar. The output for the products variable is ";;;;;eVar1=blue"
addProductEvar("eVar1", "blue");
```

## Histórico da versão

### 2.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (7 de outubro, 2019)

* Versão inicial.
