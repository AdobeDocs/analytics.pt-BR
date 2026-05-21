---
title: Evento de compra
description: Use o evento de compra para coletar dados das métricas "Pedidos", "Unidades" e "Receita".
feature: Appmeasurement Implementation
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
TQID: https://experienceleague.adobe.com/r-L330P6HA5qWBmEW-2LwECo-d3dhVK1ovWsfraErXE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 66%

---

# Evento de compra

O evento de compra é um valor na variável `events`. Esse valor é útil para organizações que desejam coletar dados sobre a receita gerada pelo site. É altamente dependente das variáveis [`products`](../products.md) e [`purchaseID`](../purchaseid.md).

Quando você define um evento de compra, ele afeta as seguintes métricas:

* A métrica &quot;Pedidos&quot; é incrementada em 1
* A métrica &quot;Unidades&quot; é incrementada pelo número de produtos na variável `products`
* A métrica &quot;Receita&quot; é incrementada com a soma dos parâmetros de preço na variável `products`

>[!NOTE]
>
>A receita não é multiplicada pelo campo de quantidade. Por exemplo, `s.products="Womens;Socks;5;4.50"` não passa US$ 22,50 para o relatório, mas sim US$ 4,50. Certifique-se de que sua implementação passe a receita total para a quantidade listada. Por exemplo, `s.products="Womens;Socks;5;22.50"`.

## Definir o evento de compra usando o Web SDK

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), o evento de compra usará os seguintes campos XDM:

* Os pedidos são mapeados para `xdm.commerce.purchases.value`.
* As unidades são mapeadas para a soma de todos os campos `xdm.productListItems[].quantity`. Consulte [`products`](../products.md) para obter mais informações.
* A receita é mapeada para a soma de todos os campos `xdm.productListItems[].priceTotal`.

```json
{
  "xdm": {
    "commerce": {
      "purchases": {
        "value": 1
      }
    }
  }
}
```

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), o evento de compra usará `data.__adobe.analytics.events`, seguindo a sintaxe da cadeia de caracteres do AppMeasurement.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "events": "purchase"
      }
    }
  }
}
```

## Definir o evento de compra usando a extensão do Adobe Analytics

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos] e defina a lista suspensa [!UICONTROL Eventos] como [!UICONTROL compra].

Outras variáveis dependentes, como `products` e `purchaseID`, não têm campos dedicados na extensão do Analytics dentro da Coleção de dados da Adobe Experience Platform. Use o editor de código personalizado siga a sintaxe do AppMeasurement para essas variáveis.

## Definir o evento de compra no AppMeasurement e no editor de código personalizado da extensão do Analytics

O evento de compra é uma string definida como parte da variável de eventos.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Desduplicação de eventos de compra

Quando você dispara um evento de compra, a Adobe verifica o seguinte:

* A ocorrência contém a variável `purchaseID`? Caso não tenha, a Adobe usa informações da ocorrência para criar uma &quot;ID de compra temporária&quot;. Essa ID de compra temporária se aplica somente ao visitante da ocorrência. As 5 IDs de compra temporárias anteriores são armazenadas para cada ID de visitante por conjunto de relatórios.
* A ID de compra temporária corresponde a qualquer uma das cinco últimas IDs de compra temporárias armazenadas? Em caso afirmativo, a solicitação de imagem é considerada uma compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
* Se a variável `purchaseID` estiver definida, ela corresponderá a qualquer valor já coletado no conjunto de relatórios para todos os visitantes? Em caso afirmativo, a solicitação de imagem é considerada uma compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
