---
description: Saiba mais sobre a variável purchaseID, que ajuda a impedir que compras duplicadas apareçam no Adobe Analytics.
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

Quando um visitante compra um item de seu site, ele `purchaseID` é preenchido na página "Obrigado" ou "Confirmação de pedido". Defina a `purchaseID` variável ao mesmo tempo em que um evento de compra é acionado. Quando `purchaseID` é definido como um valor exclusivo, os valores da variável de conversão contam somente para a ocorrência com essa ID de compra exclusiva. A definição do item `purchaseID` é importante, pois os visitantes geralmente marcam uma página de confirmação de compra para seus próprios fins. Se sua implementação não for usada `purchaseID`, os dados de conversão (como receita) podem ser inflados facilmente pelos visitantes que atualizam as páginas.

Além dos dados de compra, todas as variáveis e eventos de conversão não são contados várias vezes para ocorrências com a mesma ID de compra.

## Sintaxe

A `purchaseID` variável pode conter qualquer valor alfanumérico, até um máximo de 20 bytes. Se você definir uma ID de compra maior que 20 bytes, o valor será truncado.

```js
s.purchaseID = "uniqueid";
```
