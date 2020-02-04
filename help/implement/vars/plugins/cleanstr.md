---
title: cleanStr
description: Remova ou substitua Todos os caracteres desnecessários de uma string.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe:cleanStr

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `cleanStr` plug-in remove ou substitui todos os caracteres desnecessários de uma string, incluindo caracteres de tag HTML, espaços em branco extras, guias e retornos de nova linha/carro. Também substitui aspas simples esquerda/direita (`‘` e `’`) aspas simples retas (`'`). A Adobe recomenda usar esse plug-in se você deseja remover caracteres desnecessários de valores variáveis e o recurso &quot;Texto limpo&quot; no Launch não atende às suas necessidades de implementação. Este plug-in não é necessário se os dados coletados não contiverem caracteres desnecessários ou se o recurso &#39;Limpar texto&#39; no Launch for suficiente.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar cleanStr
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código] personalizado, que revela o botão [!UICONTROL Abrir editor] .
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando `s_gi`). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `cleanStr` método usa os seguintes argumentos:

* **`str`**(obrigatório, string): O valor que você deseja limpar a codificação HTML, espaço em branco extra, guias ou outros caracteres desnecessários.

O método retorna o valor do `str` argumento com todos os caracteres desnecessários removidos.

## Exemplos

### Exemplo nº 1

Considere o seguinte (em que os pontos representam espaços e as setas representam caracteres de tabulação)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Quando você executa o seguinte código...

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 será definida como &quot;this is a messystring&quot; (com todos os espaços extras e todos os caracteres de tabulação removidos)

### Exemplo nº 2

Se o status...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...e o código a seguir é executado...

```js
cleanStr(s.eVar1)
```

...o valor final de s.eVar1 ainda será:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Executar o plug-in sozinho (sem atribuir o valor de retorno a uma variável) não &quot;redefine&quot; a variável transmitida pelo argumento str.

## Histórico da versão

### 1.0 (15 de abril de 2018)

* Versão inicial.
