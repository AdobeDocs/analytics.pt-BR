---
title: bufferRequests
description: Aumente a confiabilidade de capturar solicitações de rastreamento de link para navegadores que descarregam imediatamente a página.
feature: Variables
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# bufferRequests

O método `bufferRequests()` permite armazenar solicitações de imagem em cache na página atual, em vez de enviá-las para o Adobe. O acionamento deste método é útil em cenários nos quais um navegador não oferece suporte a [`navigator.sendBeacon()`](https://developer.mozilla.org/pt-BR/docs/Web/API/Navigator/sendBeacon) ou cancela solicitações de imagem quando uma página é descarregada. Muitas versões dos navegadores WebKit, como o Safari, geralmente exibem o comportamento de interromper uma solicitação de imagem ao clicar em um link. O método `bufferRequests()` está disponível em todas as versões do AppMeasurement v2.25.0 ou posterior.

Quando você chama [`t()`](t-method.md) ou [`tl()`](tl-method.md) em uma página subsequente na mesma sessão do navegador e `bufferRequests()` ainda não foi chamado nessa página, todas as solicitações em buffer são enviadas além da solicitação de imagem dessa página. As solicitações em buffer são enviadas na ordem correta, sendo que a solicitação de imagem da página atual é enviada por último.

>[!TIP]
>
>O carimbo de data e hora das solicitações em buffer é compartilhado com a página para a qual os dados são enviados. Se quiser obter mais precisão no segundo exato em que uma solicitação armazenada em buffer for registrada, você poderá definir a variável de página [`timestamp`](../page-vars/timestamp.md) antes de armazenar a solicitação em buffer. Se você usar essa variável, verifique se [Os carimbos opcionais de data e hora](/help/technotes/timestamps-optional.md) estão habilitados. Caso contrário, todas as ocorrências com carimbos de data e hora serão perdidas permanentemente!

## Limitações

Ao chamar o método `bufferRequests()`, lembre-se das limitações a seguir. Como este método usa [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), muitas das mesmas limitações se aplicam:

* O link de destino deve residir no mesmo domínio e subdomínio. As solicitações em buffer não funcionam entre domínios ou subdomínios, mesmo se ambos tiverem a mesma implementação do Adobe Analytics. Essa limitação também significa que não é possível usar solicitações em buffer para rastrear links de saída.
* O link de destino deve usar o mesmo protocolo da página atual. Não é possível enviar solicitações em buffer entre HTTP e HTTPS.
* As solicitações armazenadas em buffer são armazenadas até que você chame `t()` ou `tl()` sem chamar `bufferRequests()` primeiro ou até que o navegador ou a guia seja fechada. Se uma sessão do navegador terminar antes que você possa enviar esses dados para o Adobe, as solicitações em buffer não enviadas serão perdidas permanentemente.
* Se um navegador não oferecer suporte à [API de Armazenamento da Web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) ou à [API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), um aviso será exibido para o console do navegador e o AppMeasurement tentará enviar imediatamente a solicitação de imagem usando o método `t()`.

## Solicitações em buffer no SDK da Web

No momento, o SDK da Web não oferece a capacidade de armazenar solicitações em buffer.

## Solicitações em buffer usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.bufferRequests() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `bufferRequests()` antes de chamar `t()` ou `tl()`. Quando `bufferRequests()` é chamado, as chamadas de rastreamento subsequentes são gravadas no armazenamento da sessão em vez de enviadas para os servidores de coleta de dados do Adobe.

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
