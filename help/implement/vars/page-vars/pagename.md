---
title: pageName
description: O nome da página do seu site.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 81%

---


# pageName

A variável `pageName` geralmente armazena o nome de uma determinada página. É útil para determinar quais páginas individuais são mais populares. This variable populates the [Page](/help/components/dimensions/page.md) dimension.

Se essa variável não for definida em uma chamada de rastreamento de página específica, a variável [`pageURL`](pageurl.md) será usada.

>[!NOTE]
>
>Os servidores de coleta de dados de Adobe removem essa dimensão de todas as solicitações de imagem de rastreamento [de](/help/implement/vars/functions/tl-method.md) link. Se desejar que essa dimensão apareça nas ocorrências de rastreamento de link, considere copiar essa dimensão em um [eVar](evar.md).

## Nome da página no Adobe Experience Platform Launch

Você pode definir o nome da página ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Nome da página].

É possível definir o nome da página como qualquer valor de string, incluindo elementos de dados.

## s.pageName no AppMeasurement e no editor de código personalizado do Launch

A variável `s.pageName` é uma string que geralmente contém o nome da página. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados. Esse truncamento inclui instâncias nas quais é utilizada a `pageURL` se a variável estiver em branco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```

Se estiver usando a camada `digitalData` de [](../../prepare/data-layer.md)dados:

```js
s.pageName = digitalData.page.pageInfo.pageName;
```
