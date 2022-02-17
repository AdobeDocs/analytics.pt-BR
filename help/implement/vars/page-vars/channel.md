---
title: canal
description: Preencha a dimensão “Seções do site”.
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 100%

---

# canal

A variável `channel` geralmente armazena a seção do site em que uma determinada página está. É útil determinar quais grupos do site são mais populares. Essa variável preenche a dimensão &quot;Seções do site&quot;.

## Canal usando tags na Adobe Experience Platform

É possível definir um canal ao configurar a extensão do Analytics (variáveis globais) ou sob Regras.

1. Faça logon na [Interface da coleção de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Canal].

Você pode definir um canal como qualquer valor de string ou elemento de dados.

## s.channel no AppMeasurement e no editor de código personalizado do 

A variável `s.channel` é uma string que normalmente contém a seção do site da página. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
s.channel = "Example site section";
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
