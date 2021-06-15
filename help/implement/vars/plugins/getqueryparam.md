---
title: getQueryParam
description: Extraia o valor de um parâmetro de string de consulta do URL.
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: 5a087087c8f54650173391bd7766bfdfd12ccb7e
workflow-type: ht
source-wordcount: '918'
ht-degree: 100%

---

# Plug-in da Adobe: getQueryParam

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getQueryParam` permite que você extraia o valor de qualquer parâmetro de string de consulta contido em um URL. É útil para extrair códigos de campanha, internos e externos, de URLs de páginas iniciais. Também é importante ao extrair termos de pesquisa ou outros parâmetros da string de consulta.

Esse plug-in fornece recursos robustos para a análise de URLs complexos, incluindo hashes e URLs que contêm vários parâmetros de string de consulta. Se você só precisa obter parâmetros de string de consulta simples, a Adobe recomenda usar os recursos de parâmetros de URL do Launch ou o método [`Util.getQueryParam()`](../functions/util-getqueryparam.md) incluído no AppMeasurement.

## Instale o plug-in usando a extensão Adobe Experience Platform Launch

A Adobe oferece uma extensão que permite usar os plug-ins usados com mais frequência.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Catálogo].
1. Instale e publique a extensão [!UICONTROL Plug-ins comuns do Analytics].
1. Caso ainda não o tenha feito, crie uma regra denominada &quot;Inicializar plug-ins&quot; com a seguinte configuração:
   * Condição: Nenhuma
   * Evento: principal – biblioteca carregada (início da página)
1. Adicione à regra acima uma ação com a seguinte configuração:
   * Extensão: Plug-ins comuns do Analytics
   * Tipo de ação: inicializar getQueryParam
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getQueryParam` aceita os seguintes argumentos:

* **`qsp`** (obrigatório): uma lista delimitada por vírgulas com parâmetros da string de consulta a serem procurados no URL. Não diferencia maiúsculas e minúsculas.
* **`de`** (opcional): o delimitador a ser usado se vários parâmetros da string de consulta corresponderem. O padrão é uma string vazia.
* **`url`** (opcional): um URL, string ou variável personalizados usados para extrair os valores de parâmetro da string de consulta. O padrão é `window.location`.

Esse método retorna um valor diferente a depender dos argumentos acima e do URL:

* Se um parâmetro de string de consulta correspondente não for encontrado, o método retornará uma string vazia.
* Se um parâmetro de string de consulta correspondente for encontrado, o método retornará o valor do parâmetro da string de consulta.
* Se um parâmetro de string de consulta correspondente for encontrado, mas o valor estiver vazio, o método retornará `true`.
* Se vários parâmetros de string de consulta correspondentes forem encontrados, o método retornará uma string com cada valor de parâmetro delimitado pela string no argumento `de`.

## Exemplos de chamadas

### Exemplo #1

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1
```

O código a seguir definirá s.campaign como &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid');
```

### Exemplo #2

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

O código a seguir definirá s.campaign como &quot;trackingcode1:123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Exemplo #3

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

O código a seguir definirá s.campaign como &quot;trackingcode1123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Exemplo #4

Se o URL atual for o seguinte:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

O código a seguir definirá s.campaign como &quot;123456&quot;:

```js
s.campaign=s.getQueryParam('ecid');
```

### Exemplo #5

Se o URL atual for o seguinte:

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

O código a seguir definirá s.campaign como &quot;123456&quot;

```js
s.campaign=s.getQueryParam('ecid');
```

**Observação:** o plug-in substitui o hash de verificação do URL por um ponto de interrogação se um não existir.  Se o URL contiver um ponto de interrogação antes do hash, o plug-in substituirá o hash de verificação do URL por um “e” comercial (&amp;);

### Exemplo #6

Se o URL atual for o seguinte...

```js
http://www.abc123.com/
```

... e se a variável s.testURL estiver definida da seguinte maneira:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

O código a seguir não definirá s.campaign:

```js
s.campaign=s.getQueryParam('cid');
```

No entanto, o código a seguir definirá s.campaign como &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**Observação:** o terceiro parâmetro pode ser qualquer string/variável na qual o código tentará localizar os parâmetros da string de consulta

O código a seguir definirá s.eVar2 como &quot;123456|trackingcode1|true|300&quot;:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* O valor “123456” vem do parâmetro ecid da variável s.testURL
* O valor “trackingcode1” vem do parâmetro cid da variável s.testURL
* O valor “true” provém da existência (mas não do valor) do parâmetro location após o hash da variável s.testURL

O valor “300” vem do valor do parâmetro pos da variável s.testURL

## Histórico da versão

### 4.0.1 (26 de março de 2021)

* Atualização do problema em que indefinido era retornado em vez de &quot;&quot; se o parâmetro de consulta não estivesse presente na sequência de consulta.

### 4.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.
* Remoção de dependências no plug-in pt.

### 3.3 (24 de setembro de 2019)

* Lógica desnecessária ignorada para reduzir o tamanho do código

### 3.2 (15 de maio de 2018)

* Funções `findParameterValue` e `getParameterValue` movidas para a função `getQueryParam`

### 3.1 (10 de maio de 2018)

* Correção de um problema na captura de parâmetros sem valor da string de consulta

### 3.0 (16 de abril, 2018)

* Versão pontual (recompilada, menor tamanho de código).
* Funções auxiliares renomeadas para `findParameterValue` e `getParameterValue` para fins de legibilidade.
* Foi removida a necessidade de adicionar um argumento para localização de parâmetros contidos no hash do URL

### 2.5 (8 de janeiro de 2016)

* Compatível com H-code e AppMeasurement (requer `s.pt` com o AppMeasurement).

### 2.4

* Foi adicionado o parâmetro `h`, permitindo que o código localize os parâmetros da string de consulta que estão após o hash (`#`)

### 2.3

* Correção de um problema de regressão em que o plug-in funcionava somente quando o hash estava presente após o código de rastreamento

### 2.2

* Agora remove os caracteres de hash (e tudo depois) do valor de retorno

### 2.1

* Compatível com o H.10 code
