---
title: pageName
description: O nome da página em seu site.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# pageName

A `pageName` variável geralmente armazena o nome de uma determinada página. É útil determinar quais páginas individuais são mais populares. Essa variável preenche a dimensão &#39;Nome da página&#39;.

> [!NOTE] Essa dimensão é sempre removida das chamadas de rastreamento de link. Se você quiser ver o nome da página onde um link foi rastreado, considere copiar essa variável em uma eVar.

Se essa variável não for definida em uma chamada de rastreamento de página específica, a [`pageURL`](pageurl.md) variável será usada.

## Nome da página no Adobe Experience Platform Launch

Você pode definir o nome da página ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Localize a [!UICONTROL Page name] seção.

É possível definir o nome da página com qualquer valor de string, incluindo elementos de dados.

## s.pageName no AppMeasurement e Iniciar editor de código personalizado

A `s.pageName` variável é uma string que geralmente contém o nome da página. Tem um valor máximo de 100 bytes; valores mais longos são truncados. Esse truncamento inclui instâncias nas quais a variável é revertida `pageURL` se estiver em branco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
