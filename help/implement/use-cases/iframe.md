---
title: Usar o AppMeasurement com iframes
description: Acesse as variáveis do Adobe Analytics dentro de um iframe ou página pai enquanto estiver em um iframe.
translation-type: tm+mt
source-git-commit: 355985a6baa1a1112e75446012be72f5c0a1d0c2
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---


# Usar o AppMeasurement com iframes

Você pode fazer referência às variáveis do AppMeasurement de iframes filho e pai. É necessário definir todas as variáveis no mesmo local em que a biblioteca do AppMeasurement existe. Os exemplos a seguir explicam como definir variáveis e métodos básicos do AppMeasurement dentro e fora de um iframe.

Se você usar o Adobe Experience Platform Launch, verifique se o objeto de rastreamento está acessível globalmente. Consulte Visão geral [da extensão do](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) Adobe Analytics no guia do usuário do Launch.

>!![CAUTION]
Evite incluir bibliotecas do AppMeasurement em uma página pai e em um iframe. Isso apresenta riscos ao enviar várias solicitações de imagem, inflando os relatórios e aumentando as chamadas faturáveis do servidor.

## Acessar o AppMeasurement que reside em um iframe

Você pode acessar as variáveis do AppMeasurement pelo objeto iframe. Esses exemplos definem [pageName](../vars/page-vars/pagename.md) e chamam o método [](../vars/functions/t-method.md) t() usando duas maneiras diferentes para referenciar o objeto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Acessar o AppMeasurement de dentro de um iframe

Você pode acessar as variáveis do AppMeasurement em uma página pai a partir de um iframe. Este exemplo define [pageName](../vars/page-vars/pagename.md) e chama o método [](../vars/functions/t-method.md) t() usando a [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) propriedade.

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Uso `postMessage` e ouvintes de evento

Como alternativa, você pode usar ouvintes de `postMessage` evento e de tela para definir variáveis. Este método não requer uma referência direta a um iframe.

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## Limitações

* Assim como com outro código JavaScript, o iframes só pode se comunicar quando os domínios e o protocolo correspondem. Estes exemplos não funcionam se o conteúdo do iframe reside em um domínio diferente do principal.
* Se o AppMeasurement residir em um iframe, a [`referrer`](../vars/page-vars/referrer.md) variável será definida como o URL pai, não como o URL de referência real. É possível definir manualmente a `referrer` variável para resolver esse problema.
* O depurador [do](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html) Adobe Experience Cloud não reconhece solicitações de imagem acionadas em iframes.
* Activity Map não exibe o mapa de calor sobre links clicados em iframes. Em vez disso, todo o iframe é realçado.
