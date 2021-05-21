---
title: servidor
description: Preencha a dimensão “Servidores”.
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '159'
ht-degree: 100%

---

# servidor

A variável `server` geralmente armazena o nome do host do site. Normalmente, é usada em conjuntos de relatórios que contêm dados de vários domínios. Funcionalmente é idêntica a uma prop.

## Servidor no Adobe Experience Platform Launch

Você pode definir o servidor ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Servidor].

Você pode definir o servidor como qualquer valor do tipo string ou elemento de dados.

## s.server no AppMeasurement e no editor de código personalizado do Launch

A variável `s.server` é uma string que geralmente contém o nome do host do site. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
