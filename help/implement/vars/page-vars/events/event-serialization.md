---
title: Serialização de eventos
description: Ajude a desduplicar métricas em seu site.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Serialização da ID do evento

A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios da Adobe. A eliminação da duplicação de eventos é importante nos casos em que você não deseja que as métricas sejam infladas pelos visitantes que atualizam a página.

> [!NOTE] As fontes de dados não são compatíveis com a serialização de eventos ou a eliminação da duplicação.

## Configurar serialização de eventos

Primeiro, você deve definir um evento como [!UICONTROL Unique Event Recording] nas configurações do conjunto [!UICONTROL Use Event ID] de relatórios. See [Success Events](/help/admin/admin/c-success-events/success-event.md) in the Admin user guide.

Ao usar IDs de evento, a eliminação da duplicação ocorre nos seguintes níveis:

* Cada variável usa sua própria tabela para eliminar a duplicação. Por exemplo, `event1:ABC` e ambos `event2:ABC` são contados no relatório.
* A eliminação da duplicação ocorre globalmente em todos os visitantes. Se o visitante A enviar `event1:ABC` , o visitante B também enviará `event1:ABC`, a Adobe ignorará a segunda instância do visitante B.
* A eliminação da duplicação não expira. Se um visitante enviar `event1:ABC` voltar 2 anos depois e enviar `event1:ABC` novamente, a Adobe ignorará a segunda instância.

> [!TIP] Se você quiser cancelar a duplicação do [`purchase`](event-purchase.md) evento, use a [`purchaseID`](../purchaseid.md) variável.

## Usar IDs de evento no Adobe Experience Platform Launch

É possível definir o campo de ID de evento ao configurar a extensão do Analytics (variáveis globais) ou como uma ação em uma regra.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Rules] guia e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Localize a [!UICONTROL Events] seção, onde cada evento contém um [!UICONTROL Event ID] campo.

Valores válidos são caracteres alfanuméricos de até 20 bytes de comprimento.

## Usar IDs de evento no editor de código personalizado do AppMeasurement e do Launch

A serialização de eventos faz parte da `s.events` variável. Atribua uma ID a cada evento usando dois pontos na string.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se uma serialização de eventos estiver ativada, mas não contiver uma ID de serialização, o evento sempre será contado.
