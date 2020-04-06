---
title: pageName
description: O nome da página do seu site.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# pageName

A variável `pageName` geralmente armazena o nome de uma determinada página. É útil para determinar quais páginas individuais são mais populares. Essa variável preenche a dimensão “Nome da página”.

>[!NOTE] Essa dimensão sempre é removida das chamadas de rastreamento de link. Se você quiser ver o nome da página onde um link foi rastreado, considere copiar essa variável em uma eVar.

Se essa variável não for definida em uma chamada de rastreamento de página específica, a variável [`pageURL`](pageurl.md) será usada.

## Nome da página no Adobe Experience Platform Launch

Você pode definir o nome da página ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Locate the [!UICONTROL Page name] section.

É possível definir o nome da página como qualquer valor de string, incluindo elementos de dados.

## s.pageName no AppMeasurement e no editor de código personalizado do Launch

A variável `s.pageName` é uma string que geralmente contém o nome da página. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados. Esse truncamento inclui instâncias nas quais é utilizada a `pageURL` se a variável estiver em branco.

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
