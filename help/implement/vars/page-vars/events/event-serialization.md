---
title: Serialização de eventos
description: Ajude a desduplicar métricas em seu site.
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# Serialização da ID do evento

A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios da Adobe. A eliminação da duplicação de eventos é importante nos casos em que você não deseja que as métricas sejam infladas pelos visitantes que atualizam a página.

> [!NOTE] As fontes de dados não são compatíveis com a serialização de eventos ou a eliminação da duplicação.

## Configurar serialização de eventos

Primeiro, defina a Gravação [!UICONTROL de evento] único de um evento como [!UICONTROL Usar a ID] de evento nas configurações do conjunto de relatórios. See [Success Events](../../../../admin/admin/c-success-events/success-event.md) in the Admin user guide.

Ao usar IDs de evento, a eliminação da duplicação ocorre nos seguintes níveis:

* Cada variável usa sua própria tabela para eliminar a duplicação. Por exemplo, `event1:ABC` e ambos `event2:ABC` são contados no relatório.
* A eliminação da duplicação ocorre globalmente em todos os visitantes. Se o visitante A enviar `event1:ABC` , o visitante B também enviará `event1:ABC`, a Adobe ignorará a segunda instância do visitante B.
* A eliminação da duplicação não expira. Se um visitante enviar `event1:ABC` voltar 2 anos depois e enviar `event1:ABC` novamente, a Adobe ignorará a segunda instância.

> [!TIP] Se você quiser cancelar a duplicação do `purchase` evento, use a `purchaseID` variável.

## Usar IDs de evento no Adobe Experience Platform Launch

É possível definir o campo de ID de evento ao configurar a extensão do Analytics (variáveis globais) ou como uma ação em uma regra.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos] , onde cada evento contém um campo de ID [!UICONTROL de] evento.

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
