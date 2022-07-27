---
title: p_fo (uma vez na página)
description: Garanta que determinadas rotinas sejam acionadas apenas uma vez por página.
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 97%

---

# Plug-in da Adobe: p_fo (uma vez na página)

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `p_fo` é um utilitário que verifica a existência de um objeto JavaScript específico. Se o objeto não existir, o plug-in criará o objeto e retornará `true`. Se o objeto JavaScript já existir na página, ele retornará `false`. Esse plug-in é útil para executar um código exatamente uma vez em uma página. Vários outros plug-ins dependem desse código para funcionar. Esse plug-in é desnecessário se você não estiver preocupado com quantas vezes o código é executado em uma página ou se não usar plug-ins dependentes.

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
    * Action Type: Initialize p_fo
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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `p_fo` usa os seguintes argumentos:

* **on** (obrigatório, string): o nome do objeto JavaScript que o plug-in cria se o objeto ainda não existir na página.

Se o objeto ainda não existir, essa função retornará `true` e criará o objeto. Se o objeto já existir, essa função retornará `false`.

## Exemplos de chamadas

### Exemplo #1

O código a seguir verificará a existência do objeto &quot;myobject&quot; na página.  Se o objeto &quot;myobject&quot; não existir, o código criará o objeto &quot;myobject&quot; e retornará o valor true.  Como resultado, o código dentro da declaração condicional (ou seja, Console.log(&#39;hello&#39;);) será executado.

Por outro lado, se o objeto &quot;myobject&quot; já existir quando a chamada p_fo ocorrer, a função p_fo retornará o valor false e, portanto, a declaração condicional será considerada falsa.  Nesse caso, o código dentro da declaração condicional não será executado.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTA:** sempre que um novo objeto de página/DOM for carregado (ou sempre que a página atual for recarregada), o objeto especificado no argumento “on” não existirá mais e, portanto, o plug-in “p_fo” retornará “true” na primeira vez que for executado depois que a página terminar de ser carregada.

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.0

* Versão pontual (recompilada, menor tamanho de código).
* Alteração do tipo de valor de retorno de número inteiro para booleano.

### 1.0

* Versão inicial.
