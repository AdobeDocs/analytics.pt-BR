---
title: events
description: Defina a variável events, que governa a maioria das métricas do site.
exl-id: 6ef99ee5-40c3-4ff2-a75d-c97f2e8ec1f8
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---

# events

Dimensões e métricas são componentes vitais para os relatórios. A variável `events` é responsável pela coleta de dados de muitas métricas do site. Eventos normalmente incrementam [métricas](/help/components/metrics/overview.md) em relatórios.

Antes de implementar eventos, você deve criá-los e configurá-los em [Eventos-bem sucedidos](/help/admin/admin/c-success-events/success-event.md) nas configurações do Conjunto de relatórios. Se você planeja usar eventos personalizados em ocorrências de rastreamento de link, verifique se [`linkTrackVars`](../../config-vars/linktrackvars.md) e [`linkTrackEvents`](../../config-vars/linktrackevents.md) estão definidos corretamente.

## Eventos no Adobe Experience Platform Launch

Você pode definir eventos ao configurar a extensão do Analytics (variáveis globais) ou em Regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos].

Vários recursos estão disponíveis:

* Uma lista suspensa permite selecionar o evento para incluir.
* um campo de texto opcional para serialização. Consulte [Serialização de eventos](event-serialization.md) para obter mais informações.
* Um campo de texto opcional para um valor de evento. Você pode incluir moeda para eventos de moeda, ou um número inteiro para eventos que não sejam de moeda para incrementá-lo várias vezes. Por exemplo, a seleção de `event1` na lista suspensa e a inclusão de `10` neste campo incrementa `event1` em 10 nos relatórios.
* Um botão para adicionar outro evento. Não há um limite razoável para o número de eventos que podem ser incluídos em uma ocorrência.

## s.events no AppMeasurement e no editor de código personalizado do Launch

A variável `s.events` é uma string que contém uma lista de eventos delimitada por vírgulas para inclusão na ocorrência. Não há limite de bytes para essa variável, portanto, ela não é truncada. Os valores válidos incluem:

* `event1` e `event1000`: eventos personalizados, definidos como você desejar. Registre como você usa cada evento no [documento de design de solução](../../../prepare/solution-design.md) da sua organização. O número de eventos disponíveis depende do contrato do Analytics de sua organização. A maioria das organizações com contratos não herdados tem 1000 eventos personalizados disponíveis. Entre em contato com o gerente de conta de sua organização se não tiver certeza de quantos eventos personalizados estão disponíveis para você.
* `purchase`: incrementa a métrica [&quot;Pedidos&quot;](/help/components/metrics/orders.md) em 1 e obtém valores definidos na variável `products` para calcular [&quot;Unidades&quot;](/help/components/metrics/units.md) e [&quot;Receita&quot;](/help/components/metrics/revenue.md). Consulte [Evento de compra](event-purchase.md) para obter mais informações.
* `prodView`: incrementa a métrica [“Visualizações de produto”](/help/components/metrics/product-views.md).
* `scOpen`: incrementa a métrica [“Carrinhos”](/help/components/metrics/carts.md).
* `scAdd`: incrementa a métrica [“Adições ao carrinho”](/help/components/metrics/cart-additions.md).
* `scRemove`: incrementa a métrica [“Remoções do carrinho”](/help/components/metrics/cart-removals.md).
* `scView`: incrementa a métrica [“Visualizações do carrinho”](/help/components/metrics/cart-views.md).
* `scCheckout`: incrementa a métrica [“Check-outs”](/help/components/metrics/checkouts.md).

>[!NOTE]
>
>Essa variável diferencia maiúsculas e minúsculas. Evite usar maiúsculas e minúsculas incorretas em valores de evento para garantir uma coleta de dados precisa.

```js
// Set the events variable to a single value
s.events = "event1";

// Set the events variable to multiple values
s.events = "event1,event13,purchase";
```

### Incrementar eventos contadores várias vezes

Se desejar, é possível contar eventos personalizados mais de uma vez. Atribua um número inteiro ao evento desejado dentro da string. Os eventos criados nas configurações do conjunto de relatórios são eventos contadores por padrão.

```js
// Count event1 ten times
s.events = "event1=10";

// Count event1 twice and event2 once
s.events = "event1=2,event2";
```

>[!NOTE]
>
>Os eventos contadores não suportam valores decimais ou de moeda. Use eventos de moeda para moedas ou eventos numéricos para valores decimais.

### Usar eventos de moeda

Você pode alterar um evento personalizado para usar moeda em vez de números inteiros. Os eventos de moeda são convertidos automaticamente para a moeda do conjunto de relatórios se ela e a variável `currencyCode` não coincidirem. Eles são úteis para ajudar a calcular custos de envio, descontos ou reembolsos. Você pode definir eventos de moeda na variável `products` se quiser atribuir o evento somente a esse produto.

Antes de implementar eventos de moeda, defina o evento desejado como “Moeda” em [Eventos bem-sucedidos](/help/admin/admin/c-success-events/success-event.md) nas configurações do Conjunto de relatórios.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in Report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

>[!NOTE]
>
>Se você definir um valor de moeda na variável `events` e na `products`, o valor de moeda em `events` será usado. Evite definir valores de moeda nas variáveis `events` e `products`.

### Usar eventos numéricos

É possível alterar um evento personalizado para aceitar valores decimais em vez de números inteiros. Os eventos numéricos se comportam de forma semelhante aos eventos de moeda, exceto por não usarem a conversão de moeda. Você pode definir eventos numéricos na variável `products` se quiser atribuir o evento somente a esse produto.

Antes de implementar eventos numéricos, defina o evento desejado como “Numérico” em [Eventos bem-sucedidos](/help/admin/admin/c-success-events/success-event.md) nas configurações do Conjunto de relatórios.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in Report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

>[!NOTE]
>
>Se você definir um valor numérico na variável `events` e na `products`, o valor numérico em `events` será usado. Evite definir valores numéricos nas variáveis `events` e `products`.
