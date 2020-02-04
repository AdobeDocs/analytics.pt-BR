---
title: events
description: Defina a variável events, que governa a maioria das métricas do site.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# events

Dimensões e métricas são componentes vitais para os relatórios. A `events` variável é responsável pela coleta de dados de muitas métricas do site.

## Eventos no Adobe Experience Platform Launch

Você pode definir eventos ao configurar a extensão do Analytics (variáveis globais) ou as regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos] .

Vários recursos estão disponíveis:

* Uma lista suspensa permite selecionar o evento para incluir
* Um campo de texto opcional para serialização. See [event serialization](event-serialization.md) for more information.
* Um campo de texto opcional para um valor de evento. Você pode incluir moeda para eventos de moeda, ou um número inteiro para eventos que não sejam de moeda para aumentá-la várias vezes. Por exemplo, a seleção `event1` na lista suspensa e a inclusão `10` neste campo aumenta `event1` em 10 nos relatórios.
* Um botão para adicionar outro evento. Não há um limite razoável para o número de eventos que podem ser incluídos em uma ocorrência.

## s.events no AppMeasurement e no editor de código personalizado Iniciar

A `s.events` variável é uma string que contém uma lista de eventos delimitada por vírgulas para inclusão na ocorrência. Não há limite de bytes para essa variável, portanto, ela não é truncada. Os valores válidos incluem:

* `event1` - `event1000`: Eventos personalizados, definidos como você desejar. Registre como você usa cada evento no documento [de design de](../../../prepare/solution-design.md)solução da sua organização. O número de eventos disponíveis depende do contrato do Analytics de sua organização. A maioria das organizações em contratos não herdados tem 1000 eventos personalizados disponíveis. Entre em contato com o gerente de conta de sua organização se não tiver certeza de quantos eventos personalizados estão disponíveis para você.
* `purchase`: Aumenta a métrica &quot;Pedidos&quot; em 1 e obtém valores definidos na `products` variável para calcular &quot;Unidades&quot; e &quot;Receita&quot;. Consulte Evento [de](event-purchase.md) compra para obter mais informações.
* `prodView`: Aumenta a métrica &#39;Exibições de produto&#39;.
* `scOpen`: Aumenta a métrica &#39;Carrinhos&#39;.
* `scAdd`: Aumenta a métrica &#39;Adições ao carrinho&#39;.
* `scRemove`: Aumenta a métrica &#39;Remoções do carrinho&#39;.
* `scView`: Aumenta a métrica &#39;Exibições do carrinho&#39;.
* `scCheckout`: Aumenta a métrica &quot;Finalizações&quot;.

> [!TIP] Essa variável faz distinção entre maiúsculas e minúsculas. Evite usar valores de evento com maiúsculas e minúsculas incorretas para garantir a coleta precisa de dados.

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

> [!NOTE] Os eventos contadores não suportam valores decimais ou de moeda. Use eventos de moeda para eventos de moeda ou numéricos para valores decimais.

### Usar eventos de moeda

Você pode alterar um evento personalizado para usar moeda em vez de números inteiros. Os eventos de moeda convertem automaticamente para a moeda do conjunto de relatórios se a moeda do conjunto de relatórios e a `currencyCode` variável não coincidirem. Eles são úteis para ajudar a calcular custos de envio, descontos ou reembolsos. Você pode definir eventos de moeda na `products` variável se quiser atribuir o evento somente a esse produto.

```js
// Send $9.99 USD in event1 using the events variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1=9.99";

// Send $9.99 USD in event1 using the products variable. Make sure the event type for event1 is Currency in report suite settings
s.currencyCode = "USD";
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=9.99";
```

> [!NOTE] Se você definir um valor de moeda na `events` variável e na `products` variável, o valor de moeda em `events` será usado. Evite definir valores de moeda nas variáveis `events` e `products` .

### Usar eventos numéricos

É possível alterar um evento personalizado para aceitar valores decimais em vez de números inteiros. Os eventos numéricos se comportam de forma semelhante aos eventos de moeda, exceto por não usarem a conversão de moeda. Você pode definir eventos numéricos na `products` variável se quiser atribuir o evento somente a esse produto.

```js
// Send 4.5 in event1 using the events variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1=4.5";

// Send 4.5 in event1 using the products variable. Make sure the event type for event1 is Numeric in report suite settings
s.events = "event1";
s.products = "Example category;Example product;1;0;event1=4.5";
```

> [!NOTE] Se você definir um valor numérico na `events` variável e na `products` variável, o valor numérico em `events` será usado. Evite definir valores numéricos nas variáveis `events` e `products` .
