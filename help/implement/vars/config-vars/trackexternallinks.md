---
title: trackExternalLinks
description: Ative ou desative o rastreamento automático de links para links de saída.
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '189'
ht-degree: 100%

---

# trackExternalLinks

A Adobe oferece a capacidade de rastrear links externos sem definir manualmente o método [`tl()`](../functions/tl-method.md) para cada link de saída. Ative essa variável se desejar usar o rastreamento automático de links para links de saída.

Quando ativado, o AppMeasurement compara qualquer URL de link clicado com valores em [`linkInternalFilters`](linkinternalfilters.md) e [`linkExternalFilters`](linkexternalfilters.md). Se houver uma correspondência, uma chamada de rastreamento de link de saída será acionada automaticamente.

## Rastrear links externos usando tags na Adobe Experience Platform

Rastrear links externos é uma caixa de seleção na opção [!UICONTROL Rastreamento de links] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Interface da coleção de dados](https://experience.adobe.com/data-collection) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Rastreamento de link], que revela a caixa de seleção [!UICONTROL Rastrear links externos].

Clique na caixa de seleção para ativar o rastreamento automático de links de saída.

## s.trackExternalLinks no AppMeasurement e no editor de código personalizado do

`s.trackExternalLinks` é uma variável do tipo booleano que ativa ou desativa o rastreamento automático de links de saída. Se você não quiser rastrear links externos, ou se preferir chamar manualmente o método `tl()` para rastrear links de saída, defina essa variável como `false`.

```js
s.trackExternalLinks = true;
```
