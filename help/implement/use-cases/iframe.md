---
title: Usar o AppMeasurement com iFrames
description: Acesse as variáveis do Adobe Analytics dentro de um iframe ou de uma página principal em um iframe.
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: 40bf2bbb522a94a678d0da1a645d83a5121c93d0
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 100%

---

# Usar o AppMeasurement com iFrames

Você pode fazer referência às variáveis do AppMeasurement de iFrames filhos e pais. É necessário definir todas as variáveis no mesmo local em que a biblioteca do AppMeasurement existe. Os exemplos a seguir explicam como definir variáveis e métodos básicos do AppMeasurement dentro e fora de um iframe.

Se você usar o Adobe Experience Platform Launch, verifique se o objeto do rastreador está acessível globalmente. Consulte [Visão geral da extensão do Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) no guia do usuário do Launch.

>[!CAUTION]
>
>Evite incluir bibliotecas do AppMeasurement em uma página principal e em um iframe. Isso apresenta riscos ao envio de várias solicitações de imagem, inflando relatórios e aumentando chamadas de servidor faturáveis.

## Acessar o AppMeasurement localizado em um iframe

Você pode acessar variáveis do AppMeasurement por meio do objeto iframe. Esses exemplos definem [pageName](../vars/page-vars/pagename.md) e chamam o método [t()](../vars/functions/t-method.md) usando duas maneiras diferentes para fazer referência ao objeto do iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Acessar o AppMeasurement de dentro de um iframe

Você pode acessar variáveis do AppMeasurement em uma página principal por meio de um iframe. Este exemplo define [pageName](../vars/page-vars/pagename.md) e chama o método [t()](../vars/functions/t-method.md) usando a propriedade [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Usar `postMessage` e ouvintes de eventos

Como alternativa, você pode usar `postMessage` e ouvintes de eventos para definir variáveis. Este método não exige uma referência direta a um iframe.

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

* Assim como em outro código JavaScript, os iFrames só podem se comunicar quando os domínios e o protocolo são correspondentes. Esses exemplos não funcionam se o conteúdo do iframe estiver em um domínio diferente do principal.
* Se o AppMeasurement estiver em um iframe, a variável [`referrer`](../vars/page-vars/referrer.md) será definida como o URL principal, não como o URL de referência real. Você pode definir manualmente a variável `referrer` para resolver esse problema.
* O [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/pt-BR/debugger/using/experience-cloud-debugger.html) não reconhece solicitações de imagem acionadas em iFrames.
* O Activity Map não exibe o mapa de calor em links clicados em iFrames. Em vez disso, o iframe inteiro é realçado.
