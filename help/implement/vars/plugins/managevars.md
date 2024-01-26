---
title: manageVars
description: Altere os valores de mais de uma variável do Analytics de cada vez.
feature: Variables
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 88%

---

# Plug-in da Adobe: manageVars

{{plug-in}}

O plug-in `manageVars` permite manipular os valores de várias variáveis do Analytics de uma só vez. Você também pode definir valores como minúsculas ou remover caracteres desnecessários de múltiplos valores variáveis ao mesmo tempo. A Adobe recomenda usar esse plug-in se você desejar limpar o valor de múltiplas variáveis de uma só vez.

## Instale o plug-in usando a extensão SDK da Web ou SDK da Web.

Este plug-in ainda não é compatível com o SDK da Web.

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
   * Tipo de ação: inicializar manageVars
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
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

A função `manageVars` usa os seguintes argumentos:

* **`cb`** (obrigatório, string): o nome de uma função de retorno de chamada que o plug-in usa para manipular as variáveis do Analytics. Você pode usar uma função da Adobe como `cleanStr` ou sua própria função personalizada.
* **`l`** (opcional, string): uma lista delimitada por vírgulas de variáveis do Analytics que você deseja manipular. O padrão é ter TODAS as variáveis do Adobe Analytics quando não definidas, o que inclui:
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * Todas as props
   * Todas as eVars
   * Todas as variáveis de hierarquia
   * Todas as variáveis de lista
   * Todas as variáveis de dados de contexto
* **`Il`** (opcional, booleano): defina como `false` se você deseja *excluir* a lista de variáveis declaradas no argumento `l` em vez de incluí-las. O padrão é `true`.

Chamar essa função não retorna nada. Em vez disso, altera os valores das variáveis do Analytics com base na função de retorno de chamada desejada.

## Exemplos de chamadas

### Exemplo #1

O código a seguir...

```js
manageVars("lowerCaseVars");
```

... altera os valores de todas as variáveis descritas acima para versões em minúsculas.  A única exceção a isso é a variável de eventos, pois alguns dos eventos (por exemplo, scAdd, scCheckout etc.) fazem distinção entre maiúsculas e minúsculas e não devem ser convertidos para minúsculas

### Exemplo #2

O código a seguir...

```js
manageVars("lowerCaseVars", "events", false);
```

... produz essencialmente o mesmo resultado que o primeiro exemplo, já que a variável de eventos não foi convertida em minúsculas por padrão.

### Exemplo #3

O código a seguir...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

... alterará (por exemplo, minúsculas) somente os valores de eVar1, eVar2, eVar3 e list2.

### Exemplo #4

O código a seguir...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

... alterará (por exemplo, minúsculas) os valores de todas as variáveis descritas acima, EXCETO da eVar1, eVar2, eVar3 e list2.

### Exemplo #5

O código a seguir...

```js
manageVars("cleanStr");
```

... altera os valores de todas as variáveis descritas acima, incluindo as variáveis de eventos.  Especificamente, a função de retorno de chamada cleanStr faz o seguinte com o valor de cada variável:

* Remove a codificação HTML
* Remove espaços em branco encontrados no início e no fim do valor
* Substitui aspas simples esquerda/direita por aspas simples retas (`'`)
* Substitui caracteres de tabulação e caracteres de nova linha por espaços
* Substitui todos os espaços duplos (ou triplos etc.) por espaços únicos

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.1 (14 de janeiro de 2019)

* Correção de erros para navegadores Internet Explorer 11.
* Alterações na `s.cleanStr`, que agora usa a função regular `cleanStr`.

### 2.0 (7 de maio de 2018)

* Lançamento pontual (incluindo reanálise/reescrita completa do plug-in)
* Função de retorno de chamada `cleanStr` adicionada
