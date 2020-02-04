---
title: Evento de compra
description: Use o evento purchase para coletar dados das métricas "Pedidos", "Unidades" e "Receita".
translation-type: tm+mt
source-git-commit: 7a1c3c7ed0e509969e281e865e8ff2c969a18bcb

---


# Evento de compra

O evento purchase é um valor na `events` variável. Esse valor é útil para organizações que desejam coletar dados sobre a receita gerada pelo site. É altamente dependente das variáveis `products` e `purchaseID` .

Quando você define um evento de compra, ele afeta as seguintes métricas:

* A métrica &quot;Pedidos&quot; é incrementada em 1
* A métrica &quot;Unidades&quot; é incrementada pelo número de produtos na `products` variável
* A métrica &#39;Receita&#39; aumenta pela soma dos parâmetros de preço na `products` variável

## Definir o evento de compra no Adobe Experience Platform Launch

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL Eventos] e defina os eventos como [!UICONTROL compra].

Outras variáveis dependentes, como `products` e `purchaseID` , não têm campos dedicados no Launch. Use o editor de código personalizado após a sintaxe do AppMeasurement para essas variáveis.

## Definir o evento de compra no editor de código personalizado AppMeasurement e Launch

O evento purchase é uma string definida como parte da variável events.

```js
// Set the purchase event by itself
s.events = "purchase";

// Set the purchase event alongside other events
s.events = "purchase,event1,event2";
```

## Eliminação da duplicação de eventos de compra

Quando você dispara um evento de compra, a Adobe verifica o seguinte:

* A ocorrência contém a `purchaseID` variável? Caso contrário, a Adobe usa informações da ocorrência para criar uma &quot;ID de compra temporária&quot;. Essa ID de compra temporária se aplica somente ao visitante da ocorrência. As 5 IDs de compra temporárias anteriores são armazenadas para cada ID de visitante por conjunto de relatórios.
* A ID de compra temporária corresponde a qualquer uma das cinco últimas IDs de compra temporárias armazenadas? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
* Se a `purchaseID` variável estiver definida, ela corresponderá a qualquer valor já coletado no conjunto de relatórios em todos os visitantes? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
