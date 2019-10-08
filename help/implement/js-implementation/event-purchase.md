---
description: Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável s.purchaseID é usada para serializar (cancelar a duplicação) um evento.
keywords: Implementação do Analytics
seo-description: Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável s.purchaseID é usada para serializar (cancelar a duplicação) um evento.
seo-title: Eventos de compra
solution: Analytics
title: Eventos de compra
topic: Desenvolvedor e implementação
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: e21bb18dd0d0eb13222c655091c3a87939a0351d

---


# Eventos de compra

Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável `s.purchaseID` é usada para serializar (cancelar a duplicação) um evento.

Se um evento de compra é chamado sem uma `purchaseID`, uma única destas é gerada automaticamente com base nas variáveis `s.products` e `s.events`. Essa ID de compra gerada automaticamente é armazenada localmente como um valor de cookie no navegador do visitante e não é enviada para a Adobe. Por outro lado, as IDs de compra definidas manualmente são enviadas para a Adobe. As cinco últimas compras feitas por um visitante (com ou sem ID de compra) são armazenadas no cookie local.

As seguintes verificações são feitas quando um visitante realiza uma compra:

* O a ID de compra corresponde a qualquer um dos cinco valores de cookie? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
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
