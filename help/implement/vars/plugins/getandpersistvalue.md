---
title: getAndPersistValue
description: Armazene um valor que pode ser recuperado posteriormente a qualquer momento.
exl-id: b562f9ad-3844-4535-b729-bd3f63f6f0ae
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '934'
ht-degree: 100%

---

# Plug-in da Adobe: getAndPersistValue

>[!IMPORTANT]
>
>Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getAndPersistValue` permite armazenar um valor em um cookie que pode ser recuperado posteriormente durante uma visita. Ele desempenha uma função semelhante ao recurso [!UICONTROL Duração de armazenamento] no Adobe Experience Platform Launch. A Adobe recomenda usar esse plug-in se você quiser manter automaticamente uma variável do Analytics com o mesmo valor em ocorrências subsequentes à definição da variável. Este plug-in não é necessário se o recurso de [!UICONTROL Duração de armazenamento] do Launch for suficiente ou se você não precisar definir e fazer persistir variáveis com o mesmo valor em ocorrências subsequentes. A persistência integrada das eVars não requer o uso desse plug-in, pois essas variáveis persistem no lado do servidor por ação da Adobe.

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
   * Tipo de ação: inicializar getAndPersistValue
1. Salve e publique as alterações na regra.

## Instale o plug-in usando o editor de código personalizado do Launch

Se você não quiser usar a extensão do plug-in, poderá usar o editor de código personalizado.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
1. Clique na propriedade desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] na extensão do Adobe Analytics.
1. Expanda a opção [!UICONTROL Configurar rastreamento usando código personalizado], que revela o botão [!UICONTROL Abrir editor].
1. Abra o editor de código personalizado e cole na janela de edição o código do plug-in fornecido abaixo.
1. Salve e publique as alterações na extensão do Analytics.

## Instalar o plug-in usando o AppMeasurement

Copie e cole o seguinte código em qualquer lugar no arquivo AppMeasurement depois que o objeto de rastreamento do Analytics for instanciado (usando [`s_gi`](../functions/s-gi.md)). A preservação de comentários e números de versão do código na sua implementação ajuda a Adobe a solucionar possíveis problemas.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O método `getAndPersist` aceita os seguintes argumentos:

* **`vtp`** (obrigatório): o valor a ser persistido de página em página
* **`cn`** (opcional): o nome do cookie que armazenará o valor. Se este argumento não estiver definido, o cookie é nomeado como `"s_gapv"`
* **`ex`** (opcional): o número de dias antes do cookie expirar. Se esse argumento for `0` ou não estiver definido, o cookie expirará no final da visita (após 30 minutos de inatividade).

Se a variável no argumento `vtp` estiver definida, o plug-in definirá o cookie e retornará o valor do cookie. Se a variável no argumento `vtp` não estiver definida, o plug-in apenas retornará o valor do cookie.

## Exemplos

### Exemplo #1

O código a seguir definirá eVar21 como &quot;Olá&quot;.  O código definirá o cookie ev21gapv, que expirará em 28 dias, com o valor de eVar21 (ou seja, &quot;Olá&quot;).  O código (re)definirá eVar21 com o valor do cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo #2

Suponha que a eVar21 ainda não tenha sido definida na página atual, mas tenha sido definida como &quot;Olá&quot; em uma página anterior nos últimos 28 dias.   O código a seguir somente definirá eVar21 com o valor do cookie ev21gapv (ou seja, &quot;Olá&quot;).  Ele não redefine o cookie ev21gapv, pois eVar21 não foi definida na página atual antes da função ser chamada.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo #3

Suponha que a eVar21 ainda não tenha sido definida na página atual, mas tenha sido definida como &quot;Olá&quot; em uma página anterior nos últimos 28 dias.  O código a seguir definirá somente prop35 com o valor do cookie ev21gapv (ou seja, &quot;Olá&quot;).  Ele não definirá a eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo #4

O código a seguir definirá eVar21 como &quot;E aí&quot;.  O código definirá (ou redefinirá) o cookie ev21gapv, que expirará em 28 dias, com o valor de eVar21 (ou seja, &quot;E aí&quot;).  O código definirá prop35 com o valor do cookie ev21gapv (ou seja, &quot;E aí&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo #5

Suponha que s.eVar21 não tenha sido definido em nenhuma página nos últimos 28 dias.  O código a seguir definirá s.eVar21 igual a nada, pois o cookie ev21gapv expiraria 28 dias após a última definição.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo #6

O código a seguir definirá a eVar30 como &quot;compras&quot;.  Em seguida, ele definirá o cookie s_gapv, que expirará no final da sessão do navegador, com o valor da s.eVar30 (ou seja, &quot;compras&quot;).  Em seguida, ele definirá a s.eVar30 com o valor do cookie s_gapv (ou seja, a chamada getAndPersistValue retorna o valor do cookie s_gapv, que, neste caso, é &quot;compras&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Se s.eVar30 não estiver definida como um valor explícito em qualquer página adicional vista durante a sessão, mas for definido (em doPlugins) pelo seguinte código...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

... s.eVar30 será definida como &quot;compras&quot; (ou seja, com o valor persistente do cookie s_gapv)

## Histórico da versão

### 3.0 (19 de março de 2021)

* Adição do número da versão como dados de contexto.

### 2.0 (16 de abril de 2018)

* Lançamento pontual (tamanho de código menor)
* Transmitir 0 para o argumento `ex` agora força a expiração após 30 minutos de inatividade em vez de no final da sessão do navegador.

### 1.0 (18 de janeiro de 2016)

* Versão inicial.
