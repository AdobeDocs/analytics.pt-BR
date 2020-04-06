---
title: getAndPersistValue
description: Armazene um valor que pode ser recuperado posteriormente a qualquer momento.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in da Adobe: getAndPersistValue

>[!IMPORTANT] Esse plug-in é fornecido pela Adobe Consulting como cortesia para ajudar você a tirar maior proveito do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, o que inclui instalação ou solução de problemas. Se você precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Ele pode organizar uma reunião com um consultor para obter ajuda.

O plug-in `getAndPersistValue` permite armazenar um valor em um cookie que pode ser recuperado posteriormente durante uma visita. It serves a similar role to the [!UICONTROL Storage duration] feature in Adobe Experience Platform Launch. A Adobe recomenda usar esse plug-in se você quiser manter automaticamente uma variável do Analytics com o mesmo valor em ocorrências subsequentes à definição da variável. This plug-in is not necessary if Launch&#39;s [!UICONTROL Storage duration] feature is sufficient, or if you do not need to set and persist variables to the same value in subsequent hits. A persistência integrada das eVars não requer o uso desse plug-in, pois essas variáveis persistem no lado do servidor por ação da Adobe.

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
   * Tipo de ação: inicializar getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
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

### 2.0 (16 de abril de 2018)

* Lançamento pontual (tamanho de código menor)
* Transmitir 0 para o argumento `ex` agora força a expiração após 30 minutos de inatividade em vez de no final da sessão do navegador.

### 1.0 (18 de janeiro de 2016)

* Versão inicial.
