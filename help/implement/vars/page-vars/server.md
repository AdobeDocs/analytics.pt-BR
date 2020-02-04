---
title: servidor
description: Preencha a dimensão 'Servidores'.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# servidor

A `server` variável geralmente armazena o nome do host do site. Normalmente, é usado em conjuntos de relatórios que contêm dados de vários domínios. Funcionalmente é idêntico a uma prop.

## Servidor no Adobe Experience Platform Launch

Você pode definir o servidor ao configurar a extensão do Analytics (variáveis globais) ou as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Servidor] .

Você pode definir o servidor como qualquer valor de sequência de caracteres ou elemento de dados.

## s.server no AppMeasurement e Iniciar editor de código personalizado

A `s.server` variável é uma string que geralmente contém o nome do host do site. Tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
