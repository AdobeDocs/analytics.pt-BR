---
title: servidor
description: Preencha a dimensão “Servidores”.
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 75%

---

# servidor

A variável `server` geralmente armazena o nome do host do site. Normalmente, é usada em conjuntos de relatórios que contêm dados de vários domínios. Funcionalmente é idêntica a uma prop.

## Servidor que usa o SDK da Web

O servidor é [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) no campo XDM `web.webPageDetails.server`.

## Servidor usando a extensão Adobe Analytics

Você pode definir o servidor ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina as [!UICONTROL Extensão] lista suspensa para o Adobe Analytics e a [!UICONTROL Tipo de ação] para [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Servidor].

Você pode definir o servidor como qualquer valor do tipo string ou elemento de dados.

## s.server no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.server` é uma string que geralmente contém o nome do host do site. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
