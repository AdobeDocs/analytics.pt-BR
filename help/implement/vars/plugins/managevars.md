---
title: manageVars
description: Altere os valores de mais de uma variável do Analytics de cada vez.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Plug-in da Adobe: manageVars

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudar a obter mais valor com o uso do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O `manageVars` plug-in permite manipular os valores de várias variáveis do Analytics de uma só vez. Você também pode definir valores para caracteres em minúsculas ou remover caracteres desnecessários de vários valores variáveis ao mesmo tempo. A Adobe recomenda usar esse plug-in se desejar limpar o valor de várias variáveis de uma só vez.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar plug-ins usados com mais frequência.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo]
1. Instalar e publicar a extensão de Plug-ins  comuns do Analytics
1. Para qualquer Regra de inicialização em que você deseja usar o plug-in, adicione uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: Inicializar addProductEvar
1. Salvar e publicar as alterações na regra

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

O `manageVars` método usa os seguintes argumentos:

* **`cb`**(obrigatório, string): O nome de uma função de retorno de chamada que o plug-in usa para manipular as variáveis do Analytics. Você pode usar uma função da Adobe como`cleanStr`ou sua própria função personalizada.
* **`l`**(opcional, string): Uma lista delimitada por vírgulas de variáveis do Analytics que você deseja manipular. O padrão é TODAS as variáveis do Adobe Analytics quando não definidas, o que inclui:
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
* **`Il`**(opcional, booleano): Defina como`false`se você deseja *excluir*a lista de variáveis declaradas no`l`argumento em vez de incluí-las. O padrão é`true`.

Chamar esse método não retorna nada. Em vez disso, altera os valores das variáveis do Analytics com base na função de retorno de chamada desejada.

## Exemplos de chamadas

### Exemplo nº 1

O seguinte código...

```js
s.manageVars("lowerCaseVars");
```

...altera os valores de todas as variáveis descritas acima para versões em minúsculas.  A única exceção para isso é a variável events, como alguns dos eventos (por exemplo, scAdd, scCheckout etc.) fazem distinção entre maiúsculas e minúsculas e não devem ser minúsculas

### Exemplo nº 2

O seguinte código...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...produz essencialmente o mesmo resultado que o primeiro exemplo, já que a variável events não tem minúsculas por padrão.

### Exemplo 3

O seguinte código...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...alterará (por exemplo, minúsculas) somente os valores de eVar1, eVar2, eVar3 e list2

### Exemplo nº 4

O seguinte código...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...alterará (por exemplo, minúsculas) os valores de todas as variáveis descritas acima, EXCETO para eVar1, eVar2, eVar3 e list2

### Exemplo nº 5

O seguinte código...

```js
s.manageVars("cleanStr");
```

...altera os valores de todas as variáveis descritas acima, incluindo as variáveis de eventos.  Especificamente, a função de retorno de chamada cleanStr faz o seguinte para o valor de cada variável:

* Remove a codificação HTML
* Remove espaços em branco encontrados no início e no fim do valor
* Substitui aspas simples esquerda/direita (por exemplo, &quot;) com uma aspa simples reta (&#39;)
* Substitui caracteres de tabulação, caracteres de nova linha e caracteres de retorno de carro por espaços
* Substitui todo o duplo (ou triplo, etc.) espaços com espaços únicos

## Histórico da versão

### 2.1 (14 de janeiro de 2019)

* Correção de erros para navegadores Internet Explorer 11.
* Alterações para `s.cleanStr`, que agora usa a `cleanStr` função regular.

### 2.0 (7 de maio de 2018)

* Lançamento pontual (incluindo reanálise/regravação completa do plug-in)
* Função `cleanStr` de retorno de chamada adicionada
