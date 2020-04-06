---
title: cleanStr
description: Remova ou substitua todos os caracteres desnecessários de uma string.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: cleanStr

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `cleanStr` remove ou substitui todos os caracteres desnecessários de uma string, incluindo caracteres de tags HTML, espaços em branco extras, tabulações e retornos de caracteres de nova linha. It also replaces left/right single quotes (`‘` and `’`) with straight single quotes (`'`). A Adobe recomenda usar esse plug-in se você deseja remover caracteres desnecessários de valores variáveis e se o recurso &quot;Texto limpo&quot; no Launch não atende às suas necessidades de implementação. Esse plug-in não é necessário se os dados coletados não contiverem caracteres desnecessários ou se o recurso “Limpar texto” no Launch for suficiente.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar cleanStr
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
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

### 1.0 (15 de abril de 2018)

* Versão inicial.
