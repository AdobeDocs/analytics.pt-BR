---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 61%

---

# useBeacon

A maioria dos navegadores modernos inclui o método nativo `navigator.sendBeacon()`. Ele envia de forma assíncrona uma pequena quantidade de dados por HTTP para um servidor web. O AppMeasurement pode usar o método `navigator.sendBeacon()` se a variável `useBeacon` estiver ativada. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

Se `useBeacon` estiver ativado, a próxima ocorrência enviada para a Adobe usará o método `navigator.sendBeacon()` do navegador em vez de uma solicitação de imagem `GET` padrão. Essa variável se aplica às solicitações de imagem [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md). Ela requer o AppMeasurement versão 2.17.0 ou superior.

>[!TIP]
>
>O AppMeasurement ativa `useBeacon` automaticamente para solicitações de imagem de link de saída.

A variável `useBeacon` é ignorada quando o visitante usa um navegador sem suporte a `navigator.sendBeacon()`. O uso dessa variável exige o AppMeasurement 2.16.0 ou posterior.

## Usar a API sendBeacon da Web SDK

O **[!UICONTROL O documento será descarregado]** em uma Configuração de ação determina se os dados enviados para o Adobe usam a API sendBeacon.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para o [!UICONTROL Regras] e, em seguida, clique na regra desejada.
1. Em [!UICONTROL Ações], clique na Ação desejada ou clique no botão **&#39;+&#39;** para adicionar uma nova ação.
1. Defina as [!UICONTROL Extensão] lista suspensa para **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Tipo de ação] para **[!UICONTROL Enviar evento]**
1. Clique na caixa de seleção **[!UICONTROL O documento será descarregado]** à direita.

Se essa caixa estiver marcada, os dados são enviados para o Adobe usando a API sendBeacon. Ela está desmarcada por padrão.

## Usar a API sendBeacon manualmente implementando o SDK da Web

Definir `documentUnloading` para `true` ao enviar um evento. Se não estiver definido, seu valor padrão será `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Consulte [Uso da API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) na documentação do SDK da Web para obter mais informações.

## Usar o beacon usando a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.useBeacon no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.useBeacon` é do tipo booleano e determina se o AppMeasurement usa o método `navigator.sendBeacon()` do navegador. O valor padrão é `false`. Defina essa variável como `true` antes de chamar uma função de rastreamento se desejar usar a natureza assíncrona do `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Depois que uma chamada de rastreamento é executada, essa variável é redefinida como `false`. Se sua implementação enviar várias solicitações de imagem no mesmo carregamento de página (como no caso de aplicativos de página única), defina essa variável como `true` antes de cada chamada de rastreamento.
