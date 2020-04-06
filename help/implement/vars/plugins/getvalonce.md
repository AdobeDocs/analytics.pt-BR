---
title: getValOnce
description: Impeça que uma variável do Analytics seja definida com o mesmo valor duas vezes seguidas.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getValOnce

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getValOnce` impede que uma variável seja definida com o mesmo valor mais de uma vez. A Adobe recomenda usar esse plug-in quando você deseja desduplicar ocorrências nas quais um visitante atualiza uma página ou visita uma determinada página várias vezes. Esse plug-in é desnecessário se você não se preocupar com a métrica &quot;Ocorrências&quot; no Analysis Workspace.

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
   * Tipo de ação: inicializar getValOnce
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
/* Adobe Consulting Plugin: getValOnce v2.0 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:ep);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getValOnce` aceita os seguintes argumentos:

* **`vtc`** (obrigatório, string): a variável cujo valor será verificado para conferir se já teve anteriormente um valor idêntico
* **`cn`** (opcional, string): o nome do cookie que contém o valor a ser verificado. O padrão é `"s_gvo"`
* **`et`** (opcional, número inteiro): a validade do cookie em dias (ou minutos, dependendo do argumento `ep`). O padrão é `0`, que expira no final da sessão do navegador
* **`ep`** (opcional, string): somente defina esse argumento se o argumento `et` também estiver definido. Configure esse argumento como `"m"` se desejar que o argumento `et` expire em minutos em vez de dias. O padrão é `"d"`, que define o argumento `et` para dias.

Se o argumento `vtc` e o valor do cookie corresponderem, esse método retornará uma string vazia. Se o argumento `vtc` e o valor do cookie não corresponderem, o método retornará o argumento `vtc` como uma string.

## Exemplos de chamadas

### Exemplo #1

Use esta chamada para evitar que o mesmo valor seja transmitido para s.campaign mais de uma vez seguida nos próximos 30 dias:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

Na chamada acima, o plug-in primeiro comparará o valor já contido no cookie s_campaign com o valor proveniente da variável s.campaign atual.   Se não houver correspondência, o plug-in definirá o cookie s_campaign com o novo valor proveniente de s.campaign e retornará o novo valor.   Essa comparação acontecerá nos próximos trinta dias.

### Exemplo #2

Use esta chamada para impedir que o mesmo valor seja definido na sessão:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Esse código impede que o mesmo valor seja transmitido para s.eVar2 mais de uma vez seguida durante a sessão do usuário.  Ele também ignora o valor &quot;m&quot; no parâmetro (no final da chamada), pois a hora de expiração está definida como 0.   O código também armazena o valor da comparação no cookie s_ev2.

## Histórico da versão

### 2.0

* Versão pontual (recompilada, menor tamanho de código).

### 1.1

* Adicionada a opção de escolher minutos ou dias para a expiração por meio do parâmetro `t`.
* Corrigido o escopo da variável `k` usada para restringi-la somente ao plug-in. Essa alteração evita possíveis interferências com outros códigos na página.
