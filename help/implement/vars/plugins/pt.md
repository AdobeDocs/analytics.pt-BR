---
title: pt
description: Executa uma função em uma lista de variáveis.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe: pt

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `pt` -in executa uma função ou um método em uma lista de variáveis do Analytics. Por exemplo, você pode executar seletivamente o `clearVars` método em várias variáveis sem chamar manualmente o método a cada vez. Vários outros plug-ins dependem desse código para serem executados corretamente. Esse plug-in não é necessário se você não precisar executar uma função específica em mais de uma variável do Analytics por vez ou se não estiver usando plug-ins dependentes.

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
   * Tipo de ação: Inicializar pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `pt` método usa os seguintes argumentos:

* **`l`**(obrigatório, string): Uma lista de variáveis que a função contida no`cf`argumento pode executar.
* **`de`**(opcional, string): O delimitador que separa a lista de variáveis no`l`argumento. O padrão é uma vírgula (`,`).
* **`cf`**(obrigatório, string): O nome da função de retorno de chamada contida no objeto AppMeasurement a ser chamado em relação a cada uma das variáveis contidas no`l`argumento.
* **`fa`**(opcional, string): Se a função no`cf`argumento exigir argumentos adicionais ao ser executada, inclua-os aqui. O padrão é`undefined`.

Chamar esse método retornará um valor se a função de retorno de chamada (no `cf` argumento) retornar um valor.

## Exemplos de chamadas

### Exemplo nº 1

O código a seguir faz parte do plug-in getQueryParam.  Ela executa a função auxiliar getParameterValue em relação a cada um dos pares de valor chave contidos na sequência de caracteres de consulta do URL (fullQueryString).  Em outro lugar, para extrair cada par de valor chave, fullQueryString deve ser delimitado e dividido por um caractere &quot;&amp;&quot; de E comercial. O parâmetroKey se refere ao parâmetro da string de consulta que o plug-in está tentando extrair especificamente da string de consulta

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

* Alterações menores no código para reduzir o tamanho geral

### 2.0 (17 de abril de 2018)

* Lançamento de ponto (recompilado, tamanho de código menor).
* Adicionado suporte para código H e AppMeasurement.

### 1.0 (23 de setembro de 2013)

* Versão inicial.
