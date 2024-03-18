---
title: Evento de compra
description: Use o evento de compra para coletar dados das métricas "Pedidos", "Unidades" e "Receita".
feature: Variables
exl-id: 5ad148d6-cf45-4dea-846a-255004300bc2
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 72%

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

## Definir o evento de compra usando o SDK da Web

Se estiver usando o [**Objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), o evento de compra usa os seguintes campos XDM:

* Os pedidos são mapeados para `xdm.commerce.purchases.value`.
* As unidades são mapeadas para a soma de todos os campos `xdm.productListItems[].quantity`.
* A receita é mapeada para a soma de todos os campos `xdm.productListItems[].priceTotal`.

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), o evento de compra usa `data.__adobe.analytics.events`, seguindo a sintaxe da string de AppMeasurement.

## Definir o evento de compra usando a extensão do Adobe Analytics

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina o [!UICONTROL Extensão] para o Adobe Analytics e a caixa de diálogo [!UICONTROL Tipo de ação] para [!UICONTROL Definir variáveis].
6. Localize o [!UICONTROL Eventos] e defina o [!UICONTROL Eventos] lista suspensa para [!UICONTROL compra].

Outras variáveis dependentes, como `products` e `purchaseID` não têm campos dedicados na extensão Analytics dentro da Coleção de dados da Adobe Experience Platform. Use o editor de código personalizado siga a sintaxe do AppMeasurement para essas variáveis.

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
* A ID de compra temporária corresponde a qualquer uma das cinco últimas IDs de compra temporárias armazenadas? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
* Se a variável `purchaseID` estiver definida, ela corresponderá a qualquer valor já coletado no conjunto de relatórios para todos os visitantes? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
