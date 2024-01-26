---
title: canal
description: Preencha a dimensão “Seções do site”.
feature: Variables
exl-id: f494a051-a296-4f1c-9044-04a8b59376fa
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 76%

---

# canal

A variável `channel` geralmente armazena a seção do site em que uma determinada página está. É útil determinar quais grupos do site são mais populares. Essa variável preenche a dimensão &quot;Seções do site&quot;.

## Canal usando o SDK da Web

O canal é [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) no campo XDM `web.webPageDetails.siteSection`.

## Canal usando a extensão do Adobe Analytics

É possível definir um canal ao configurar a extensão do Analytics (variáveis globais) ou sob Regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina o [!UICONTROL Extensão] para o Adobe Analytics e a caixa de diálogo [!UICONTROL Tipo de ação] para [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Canal].

Você pode definir um canal como qualquer valor de string ou elemento de dados.

## s.channel no AppMeasurement e o editor de código personalizado da extensão do Analytics

A variável `s.channel` é uma string que normalmente contém a seção do site da página. A variável tem um valor máximo de 100 bytes; valores mais longos são truncados.

```js
s.channel = "Example site section";
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.channel = digitalData.page.category.primaryCategory;
```
