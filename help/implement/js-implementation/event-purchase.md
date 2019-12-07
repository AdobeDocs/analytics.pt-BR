---
description: Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável s.purchaseID é usada para serializar (cancelar a duplicação) um evento.
keywords: Analytics Implementation
title: Eventos de compra
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Eventos de compra

Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável `s.purchaseID` é usada para serializar (cancelar a duplicação) um evento.

Se uma ocorrência com um evento de compra for transmitida sem uma ID de compra, o Adobe Analytics usará as informações da ocorrência (s.purchase e s.events) para criar uma "ID de compra temporária". Essa ID de compra temporária se aplica somente ao visitante da ocorrência. As 5 IDs de compra temporárias anteriores são armazenadas para cada ID de visitante (por conjunto de relatórios).

As seguintes verificações são feitas quando um visitante realiza uma compra:

* O a ID de compra temporária corresponde a qualquer uma das cinco últimas IDs de compra temporárias armazenadas? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
* Se `s.purchaseID` estiver definido, ele corresponde a algum valor já coletado no conjunto de relatórios? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.

O código específico do lado do servidor pode ser usado para gerar o número exclusivo (valor alfanumérico) incorporado na fonte HTML. Em geral, a ID do pedido ou valor alfanumérico semelhante é usado para essa finalidade. Esse valor não deve ser alterado se o usuário atualizar a página.

## Sintaxe

```js
s.purchaseID="12345678";
```

## Exemplos

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## Observações adicionais

* Não use uma função de aleatoriedade do JavaScript para gerar um número, que gera números exclusivos sempre que a página é carregada. A Adobe recomenda usar uma camada de dados para armazenar uma determinada ID de compra.
* Os identificadores exclusivos são aplicáveis a todos os usuários em todas as sessões. Certifique-se de que todas as IDs de compra sejam realmente únicas.
* Valores válidos são valores alfanuméricos de até 20 caracteres.
* A variável `s.purchaseID``s.events` serializa todos os eventos transmitidos na variável   e substitui qualquer valor de serialização para eventos. Não use a serialização [!UICONTROL de] eventos para nenhum evento se a `s.purchaseID` variável for usada na página atual.
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
