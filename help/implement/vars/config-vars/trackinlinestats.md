---
title: trackInlineStats
description: (Desativado) Ativar ou desativar o ClickMap na implementação.
keywords: desativar clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 28%

---

# trackInlineStats

>[!IMPORTANT]
>
>Essa variável foi removida e não é mais usada.

O ClickMap é um recurso descontinuado no Adobe Analytics que coleta dados sobre onde os visitantes clicam e no que clicam. O recurso foi substituído por [Activity Map](/help/analyze/activity-map/overview.md).

Quando ativado, o AppMeasurement coleta informações sobre o link e envia esses dados na próxima solicitação de imagem. As informações de cada clique são armazenadas em um cookie rotulado como `s_sq`.

## Ativar ClickMap usando a extensão do Adobe Analytics

[!UICONTROL Habilitar ClickMap] é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Habilitar ClickMap].

>[!NOTE]
>
>Esta caixa de seleção é diferente da caixa de seleção [!UICONTROL Usar Activity Map], que está na opção [!UICONTROL Gerenciamento de biblioteca].

## s.trackInlineStats no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackInlineStats` é um booliano que habilita ou desabilita o rastreamento de ClickMap. Como o recurso é desativado, o Adobe não recomenda configurar essa variável. Seu valor padrão é `false`.

```js
s.trackInlineStats = false;
```
