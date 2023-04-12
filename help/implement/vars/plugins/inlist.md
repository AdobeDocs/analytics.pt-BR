---
title: inList
description: Verifique se um valor está contido em outro valor delimitado por caracteres.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 87%

---

# Plug-in da Adobe: inList

{{plug-in}}

O plug-in `inList` permite verificar se um valor já existe em uma string delimitada ou em um objeto de matriz JavaScript. Vários outros plug-ins dependem do plug-in `inList` para funcionar. Esse plug-in oferece uma vantagem distinta em relação ao método JavaScript `indexOf()`, no qual não é possível corresponder strings parciais. Por exemplo, se você usou este plug-in para verificar `"event2"`, ele não corresponderá a uma string que contém `"event25"`. Este plug-in não é necessário se você não precisa verificar valores em strings delimitadas ou matrizes, ou se deseja usar sua própria lógica de `indexOf()`.

## Instalar o plug-in usando a extensão Web SDK ou Web SDK

Esse plug-in ainda não é compatível com o uso no SDK da Web.

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
   * Tipo de ação: inicializar inList
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
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `inList` retorna uma operação booleana dependendo de suas entradas. Ela usa os seguintes argumentos:

* **`lv`** (obrigatório, string ou array): uma lista delimitada de valores ou um objeto de matriz JavaScript que passará por pesquisa
* **`vtc`** (obrigatório, string): o valor a ser pesquisado
* **`d`** (opcional, string): o delimitador usado para separar valores individuais no argumento `lv`. O padrão é uma vírgula (`,`) quando um valor não está definido.
* **`cc`** (opcional, booleano): se definido como `true` ou `1`, uma verificação que diferencia maiúsculas de minúsculas é realizada. Se definido como `false` ou omitido, então é feita uma verificação que não diferencia maiúsculas de minúsculas. O padrão é `false`.

Chamar essa função retornará `true` se uma correspondência for encontrada e `false` se uma correspondência não for encontrada.

## Exemplos

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### v2.1 (26 de setembro de 2019)

* Adicionada a opção para que o argumento `cc` não seja booleano. Por exemplo, `1` é um valor válido de verificação de letras maiúsculas e minúsculas.

### v2.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).

### v1.01 (27 de setembro de 2017)

* Código otimizado para reduzir o tamanho

### v1.0 (2009)

* Versão inicial.
