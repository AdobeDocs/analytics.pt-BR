---
title: getPageName
description: Crie um pageName fácil de ler a partir do caminho do site atual.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getPageName

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getPageName` cria uma versão formatada amigável e fácil de ler do URL atual. A Adobe recomenda usar esse plug-in se você quiser um valor de [`pageName`](../page-vars/pagename.md) fácil de definir e de entender nos relatórios. Esse plug-in será desnecessário se você já tiver uma estrutura de nomeação para a variável `pageName`, como por meio de uma camada de dados. Ele é melhor usado quando você não tem outra solução para definir a variável `pageName`.

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
   * Tipo de ação: inicializar getPageName
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
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getPageName` aceita os seguintes argumentos:

* **`si`** (opcional, string): uma ID inserida no início da string que representa a ID do site. Esse valor pode ser uma ID numérica ou um nome amigável. Quando não estiver definido, o padrão será o domínio atual.
* **`qv`** (opcional, string): uma lista, delimitada por vírgulas, de parâmetros da string de consulta que, se encontrados no URL, são adicionados à string
* **`hv`** (opcional, string): uma lista de parâmetros delimitada por vírgulas encontrada no hash do URL que, se encontrados no URL, são adicionados à string
* **`de`** (opcional, string): o delimitador usado para dividir partes individuais da string. O padrão é uma barra vertical (`|`).

O método retorna uma string que contém uma versão amigável do URL. Normalmente, essa string é atribuída à variável `pageName`, mas também pode ser usada em outras variáveis.

## Exemplos de chamadas

### Exemplo #1

Se o URL atual fosse...

```js
https://mail.google.com/mail/u/0/#inbox
```

... e o código a seguir for executado...

```js
s.pageName = getPageName()
```

... o valor final de s.pageName será:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Exemplo #2

Se o URL atual fosse...

```js
https://mail.google.com/mail/u/0/#inbox
```

... e o código a seguir for executado...

```js
s.pageName = getPageName("gmail")
```

... o valor final de s.pageName será:

```js
s.pageName = "gmail|mail|u|0";
```

### Exemplo #3

Se o URL atual fosse...

```js
https://www.google.com/
```

... e o código a seguir for executado...

```js
s.pageName = getPageName()
```

... o valor final de s.pageName será:

```js
s.pageName = "www.google.com|home"
```

**Observação**: quando o código é executado em um URL que não contém um caminho, ele sempre adicionará o valor de &quot;home&quot; ao final do valor de retorno

### Exemplo #4

Se o URL atual fosse...

```js
https://www.google.com/
```

... e o código a seguir for executado...

```js
s.pageName = getPageName("google","","","|")
```

... o valor final de s.pageName será:

```js
s.pageName = "google|home"
```

### Exemplo #5

Se o URL atual fosse...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

... e o código a seguir for executado...

```js
s.pageName = getPageName()
```

... o valor final de s.pageName será:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

No entanto, se, em vez disso, o código a seguir for executado...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

... o valor final de s.pageName será:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Melhorias em relação às versões anteriores

A versão 4.0+ do plug-in getPageName não depende da existência do objeto AppMeasurement do Adobe Analytics (ou seja, do objeto &quot;s&quot;) para ser executado.  Se você optar por atualizar para esta versão, altere o código que chama o plug-in removendo qualquer instância do objeto &quot;s&quot; da chamada.
Por exemplo, altere isso:

```js
s.pageName = s.getPageName();
```

...para isto:

```js
s.pageName = getPageName();
```

## Histórico da versão

### 4.1 (17 de setembro de 2019)

* Delimitador padrão alterado para um caractere de barra vertical (era dois pontos + espaço).

### 4.0 (22 de maio de 2018)

* Reanálise/reescrita completa do plug-in
