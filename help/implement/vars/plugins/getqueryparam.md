---
title: getQueryParam
description: Extraia o valor de um parâmetro de string de consulta do URL.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Plug-in da Adobe: getQueryParam

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudá-lo a obter mais valor do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `getQueryParam` -in permite que você extraia o valor de qualquer parâmetro de string de consulta contido em um URL. É útil para extrair códigos de campanha, internos e externos, de URLs de página inicial. Também é importante ao extrair termos de pesquisa ou outros parâmetros da string de consulta.

Este plug-in fornece recursos robustos na análise de URLs complexos, incluindo hashes e URLs que contêm vários parâmetros de string de consulta. Se você só tiver necessidades de parâmetro de sequência de consulta simples, a Adobe recomenda usar os recursos de parâmetro de URL no Launch ou o `Util.getQueryParam` método incluído no AppMeasurement.

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
   * Tipo de ação: Inicializar getQueryParam
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado Iniciar

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código] personalizado, que revela o botão [!UICONTROL Abrir editor] .
1. Abra o editor de código personalizado e cole o código do plug-in fornecido abaixo na janela de edição.
1. Salve e publique as alterações na extensão do Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getQueryParam` método usa os seguintes argumentos:

* **`qsp`**(obrigatório): Uma lista delimitada por vírgulas de parâmetros da string de consulta para procurar dentro do URL. Não faz distinção entre maiúsculas e minúsculas.
* **`de`**(opcional): O delimitador a ser usado se vários parâmetros da string de consulta corresponderem. O padrão é uma string vazia.
* **`url`**(opcional): Um URL personalizado, uma sequência de caracteres ou uma variável para extrair os valores de parâmetro da string de consulta. O padrão é`window.location`.

Chamar esse método retorna um valor dependendo dos argumentos acima e do URL:

* Se um parâmetro de string de consulta correspondente não for encontrado, o método retornará uma string vazia.
* Se um parâmetro de string de consulta correspondente for encontrado, o método retornará o valor do parâmetro da string de consulta.
* Se um parâmetro de string de consulta correspondente for encontrado, mas o valor estiver vazio, o método retornará `true`.
* Se vários parâmetros de string de consulta correspondentes forem encontrados, o método retornará uma string com cada valor de parâmetro delimitado pela string no `de` argumento.

## Exemplos de chamadas

### Exemplo #1

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1
```

O código a seguir definirá s.campaign igual a &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid');
```

### Exemplo #2

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

O código a seguir definirá s.campaign igual a &quot;trackingcode1:123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Exemplo 3

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

O código a seguir definirá s.campaign igual a &quot;trackingcode1123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Exemplo #4

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

O código a seguir definirá s.campaign igual a &quot;123456&quot;:

```js
s.campaign=s.getQueryParam('ecid');
```

### Exemplo #5

Se o URL atual for o seguinte:

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

O código a seguir definirá s.campaign igual a &quot;123456&quot;

```js
s.campaign=s.getQueryParam('ecid');
```

**** Observação: O plug-in substitui o URL ao caractere hash de Check por um ponto de interrogação se um ponto de interrogação não existir.  Se o URL contiver um ponto de interrogação anterior ao caractere de hash, o plug-in substituirá o URL para o caractere de hash de Check por um E comercial;

### Exemplo #6

Se o URL atual for o seguinte...

```js
http://www.abc123.com/
```

...e se a variável s.testURL estiver definida da seguinte maneira:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

O código a seguir não definirá s.campaign de forma alguma:

```js
s.campaign=s.getQueryParam('cid');
```

No entanto, o código a seguir definirá s.campaign igual a &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**** Observação: o terceiro parâmetro pode ser qualquer string/variável que o código usará para tentar localizar os parâmetros da string de consulta em

O código a seguir definirá s.eVar2 igual a &quot;123456|trackingcode1|true|300&quot;:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* O valor de 123456 vem do parâmetro ecid na variável s.testURL
* O valor de trackingcode1 vem do parâmetro cid na variável s.testURL
* O valor de true provém da existência (mas não do valor) do parâmetro location após o caractere hash na variável s.testURL

O valor de 300 vem do valor do parâmetro pos na variável s.testURL

## Histórico da versão

### 3.3 (24 de setembro de 2019)

* A lógica desnecessária foi ignorada para reduzir o tamanho do código

### 3.2 (15 de maio de 2018)

* Movido `findParameterValue` e `getParameterValue` funções para a `getQueryParam` função

### 3.1 (10 de maio de 2018)

* Correção de um problema com a captura de parâmetros da string de consulta sem valor

### 3.0 (16 de abril de 2018)

* Lançamento de ponto (recompilado, tamanho de código menor).
* Funções auxiliares renomeadas para `findParameterValue` e `getParameterValue` para fins de leitura.
* Foi removida a necessidade de adicionar um argumento para localizar parâmetros contidos no hash do URL

### 2.5 (8 de janeiro de 2016)

* Compatível com o código H e o AppMeasurement (requer `s.pt` o AppMeasurement).

### 2.4

* Foi adicionado o `h` parâmetro, permitindo que o código localize os parâmetros da string de consulta encontrados após o caractere hash (`#`)

### 2.3

* Correção de um problema de regressão em que o plug-in funcionava somente quando o hash estava presente após o código de rastreamento

### 2.2

* Agora remove os caracteres de hash (e tudo depois) do valor de retorno

### 2.1

* Compatível com o código H.10
