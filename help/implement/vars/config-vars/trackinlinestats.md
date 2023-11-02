---
title: trackInlineStats
description: Ative ou desative o ClickMap na implementação.
keywords: desativar clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 31%

---

# trackInlineStats

>[!IMPORTANT]
>
>Essa variável foi removida. Consulte [Habilitar Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) em vez disso.

O ClickMap é um recurso descontinuado no Adobe Analytics que coleta dados sobre onde os visitantes clicam e no que clicam. O recurso foi substituído por [Activity Map](/help/analyze/activity-map/activity-map.md).

Quando ativado, o AppMeasurement coleta informações sobre o link e envia esses dados na próxima solicitação de imagem. As informações de cada clique são armazenadas em um cookie rotulado `s_sq`.

## Ativar ClickMap usando a extensão do Adobe Analytics

[!UICONTROL Ativar ClickMap] é uma caixa de seleção na [!UICONTROL Rastreamento de link] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a [!UICONTROL Rastreamento de link] acordeão, que revela a [!UICONTROL Ativar ClickMap] caixa de seleção

>[!NOTE]
>
>Essa caixa de seleção é diferente da caixa [!UICONTROL Usar Activity Map] que está na caixa de seleção [!UICONTROL Gerenciamento de biblioteca] acordeão.

## s.trackInlineStats no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.trackInlineStats` é uma variável do tipo booleano que ativa ou desativa o rastreamento de ClickMap. Como o recurso é desativado, o Adobe não recomenda configurar essa variável. Seu valor padrão é `false`.

```js
s.trackInlineStats = false;
```
