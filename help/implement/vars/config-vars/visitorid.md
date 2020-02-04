---
title: visitorID
description: Use uma ID de visitante personalizada.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorID

A Adobe usa vários métodos diferentes para identificar visitantes em seu site. A `visitorID` variável substitui todos os outros métodos de identificação do visitante.

> [!IMPORTANT] A Adobe recomenda não usar essa variável. Em vez disso, use o Serviço [de identidade da](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud.

## ID de visitante no Adobe Experience Platform Launch

[!UICONTROL A ID] do visitante é um campo sob a opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Cookies] , que revela o campo ID [!UICONTROL do] visitante.

Atribua esse campo ao elemento de dados que contém sua ID de visitante personalizada. Não defina esse campo para um valor estático.

## s.visitorID no AppMeasurement e no editor de código personalizado Iniciar

A `s.visitorID` variável é uma string que contém um identificador exclusivo personalizado para o visitante. Valores válidos incluem caracteres alfanuméricos de até 100 bytes. Evite usar traços, espaços, sublinhados ou símbolos nessa variável.

> [!WARNING] Se você definir a parte da `visitorID` variável por uma visita, os dados resultarão em dois visitantes únicos separados.

```js
s.visitorID = "abc123";
```
