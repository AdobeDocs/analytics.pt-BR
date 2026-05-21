---
title: bufferRequests
description: Aumente a confiabilidade de capturar solicitações de rastreamento de link para navegadores que descarregam imediatamente a página.
feature: Appmeasurement Implementation
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
TQID: https://experienceleague.adobe.com/HJdo1hCpisjHdOaTi8OP2tWSP2yAftEqfkCNXycFcrM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 7%

---

# bufferRequests

O método `bufferRequests()` permite armazenar solicitações de imagem em cache na página atual, em vez de enviá-las para a Adobe. O acionamento deste método é útil em cenários nos quais um navegador não oferece suporte a [`navigator.sendBeacon()`](https://developer.mozilla.org/pt-BR/docs/Web/API/Navigator/sendBeacon) ou cancela solicitações de imagem quando uma página é descarregada. Muitas versões dos navegadores WebKit, como o Safari, geralmente exibem o comportamento de interromper uma solicitação de imagem ao clicar em um link. O método `bufferRequests()` está disponível em todas as versões do AppMeasurement v2.25.0 ou posterior.

Quando você chama [`t()`](t-method.md) ou [`tl()`](tl-method.md) em uma página subsequente na mesma sessão do navegador e `bufferRequests()` ainda não foi chamado nessa página, todas as solicitações em buffer são enviadas além da solicitação de imagem dessa página. As solicitações em buffer são enviadas na ordem correta, sendo que a solicitação de imagem da página atual é enviada por último.

>[!TIP]
>
>O carimbo de data e hora das solicitações em buffer é compartilhado com a página para a qual os dados são enviados. Se quiser obter mais precisão no segundo exato em que uma solicitação armazenada em buffer for registrada, você poderá definir a variável de página [`timestamp`](../page-vars/timestamp.md) antes de armazenar a solicitação em buffer. Se você usar essa variável, verifique se [Os carimbos opcionais de data e hora](/help/admin/tools/manage-rs/edit-settings/general/timestamp-configuration.md) estão habilitados. Caso contrário, todas as ocorrências com carimbos de data e hora serão perdidas permanentemente!

## Limitações

Ao chamar o método `bufferRequests()`, lembre-se das limitações a seguir. Como este método usa [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), muitas das mesmas limitações se aplicam:

* O link de destino deve residir no mesmo domínio e subdomínio. As solicitações em buffer não funcionam entre domínios ou subdomínios, mesmo se ambos tiverem a mesma implementação do Adobe Analytics. Essa limitação também significa que não é possível usar solicitações em buffer para rastrear links de saída.
* O link de destino deve usar o mesmo protocolo da página atual. Não é possível enviar solicitações em buffer entre HTTP e HTTPS.
* As solicitações armazenadas em buffer são armazenadas até que você chame `t()` ou `tl()` sem chamar `bufferRequests()` primeiro ou até que o navegador ou a guia seja fechada. Se uma sessão do navegador terminar antes que você possa enviar esses dados para o Adobe, as solicitações em buffer não enviadas serão perdidas permanentemente.
* Se um navegador não oferecer suporte à [API de Armazenamento da Web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) ou à [API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), um aviso será exibido para o console do navegador e a AppMeasurement tentará enviar imediatamente a solicitação de imagem usando o método `t()`.

## Solicitações em buffer no Web SDK

No momento, o Web SDK não oferece a capacidade de armazenar solicitações em buffer.

## Solicitações em buffer usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.bufferRequests() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `bufferRequests()` antes de chamar `t()` ou `tl()`. Quando `bufferRequests()` é chamado, as chamadas de rastreamento subsequentes são gravadas no armazenamento da sessão em vez de enviadas para os servidores de coleta de dados da Adobe.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```
