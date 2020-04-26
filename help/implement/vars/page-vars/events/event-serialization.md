---
title: Serialização de eventos
description: Ajude a desduplicar métricas em seu site.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Serialização da ID do evento

A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios do Analytics. A desduplicação de eventos é importante nos casos em que você não deseja que métricas sejam infladas pelos visitantes que atualizam a página.

>[!NOTE] As fontes de dados não são compatíveis com serialização de eventos ou com desduplicação.

## Configurar serialização de eventos

Primeiro, defina a [!UICONTROL Gravação de evento único] como [!UICONTROL Usar a ID de evento] nas configurações do conjunto de relatórios. Consulte [Evento bem-sucedido](/help/admin/admin/c-success-events/success-event.md) no Guia do usuário de administração.

Ao usar IDs de evento, a desduplicação ocorre nos seguintes níveis:

* Cada variável usa sua própria tabela para desduplicação. Por exemplo, `event1:ABC` e `event2:ABC` são contados no relatório.
* A desduplicação ocorre globalmente, para todos os visitantes. Se o visitante A enviar `event1:ABC` e o visitante B também enviar `event1:ABC`, a Adobe ignorará a segunda instância do visitante B.
* A desduplicação não expira. Se um visitante enviar `event1:ABC` voltar 2 anos depois e enviar `event1:ABC` novamente, a Adobe ignorará a segunda instância.

>[!TIP] Se você quiser desduplicar o evento [`purchase`](event-purchase.md), use a variável [`purchaseID`](../purchaseid.md).

## Usar IDs de evento no Adobe Experience Platform Launch

É possível definir o campo de ID de evento ao configurar a extensão do Analytics (variáveis globais) ou como uma ação em uma regra.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos], onde cada evento contém um campo [!UICONTROL ID de evento].

Valores válidos são caracteres alfanuméricos de até 20 bytes de tamanho.

## Usar IDs de evento no AppMeasurement e no editor de código personalizado do Launch

A serialização de eventos faz parte da variável `s.events`. Atribua uma ID a cada evento usando o sinal de dois pontos na string.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se uma serialização de eventos estiver ativada, mas não contiver uma ID de serialização, o evento sempre será contado.
