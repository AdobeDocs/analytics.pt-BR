---
title: marketing
description: Preencha a dimensão 'Seções do site'.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# marketing

A `channel` variável geralmente armazena a seção do site em que uma determinada página está. É útil determinar quais grupos do site são mais populares. Essa variável preenche a dimensão &quot;Seções do site&quot;.

## Canal no Adobe Experience Platform Launch

É possível definir o canal ao configurar a extensão do Analytics (variáveis globais) ou as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Canal] .

Você pode definir o canal para qualquer valor de sequência de caracteres ou elemento de dados.

## s.channel no AppMeasurement e Iniciar editor de código personalizado

A `s.channel` variável é uma string que normalmente contém a seção do site da página. Tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
s.channel = "Example site section";
```
