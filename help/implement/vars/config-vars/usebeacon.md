---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 62%

---

# useBeacon

A maioria dos navegadores modernos inclui o método nativo `navigator.sendBeacon()`. Ele envia de forma assíncrona uma pequena quantidade de dados por HTTP para um servidor web. O AppMeasurement pode usar o método `navigator.sendBeacon()` se a variável `useBeacon` estiver ativada. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

Se `useBeacon` estiver ativado, a próxima ocorrência enviada para a Adobe usará o método `navigator.sendBeacon()` do navegador em vez de uma solicitação de imagem `GET` padrão. Essa variável se aplica às solicitações de imagem [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md). Ela requer o AppMeasurement versão 2.17.0 ou superior.

>[!TIP]
>
>O AppMeasurement ativa `useBeacon` automaticamente para solicitações de imagem de link de saída.

A variável `useBeacon` é ignorada quando o visitante usa um navegador sem suporte a `navigator.sendBeacon()`. O uso dessa variável exige o AppMeasurement 2.16.0 ou posterior.

## Usar a API sendBeacon usando a extensão SDK da Web

O **[!UICONTROL Documento descarregará a caixa de seleção]** em uma Configuração de ação que determina se os dados enviados para o Adobe usam a API sendBeacon.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Regras] e clique na regra desejada.
1. Em [!UICONTROL Ações], clique na Ação desejada ou clique no ícone **&#39;+&#39;** para adicionar uma nova ação.
1. Defina a lista suspensa [!UICONTROL Extensão] como **[!UICONTROL Adobe Experience Platform Web SDK]** e o [!UICONTROL Tipo de Ação] como **[!UICONTROL Enviar evento]**
1. Clique na caixa de seleção **[!UICONTROL Documento será descarregado]** à direita.

Se essa caixa estiver marcada, os dados serão enviados para o Adobe usando a API sendBeacon. Ela está desmarcada por padrão.

## Usar a API sendBeacon implementando manualmente o SDK da Web

Definir `documentUnloading` como `true` ao enviar um evento. Se não estiver definido, seu valor padrão é `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Consulte [Usando a API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) na documentação do SDK da Web para obter mais informações.

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
