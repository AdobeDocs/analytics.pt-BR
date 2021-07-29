---
title: cleanStr
description: Remova ou substitua todos os caracteres desnecessários de uma string.
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 82%

---

# Plug-in da Adobe: cleanStr

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `cleanStr` remove ou substitui todos os caracteres desnecessários de uma string, incluindo caracteres de tags HTML, espaços em branco extras, tabulações e retornos de caracteres de nova linha. Também substitui aspas simples esquerda/direita (`‘` e `’`) por aspas simples retas (`'`). O Adobe recomenda usar esse plug-in se você quiser remover caracteres desnecessários de valores variáveis e se o recurso &quot;Texto limpo&quot; no Adobe Experience Platform não atender às suas necessidades de implementação. Esse plug-in não é necessário se os dados coletados não contiverem caracteres desnecessários ou se o recurso &quot;Texto limpo&quot; na interface do usuário da coleta de dados for suficiente.

## Instalar o plug-in usando tags no Adobe Experience Platform

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon na [Interface do usuário da coleta de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar cleanStr
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do 

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon na [Interface do usuário da coleta de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `cleanStr` aceita os seguintes argumentos:

* **`str`** (obrigatório, string): o valor que você deseja limpar da codificação HTML, o espaço em branco extra, tabulações ou outros caracteres desnecessários.

O método retorna o valor do argumento `str` com todos os caracteres desnecessários removidos.

## Exemplos

### Exemplo #1

Considere o seguinte (os pontos representam espaços e as setas representam caracteres de tabulação)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Quando você executa o seguinte código...

```js
s.eVar1 = cleanStr(s.eVar1)
```

... eVar1 será definida como &quot;this is a messystring&quot; (com todos os espaços extras e todos os caracteres de tabulação removidos)

### Exemplo #2

Se...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

... e o código a seguir for executado...

```js
cleanStr(s.eVar1)
```

...o valor final de s.eVar1 ainda será:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Executar o plug-in por si só (sem atribuir o valor de retorno a uma variável) não &quot;redefine&quot; a variável transmitida pelo argumento str.

## Histórico da versão

### 2.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 1.0 (15 de abril de 2018)

* Versão inicial.
