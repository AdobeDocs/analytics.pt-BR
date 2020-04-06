---
title: visitorID
description: Use uma ID de visitante personalizada.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# visitorID

A Adobe usa vários métodos diferentes para identificar visitantes em seu site. A variável `visitorID` substitui todos os outros métodos de identificação de visitantes.

>[!IMPORTANT] A Adobe recomenda não usar essa variável. Em vez disso, use o [Serviço de Identidade da Adobe Experience Cloud](https://docs.adobe.com/content/help/pt-BR/id-service/using/home.html).

## ID de visitante no Adobe Experience Platform Launch

[!UICONTROL Visitor ID] é um campo sob o [!UICONTROL Cookies] acordeão ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL Cookies] acordeão, que revela o [!UICONTROL Visitor ID] campo.

Atribua esse campo ao elemento de dados que contém sua ID de visitante personalizada. Não defina esse campo como um valor estático.

## s.visitorID no AppMeasurement e no editor de código personalizado do Launch

A variável `s.visitorID` é uma string que contém um identificador exclusivo personalizado para o visitante. Valores válidos incluem caracteres alfanuméricos de até 100 bytes. Evite usar traços, espaços, sublinhados ou símbolos nessa variável.

>[!WARNING] Se você definir a variável `visitorID` durante uma visita, os dados resultarão em dois visitantes únicos separados.

```js
s.visitorID = "abc123";
```
