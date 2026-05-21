---
title: trackInlineStats
description: (Desativado) Ativar ou desativar o ClickMap na implementação.
keywords: desativar clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: https://experienceleague.adobe.com/K6rwl-ZECfoMLfC0Z25PPq2jV1FBo0cTsl1YfDeNpBQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 29%

---

# trackInlineStats

>[!IMPORTANT]
>
>Essa variável foi removida e não é mais usada.

O ClickMap é um recurso removido do Adobe Analytics que coleta dados sobre onde os visitantes clicam e no que clicam. O recurso foi substituído por [Activity Map](/help/analyze/activity-map/overview.md).

Quando habilitado, o AppMeasurement coleta informações sobre o link e envia esses dados na próxima solicitação de imagem. As informações de cada clique são armazenadas em um cookie rotulado como `s_sq`.

## Ativar o ClickMap usando a extensão do Adobe Analytics

[!UICONTROL Habilitar ClickMap] é uma caixa de seleção na opção [!UICONTROL Rastreamento de link] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Habilitar ClickMap].

>[!NOTE]
>
>Esta caixa de seleção é diferente da caixa de seleção [!UICONTROL Usar Activity Map], que está na opção [!UICONTROL Gerenciamento de biblioteca].

## s.trackInlineStats no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.trackInlineStats` é um booliano que habilita ou desabilita o rastreamento de ClickMap. Como o recurso é desativado, a Adobe não recomenda definir essa variável. Seu valor padrão é `false`.

```js
s.trackInlineStats = false;
```
