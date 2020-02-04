---
title: pageURL
description: Substitua o URL da página coletado automaticamente em seu site.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# pageURL

O AppMeasurement coleta automaticamente o URL da página em cada ocorrência. Se você quiser substituir o URL da página coletado automaticamente pelo AppMeasurement, use essa variável. Não é necessário definir essa variável na maioria dos casos.

> [!NOTE] Essa variável não é uma dimensão disponível na Analysis Workspace. Ela só está disponível no Data Warehouse e nos Feeds de dados. Se você deseja usar o URL da página como uma dimensão na Analysis Workspace, considere passar a `pageURL` variável para uma eVar em cada ocorrência.

Às vezes, os URLs têm mais de 255 bytes. O AppMeasurement usa o parâmetro da string de `g` consulta para os primeiros 255 bytes do URL em solicitações de imagem. Se um URL tiver mais de 255 bytes, o restante do URL será armazenado no parâmetro da string de `-g` consulta. As strings de protocolo e consulta no URL são incluídas nesta variável.

## URL da página no Adobe Experience Platform Launch

O Launch preenche automaticamente o URL da página. No entanto, é possível definir a substituição do URL da página ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção URL [!UICONTROL da] página.

Você pode definir o URL da página como qualquer valor de string.

## s.pageURL no AppMeasurement e Iniciar editor de código personalizado

A `s.pageURL` variável é uma string que contém o URL da página. O AppMeasurement coleta essa variável automaticamente, no entanto, você pode substituir seu valor, se desejar.

```js
s.pageURL = "https://example.com";
```

Se você deseja usar o URL da página como uma dimensão nos relatórios, considere usar o seguinte na implementação:

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
