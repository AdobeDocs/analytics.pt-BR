---
title: Serialização de eventos
description: Ajude a desduplicar métricas em seu site.
feature: Appmeasurement Implementation
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/43YfbDVjSH7ZJ8kqlXwAnb8UsIEoG3Ei-NRnkLLW63Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 87%

---

# Serialização da ID do evento

A serialização de eventos é um processo de implementação de medidas, usado para evitar que eventos duplicados sejam inseridos nos relatórios do Analytics. A desduplicação de eventos é importante nos casos em que você não deseja que métricas sejam infladas pelos visitantes que atualizam a página.

>[!NOTE]
>
>As fontes de dados não são compatíveis com a serialização de eventos ou a desduplicação.

## Configurar serialização de eventos

Primeiro, defina a [!UICONTROL Gravação de evento único] como [!UICONTROL Usar a ID de evento] nas configurações do conjunto de relatórios. Consulte [Evento bem-sucedido](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) no Guia do usuário de administração.

Ao usar IDs de evento, a desduplicação ocorre nos seguintes níveis:

* Cada variável usa sua própria tabela para desduplicação. Por exemplo, `event1:ABC` e `event2:ABC` são contados no relatório.
* A desduplicação ocorre globalmente, para todos os visitantes. Se o visitante A enviar `event1:ABC` e o visitante B também enviar `event1:ABC`, a Adobe ignorará a segunda instância do visitante B.
* A desduplicação não expira. Se um visitante enviar `event1:ABC` voltar 2 anos depois e enviar `event1:ABC` novamente, a Adobe ignorará a segunda instância.

>[!TIP]
>
>Se você quiser desduplicar o evento [`purchase`](event-purchase.md), use a variável [`purchaseID`](../purchaseid.md).

## Usar IDs de evento usando o SDK da Web

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), a serialização de eventos usará o campo XDM do evento desejado `id`. O caminho XDM completo depende de qual evento você deseja serializar.

Por exemplo, se você deseja serializar a métrica Adições ao carrinho, defina `xdm.commerce.productListAdds.id` com o valor de serialização desejado. Se você quiser serializar um evento Personalizado 20, defina `xdm._experience.analytics.event1to100.event20.id` para o valor de serialização desejado.

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), a serialização de eventos usará `data.__adobe.analytics.events`, seguindo a sintaxe da cadeia de caracteres do AppMeasurement.

## Usar IDs de evento usando a extensão do Adobe Analytics

É possível definir o campo de ID de evento ao configurar a extensão do Analytics (variáveis globais) ou como uma ação em uma regra.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
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

Se uma serialização de eventos estiver habilitada, mas não contiver uma ID de serialização, o evento sempre será contado.
