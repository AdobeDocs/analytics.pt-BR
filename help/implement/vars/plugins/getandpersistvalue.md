---
title: getAndPersistValue
description: Armazene um valor que pode ser recuperado posteriormente a qualquer momento.
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Plug-in da Adobe: getAndPersistValue

> [!IMPORTANT] Este plug-in é fornecido pela Adobe Consulting como cortesia para ajudar a obter mais valor com o uso do Adobe Analytics. O Atendimento ao cliente da Adobe não fornece suporte para este plug-in, incluindo instalação ou solução de problemas. Se precisar de ajuda com esse plug-in, entre em contato com o Gerente de conta de sua organização. Eles podem organizar uma reunião com um consultor para obter assistência.

O plug- `getAndPersistValue` in permite armazenar um valor em um cookie que pode ser recuperado posteriormente durante uma visita. Ela desempenha uma função semelhante ao recurso de duração [!UICONTROL do] armazenamento no Adobe Experience Platform Launch. A Adobe recomenda usar esse plug-in se você quiser manter automaticamente uma variável do Analytics com o mesmo valor em ocorrências subsequentes após a definição da variável. Este plug-in não é necessário se o recurso de duração [!UICONTROL do] armazenamento do Launch for suficiente ou se você não precisar definir e persistir variáveis com o mesmo valor em ocorrências subsequentes. A persistência integrada das eVars não requer o uso desse plug-in, pois essas variáveis persistem no lado do servidor pela Adobe.

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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usar o plug-in

O `getAndPersist` método usa os seguintes argumentos:

* **`vtp`**(obrigatório): O valor para persistir de página em página
* **`cn`**(opcional): O nome do cookie para armazenar o valor. Se este argumento não estiver definido, o cookie é nomeado`"s_gapv"`
* **`ex`**(opcional): O número de dias antes do cookie expirar. Se esse argumento for`0`ou não estiver definido, o cookie expirará no final da visita (30 minutos de inatividade).

Se a variável no `vtp` argumento estiver definida, o plug-in definirá o cookie e retornará o valor do cookie. Se a variável no `vtp` argumento não estiver definida, o plug-in retornará somente o valor do cookie.

## Exemplos

### Exemplo nº 1

O código a seguir definirá eVar21 igual ao valor de &quot;hello&quot;.  O código definirá o cookie ev21gapv, que expirará em 28 dias, igual ao valor de eVar21 (ou seja, &quot;olá&quot;).  O código definirá (re)eVar21 igual ao valor do cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo nº 2

Suponha que a eVar21 ainda não tenha sido definida na página atual, mas tenha sido definida como &quot;hello&quot; em uma página anterior nos últimos 28 dias.   O código a seguir só definirá eVar21 igual ao valor do cookie ev21gapv (ou seja, &quot;olá&quot;).  Ele não redefine o cookie ev21gapv, pois eVar21 não foi definida na página atual antes da função ser chamada.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo 3

Suponha que a eVar21 ainda não tenha sido definida na página atual, mas tenha sido definida como &quot;hello&quot; em uma página anterior nos últimos 28 dias.  O código a seguir definirá somente prop35 igual ao valor do cookie ev21gapv (ou seja, &quot;olá&quot;).  Ele não definirá a eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo nº 4

O código a seguir definirá eVar21 igual ao valor de &quot;howdy&quot;.  O código definirá (ou redefinirá) o cookie ev21gapv, que expirará em 28 dias, igual ao valor de eVar21 (ou seja, &quot;uau&quot;).  O código definirá prop35 igual ao valor do cookie ev21gapv (ou seja, &quot;uau&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo nº 5

Suponha que s.eVar21 não tenha sido definido em nenhuma página nos últimos 28 dias.  O código a seguir definirá s.eVar21 igual a nada, pois o cookie ev21gapv expiraria 28 dias após sua última definição.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemplo nº 6

O código a seguir definirá a eVar30 igual a &quot;compra&quot;.  Em seguida, ele definirá o cookie s_gapv, que expirará no final da sessão do navegador, igual ao valor de s.eVar30 (ou seja, &quot;shopping&quot;).  Em seguida, definirá s.eVar30 igual ao valor do cookie s_gapv (ou seja, a chamada getAndPersistValue retorna o valor do cookie s_gapv, que neste caso é &quot;shopping&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Se s.eVar30 não estiver definido como um valor explícito em quaisquer páginas adicionais vistas durante a sessão, mas estiver definido (em doPlugins) pelo seguinte código...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 será definida como &quot;shopping&quot; (ou seja, o valor persistente do cookie s_gapv)

## Histórico da versão

### 2.0 (16 de abril de 2018)

* Lançamento de ponto (tamanho de código menor)
* Passar 0 para o `ex` argumento agora força a expiração após 30 minutos de inatividade em vez de expirar no final da sessão do navegador.

### 1.0 (18 de janeiro de 2016)

* Versão inicial.
