---
title: pt
description: Executa uma função em uma lista de variáveis.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---

# Plug-in da Adobe: pt

{{plug-in}}

O plug-in `pt` executa uma função ou um método em uma lista de variáveis do Analytics. Por exemplo, você pode executar seletivamente a função [`clearVars`](../functions/clearvars.md) em muitas variáveis sem chamar manualmente a função a cada vez. Vários outros plug-ins dependem desse código para serem executados corretamente. Esse plug-in não é necessário se você não precisar executar uma função específica em mais de uma variável do Analytics por vez ou se não estiver usando plug-ins dependentes.

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
    * Action Type: Initialize pt
1. Save and publish the changes to the rule.-->

## Instale o plug-in usando o editor de código personalizado do

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `pt` usa os seguintes argumentos:

* **`l`** (obrigatório, string): uma lista de variáveis para as quais a função contida no argumento `cf` será executada.
* **`de`** (opcional, string): o delimitador que separa a lista de variáveis no argumento `l`. O padrão é uma vírgula (`,`).
* **`cf`** (obrigatório, string): o nome da função de retorno de chamada contida no objeto AppMeasurement a ser chamado para cada uma das variáveis contidas no argumento `l`.
* **`fa`** (opcional, string): se a função no argumento `cf` exigir argumentos adicionais ao ser executada, inclua-os aqui. O padrão é `undefined`.

Chamar essa função retornará um valor se a função de retorno de chamada (no argumento `cf`) retornar um valor.

## Exemplos de chamadas

### Exemplo #1

O código a seguir faz parte do plug-in getQueryParam.  Ela executa a função auxiliar getParameterValue para cada um dos pares de valor-chave contidos na string de consulta do URL (fullQueryString).  Em outro lugar, para extrair cada par de valor-chave, fullQueryString deve ser delimitado e dividido por um caractere “e” comercial (&amp;). O parameterKey se refere ao parâmetro da string de consulta que o plug-in está tentando extrair especificamente da string de consulta.

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

A linha acima é um atalho para executar código que se assemelha ao seguinte:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.01 (24 de setembro de 2019)

* Alterações menores no código para reduzir o tamanho geral.

### 2.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Adicionado suporte para H-code e AppMeasurement.

### 1.0 (23 de setembro de 2013)

* Versão inicial.
