---
title: pt
description: Executa uma função em uma lista de variáveis.
translation-type: tm+mt
source-git-commit: e2afe854a4141510fe2ecd85aa6df59f6751d0f5

---


# Plug-in da Adobe: pt

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `pt` executa uma função ou um método em uma lista de variáveis do Analytics. Por exemplo, você pode executar seletivamente o método [`clearVars`](../functions/clearvars.md) em muitas variáveis sem chamar manualmente o método de vez em vez. Vários outros plug-ins dependem desse código para serem executados corretamente. Esse plug-in não é necessário se você não precisar executar uma função específica em mais de uma variável do Analytics por vez ou se não estiver usando plug-ins dependentes.

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
   * Tipo de ação: inicializar pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `pt` aceita os seguintes argumentos:

* **`l`** (obrigatório, string): uma lista de variáveis para as quais a função contida no argumento `cf` será executada.
* **`de`** (opcional, string): o delimitador que separa a lista de variáveis no argumento `l`. O padrão é uma vírgula (`,`).
* **`cf`** (obrigatório, string): o nome da função de retorno de chamada contida no objeto AppMeasurement a ser chamado para cada uma das variáveis contidas no argumento `l`.
* **`fa`** (opcional, string): se a função no argumento `cf` exigir argumentos adicionais ao ser executada, inclua-os aqui. O padrão é `undefined`.

Chamar esse método retornará um valor se a função de retorno de chamada (no argumento `cf`) retornar um valor.

## Exemplos de chamadas

### Exemplo #1

O código a seguir faz parte do plug-in getQueryParam.  Ela executa a função auxiliar getParameterValue para cada um dos pares de valor-chave contidos na string de consulta do URL (fullQueryString).  Em outro lugar, para extrair cada par de valor-chave, fullQueryString deve ser delimitado e dividido por um caractere “e” comercial (&amp;). O parameterKey se refere ao parâmetro da string de consulta que o plug-in está tentando extrair especificamente da string de consulta.

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

A linha acima é um atalho para executar código que se assemelha ao seguinte:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Histórico da versão

### 2.01 (24 de setembro de 2019)

* Alterações menores no código para reduzir o tamanho geral.

### 2.0 (17 de abril de 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Adicionado suporte para H-code e AppMeasurement.

### 1.0 (23 de setembro de 2013)

* Versão inicial.
