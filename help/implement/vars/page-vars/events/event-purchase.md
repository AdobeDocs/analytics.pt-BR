---
title: Evento de compra
description: Use o evento de compra para coletar dados das métricas "Pedidos", "Unidades" e "Receita".
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Evento de compra

O evento de compra é um valor na variável `events`. Esse valor é útil para organizações que desejam coletar dados sobre a receita gerada pelo site. É altamente dependente das variáveis [`products`](../products.md) e [`purchaseID`](../purchaseid.md).

Quando você define um evento de compra, ele afeta as seguintes métricas:

* A métrica &quot;Pedidos&quot; é incrementada em 1
* A métrica &quot;Unidades&quot; é incrementada pelo número de produtos na variável `products`
* A métrica &quot;Receita&quot; é incrementada com a soma dos parâmetros de preço na variável `products`

## Definir o evento de compra no Adobe Experience Platform Launch

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos] e selecione [!UICONTROL compra] na lista suspensa de eventos.

Outras variáveis dependentes, como `products` e `purchaseID`, não têm campos dedicados no Launch. Use o editor de código personalizado siga a sintaxe do AppMeasurement para essas variáveis.

## Definir o evento de compra no AppMeasurement e no editor de código personalizado do Launch

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
