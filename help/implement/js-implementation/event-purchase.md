---
description: Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável s.purchaseID é usada para serializar (cancelar a duplicação) um evento.
keywords: Implementação do Analytics
seo-description: Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável s.purchaseID é usada para serializar (cancelar a duplicação) um evento.
seo-title: Eventos de compra
solution: Analytics
title: Eventos de compra
topic: Desenvolvedor e implementação
uuid: d 90 cdec 7-7397-445 a -84 e 5-31014 f 7 ff 875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Eventos de compra

Para o evento compra, as variáveis do Analytics são usadas para capturar informações específicas de compra. A variável s.purchaseID é usada para serializar (cancelar a duplicação) um evento.

The *`purchaseID`* is limited to 20 characters. A variável *`purchaseID`* serializa todos os eventos transmitidos na variável [!UICONTROL s.events] e substitui qualquer valor de serialização para eventos. If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

Se um evento de compra é chamado sem uma *`purchaseID`*, uma única destas é gerada automaticamente com base nas variáveis *`s.products`* e *`s.events`.* Esta *`purchaseID`gerada automaticamente é armazenada localmente como um valor de cookie no navegador do visitante e não é enviada para qualquer tabela de conjunto de relatório.* Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

As seguintes verificações são feitas quando um visitante realiza uma compra:

* O *`purchaseID`* corresponde a algum valor de cookie? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
* If *`purchaseID`* is defined, does it match any value in the report suite's back-end table? Neste caso, a solicitação de imagem é considerada como compra duplicada. Todas as variáveis de conversão, incluindo o evento de compra, não aparecem no relatório.
* Se *`purchaseID`* é exclusiva dos últimos 5 valores armazenados na tabela *`purchaseID`do cookie e conjunto de relatórios, a solicitação de imagem é única e incluída no relatório.* Por exemplo, se cinco compras já estiverem incluídas no cookie local, a mais antiga é substituída.

O código específico do lado do servidor pode ser usado para gerar o número exclusivo (valor alfanumérico) incorporado na fonte HTML. Em geral, a ID do pedido ou valor alfanumérico semelhante é usado para essa finalidade. Esse valor não deve ser alterado se o usuário atualizar a página. A seguir, há um curto exemplo (observe o código *`purchaseID`* em negrito):

## Sintaxe {#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## Exemplos {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## Observações adicionais {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* Assegure-se de usar o código do lado do servidor para gerar o identificador exclusivo para o evento. Não use uma função de aleatoriedade do JavaScript para gerar um número que gera números exclusivos sempre que a página for carregada (cada [!UICONTROL instância]/[!UICONTROL pageview] conta).

* Os identificadores exclusivos são aplicáveis a todos os usuários em todas as sessões. Portanto, verifique se o identificador é exclusivo entre usuários e sessões. Por exemplo, se a ID do pedido se repetir depois de 30 dias, anexe a data do pedido para tornar a [!UICONTROL ID do pedido] suficientemente exclusiva.
* O valor da serialização pode ser composto de caracteres alfanuméricos de até 20 caracteres de tamanho. Essa limitação é idêntica às limitações de [!UICONTROL s.purchaseID] (substitua s. por s_ no código G).
* A variável [!UICONTROL s.purchaseID] serializa todos os eventos transmitidos na variável [!UICONTROL s.events] e substitui qualquer valor de serialização para eventos. Não use a [!UICONTROL serialização de eventos] para os eventos se a variável [!UICONTROL s.purchaseID] estiver sendo usada na página atual (substitua s. por s_ para código G).

