---
title: Serialização de eventos
description: Ajude a desduplicar métricas em seu site.
feature: Variables
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 83%

---

# Serialização da ID do evento

A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios do Analytics. A desduplicação de eventos é importante nos casos em que você não deseja que métricas sejam infladas pelos visitantes que atualizam a página.

>[!NOTE]
>
>As fontes de dados não são compatíveis com a serialização de eventos ou a desduplicação.

## Configurar serialização de eventos

Primeiro, defina a [!UICONTROL Gravação de evento único] como [!UICONTROL Usar a ID de evento] nas configurações do conjunto de relatórios. Consulte [Evento bem-sucedido](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) no Guia do usuário de administração.

Ao usar IDs de evento, a desduplicação ocorre nos seguintes níveis:

* Cada variável usa sua própria tabela para desduplicação. Por exemplo, `event1:ABC` e `event2:ABC` são contados no relatório.
* A desduplicação ocorre globalmente, para todos os visitantes. Se o visitante A enviar `event1:ABC` e o visitante B também enviar `event1:ABC`, a Adobe ignorará a segunda instância do visitante B.
* A desduplicação não expira. Se um visitante enviar `event1:ABC` voltar 2 anos depois e enviar `event1:ABC` novamente, a Adobe ignorará a segunda instância.

>[!TIP]
>
>Se você quiser desduplicar o evento [`purchase`](event-purchase.md), use a variável [`purchaseID`](../purchaseid.md).

## Usar IDs de evento usando o SDK da Web

Se estiver usando o [**Objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), a serialização de eventos usa o campo XDM do evento desejado `id`. O caminho XDM completo depende de qual evento você deseja serializar.

Por exemplo, se você deseja serializar a métrica Adições ao carrinho, defina `xdm.commerce.productListAdds.id` para o valor de serialização desejado. Se quiser serializar um evento personalizado 20, defina `xdm._experience.analytics.event1to100.event20` para o valor de serialização desejado.

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), a serialização de eventos usa `data.__adobe.analytics.events`, seguindo a sintaxe da string de AppMeasurement.

## Usar IDs de evento usando a extensão do Adobe Analytics

É possível definir o campo de ID de evento ao configurar a extensão do Analytics (variáveis globais) ou como uma ação em uma regra.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina o [!UICONTROL Extensão] para o Adobe Analytics e a caixa de diálogo [!UICONTROL Tipo de ação] para [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos], onde cada evento contém um campo [!UICONTROL ID de evento].

Valores válidos são caracteres alfanuméricos de até 20 bytes de tamanho. Se você inserir um valor com mais de 20 bytes, o sistema o truncará para os primeiros 20 bytes.

## Use Ids de evento no AppMeasurement e no editor de código personalizado da extensão do Analytics

A serialização de eventos faz parte da variável `s.events`. Atribua uma ID a cada evento usando o sinal de dois pontos na string.

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

Se uma serialização de eventos estiver ativada, mas não contiver uma ID de serialização, o evento sempre será contado.
