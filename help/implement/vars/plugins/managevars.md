---
title: manageVars
description: Altere os valores de mais de uma variável do Analytics de cada vez.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: manageVars

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `manageVars` permite manipular os valores de várias variáveis do Analytics de uma só vez. Você também pode definir valores como minúsculas ou remover caracteres desnecessários de múltiplos valores variáveis ao mesmo tempo. A Adobe recomenda usar esse plug-in se você desejar limpar o valor de múltiplas variáveis de uma só vez.

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
   * Tipo de ação: inicializar manageVars
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `manageVars` aceita os seguintes argumentos:

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

Chamar esse método não retorna nada. Em vez disso, altera os valores das variáveis do Analytics com base na função de retorno de chamada desejada.

## Exemplos de chamadas

### Exemplo #1

O código a seguir...

```js
s.manageVars("lowerCaseVars");
```

... altera os valores de todas as variáveis descritas acima para versões em minúsculas.  A única exceção a isso é a variável de eventos, pois alguns dos eventos (por exemplo, scAdd, scCheckout etc.) fazem distinção entre maiúsculas e minúsculas e não devem ser convertidos para minúsculas

### Exemplo #2

O código a seguir...

```js
s.manageVars("lowerCaseVars", "events", false);
```

... produz essencialmente o mesmo resultado que o primeiro exemplo, já que a variável de eventos não foi convertida em minúsculas por padrão.

### Exemplo #3

O código a seguir...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

... alterará (por exemplo, minúsculas) somente os valores de eVar1, eVar2, eVar3 e list2.

### Exemplo #4

O código a seguir...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

... alterará (por exemplo, minúsculas) os valores de todas as variáveis descritas acima, EXCETO da eVar1, eVar2, eVar3 e list2.

### Exemplo #5

O código a seguir...

```js
s.manageVars("cleanStr");
```

... altera os valores de todas as variáveis descritas acima, incluindo as variáveis de eventos.  Especificamente, a função de retorno de chamada cleanStr faz o seguinte com o valor de cada variável:

* Remove a codificação HTML
* Remove espaços em branco encontrados no início e no fim do valor
* Substitui aspas simples esquerda/direita (por exemplo, &quot;) por uma aspa simples reta (&#39;)
* Substitui caracteres de tabulação e caracteres de nova linha por espaços
* Substitui todos os espaços duplos (ou triplos etc.) por espaços únicos

## Histórico da versão

### 2.1 (14 de janeiro de 2019)

* Correção de erros para navegadores Internet Explorer 11.
* Alterações na `s.cleanStr`, que agora usa a função regular `cleanStr`.

### 2.0 (7 de maio de 2018)

* Lançamento pontual (incluindo reanálise/reescrita completa do plug-in)
* Função de retorno de chamada `cleanStr` adicionada
