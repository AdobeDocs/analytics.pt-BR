---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
feature: Appmeasurement Implementation
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-drQZhKcoWzWfwcbFKms2xV2eunuNYIjkm4AWTmD-Pg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 60%

---

# useBeacon

A maioria dos navegadores modernos inclui o método nativo `navigator.sendBeacon()`. Ele envia de forma assíncrona uma pequena quantidade de dados por HTTP para um servidor web. O AppMeasurement pode usar o método `navigator.sendBeacon()` se a variável `useBeacon` estiver habilitada. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

Se `useBeacon` estiver habilitado, a próxima ocorrência enviada para a Adobe usará o método `navigator.sendBeacon()` do navegador em vez de uma solicitação de imagem `GET` padrão. Essa variável se aplica às solicitações de imagem [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md). Ela requer o AppMeasurement versão 2.17.0 ou superior.

>[!TIP]
>
>O AppMeasurement habilita `useBeacon` automaticamente para solicitações de imagem de link de saída.

A variável `useBeacon` é ignorada quando o visitante usa um navegador sem suporte a `navigator.sendBeacon()`. O uso dessa variável exige o AppMeasurement 2.16.0 ou posterior.

## Usar a API sendBeacon usando a extensão Web SDK

O **[!UICONTROL Documento descarregará a caixa de seleção]** em uma Configuração de ação que determina se os dados enviados para o Adobe usam a API sendBeacon.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Regras] e clique na regra desejada.
1. Em [!UICONTROL Ações], clique na Ação desejada ou clique no ícone **&#39;+&#39;** para adicionar uma nova ação.
1. Defina a lista suspensa [!UICONTROL Extensão] como **[!UICONTROL Adobe Experience Platform Web SDK]** e o [!UICONTROL Tipo de Ação] como **[!UICONTROL Enviar evento]**
1. Clique na caixa de seleção **[!UICONTROL Documento será descarregado]** à direita.

Se essa caixa estiver marcada, os dados serão enviados para o Adobe usando a API sendBeacon. Ela está desmarcada por padrão.

## Use a API sendBeacon para implementar manualmente o Web SDK

Definir `documentUnloading` como `true` ao enviar um evento. Se não estiver definido, seu valor padrão é `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Consulte [Usando a API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) na documentação do Web SDK para obter mais informações.

## Usar beacon usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.useBeacon no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.useBeacon` é do tipo booleano e determina se o AppMeasurement usa o método `navigator.sendBeacon()` do navegador. O valor padrão é `false`. Defina essa variável como `true` antes de chamar uma função de rastreamento se desejar usar a natureza assíncrona do `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Depois que uma chamada de rastreamento é executada, essa variável é redefinida como `false`. Se sua implementação enviar várias solicitações de imagem no mesmo carregamento de página (como no caso de aplicativos de página única), defina essa variável como `true` antes de cada chamada de rastreamento.
