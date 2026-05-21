---
title: p_fo (uma vez na página)
description: Garanta que determinadas rotinas sejam acionadas apenas uma vez por página.
feature: Appmeasurement Implementation
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7kJ-oRIsYzFeRnApFYvIigsBMb8QgeBtjCiHt8am7Nk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 742
ht-degree: 77%

---

# Plug-in da Adobe: p_fo (uma vez na página)

{{plug-in}}

O plug-in `p_fo` é um utilitário que verifica a existência de um objeto JavaScript específico. Se o objeto não existir, o plug-in criará o objeto e retornará `true`. Se o objeto JavaScript já existir na página, ele retornará `false`. Esse plug-in é útil para executar um código exatamente uma vez em uma página. Vários outros plug-ins dependem desse código para funcionar. Esse plug-in é desnecessário se você não estiver preocupado com quantas vezes o código é executado em uma página ou se não usar plug-ins dependentes.

## Instale o plug-in usando a extensão Web SDK

O Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência com o Web SDK.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Marcas]** à esquerda e clique na propriedade de marca desejada.
1. Clique em **[!UICONTROL Extensões]** à esquerda e na guia **[!UICONTROL Catálogo]**
1. Localize e instale a extensão **[!UICONTROL Plug-ins Comuns do Web SDK]**.
1. Clique em **[!UICONTROL Elementos de dados]** à esquerda e, em seguida, clique no elemento de dados desejado.
1. Defina o nome do elemento de dados desejado com a seguinte configuração:
   * Extensão: Plug-ins comuns do Web SDK
   * Elemento de Dados: `p_fo`
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
   * Tipo de ação: inicializar p_fo
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
