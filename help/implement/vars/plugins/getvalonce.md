---
title: getValOnce
description: Impedir que uma variável do Analytics seja definida com o mesmo valor duas vezes seguidas.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Plug-in da Adobe: getValOnce

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `getValOnce` -in impede que uma variável seja definida igual ao mesmo valor mais de uma vez. A Adobe recomenda usar esse plug-in quando você deseja desduplicar ocorrências em que um visitante atualiza uma página ou visita uma determinada página várias vezes. Esse plug-in é desnecessário se você não estiver preocupado com a métrica &quot;Ocorrências&quot; na Analysis Workspace.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Catalog] botão
1. Instalar e publicar a [!UICONTROL Common Analytics Plugins] extensão
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhum
   * Evento: Principal - Biblioteca carregada (início da página)
1. Adicione uma ação à regra acima com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar getValOnce
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão na extensão do Adobe Analytics.
1. Amplie o [!UICONTROL Configure tracking using custom code] acordeão, que revela o [!UICONTROL Open Editor] botão.
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

## Instale o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getValOnce` método usa os seguintes argumentos:

* **`vtc`** (obrigatório, string): A variável para verificar se foi definida anteriormente como um valor idêntico
* **`cn`** (opcional, string): O nome do cookie que contém o valor a ser verificado. O padrão é `"s_gvo"`
* **`et`** (opcional, número inteiro): A expiração do cookie em dias (ou minutos, dependendo do `ep` argumento). O padrão é `0`, que expira no final da sessão do navegador
* **`ep`** (opcional, string): Somente defina esse argumento se o `et` argumento também estiver definido. Configure esse argumento para `"m"` se desejar que o `et` argumento expire em minutos em vez de dias. O padrão é `"d"`, que define o `et` argumento em dias.

Se o `vtc` argumento e o valor do cookie corresponderem, esse método retornará uma string vazia. Se o `vtc` argumento e o valor do cookie não corresponderem, o método retornará o `vtc` argumento como uma string.

## Exemplos de chamadas

### Exemplo nº 1

Use esta chamada para evitar que o mesmo valor seja transmitido para s.campaign mais de uma vez seguidas nos próximos 30 dias:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

Na chamada acima, o plug-in primeiro comparará o valor já contido no cookie s_campaign com o valor proveniente da variável s.campaign atual.   Se não houver correspondência, o plug-in definirá o cookie s_campaign igual ao novo valor proveniente de s.campaign e retornará o novo valor.   Essa comparação acontecerá nos próximos trinta dias

### Exemplo nº 2

Use esta chamada para impedir que o mesmo valor seja definido na sessão:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Esse código impede que o mesmo valor seja passado para s.eVar2 mais de uma vez seguidas durante a sessão do usuário.  Ele também ignora o valor &quot;m&quot; no parâmetro (no final da chamada), pois a hora de expiração é definida como 0.   O código também armazena o valor de comparação no cookie s_ev2.

## Histórico da versão

### 2.0

* Lançamento de ponto (recompilado, tamanho de código menor).

### 1.1

* Adicionada a opção de escolher minutos ou dias para a expiração por meio do `t` parâmetro.
* Corrigido o escopo da `k` variável usada para restringi-la somente ao plug-in. Essa alteração evita possíveis interferências com outros códigos na página.
