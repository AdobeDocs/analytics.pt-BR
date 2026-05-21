---
title: servidor
description: Preencha a dimensão “Servidores”.
feature: Appmeasurement Implementation
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
TQID: https://experienceleague.adobe.com/HR37R-XDPYMhGTYxNbavO7utFH9wZgXNLDGdnmm-Gb0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 82%

---

# servidor

A variável `server` geralmente armazena o nome do host do site. Normalmente, é usada em conjuntos de relatórios que contêm dados de vários domínios. Funcionalmente é idêntica a uma prop.

## Servidor usando o Web SDK

O servidor está mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Servidor usando a extensão do Adobe Analytics

Você pode definir o servidor ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
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
