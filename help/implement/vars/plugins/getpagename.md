---
title: getPageName
description: Crie um pageName fácil de ler a partir do caminho do site atual.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Plug-in da Adobe: getPageName

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `getPageName` -in cria uma versão formatada fácil de ler e amigável do URL atual. A Adobe recomenda usar esse plug-in se você quiser um [`pageName`](../page-vars/pagename.md) valor fácil de definir e entender nos relatórios. Esse plug-in será desnecessário se você já tiver uma estrutura de nomeação para a `pageName` variável, por exemplo, por meio de uma camada de dados. Ele é melhor usado quando você não tem outra solução para definir a `pageName` variável.

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
   * Tipo de ação: Inicializar getPageName
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
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getPageName` método usa os seguintes argumentos:

* **`si`** (opcional, string): Uma ID inserida no início da string que representa a ID do site. Esse valor pode ser uma ID numérica ou um nome amigável. Quando não estiver definido, o padrão será o domínio atual.
* **`qv`** (opcional, string): Uma lista delimitada por vírgulas de parâmetros da string de consulta que, se encontrada no URL, são adicionados à string
* **`hv`** (opcional, string): Uma lista de parâmetros delimitada por vírgulas encontrada no hash do URL que, se encontrado no URL, é adicionada à string
* **`de`** (opcional, string): O delimitador para dividir partes individuais da string. O padrão é um pipe (`|`).

O método retorna uma string contendo uma versão formatada amigavelmente do URL. Normalmente, essa string é atribuída à `pageName` variável, mas também pode ser usada em outras variáveis.

## Exemplos de chamadas

### Exemplo nº 1

Se o URL atual fosse...

```js
https://mail.google.com/mail/u/0/#inbox
```

...e o código a seguir é executado...

```js
s.pageName = getPageName()
```

...o valor final de s.pageName será:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Exemplo nº 2

Se o URL atual fosse...

```js
https://mail.google.com/mail/u/0/#inbox
```

...e o código a seguir é executado...

```js
s.pageName = getPageName("gmail")
```

...o valor final de s.pageName será:

```js
s.pageName = "gmail|mail|u|0";
```

### Exemplo 3

Se o URL atual fosse...

```js
https://www.google.com/
```

...e o código a seguir é executado...

```js
s.pageName = getPageName()
```

...o valor final de s.pageName será:

```js
s.pageName = "www.google.com|home"
```

**Observação**: Quando o código é executado em um URL que não contém um caminho, ele sempre adicionará o valor de &quot;home&quot; ao final do valor de retorno

### Exemplo nº 4

Se o URL atual fosse...

```js
https://www.google.com/
```

...e o código a seguir é executado...

```js
s.pageName = getPageName("google","","","|")
```

...o valor final de s.pageName será:

```js
s.pageName = "google|home"
```

### Exemplo nº 5

Se o URL atual fosse...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...e o código a seguir é executado...

```js
s.pageName = getPageName()
```

...o valor final de s.pageName será:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

No entanto, se o código a seguir for executado...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...o valor final de s.pageName será:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Atualização de versões anteriores

A versão 4.0+ do plug-in getPageName não depende da existência do objeto AppMeasurement do Adobe Analytics (ou seja, o objeto &quot;s&quot;) a ser executado.  Se optar por atualizar para esta versão, altere o código que chama o plug-in removendo qualquer instância do objeto &quot;s&quot; da chamada.
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

* Valor do delimitador padrão alterado para um caractere de barra vertical (de dois pontos + espaço).

### 4.0 (22 de maio de 2018)

* Reanálise/regravação completa do plug-in
