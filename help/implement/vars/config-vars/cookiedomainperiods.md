---
title: cookieDomainPeriods
description: Ajude o AppMeasurement a entender em qual domínio armazenar cookies se o domínio tiver um ponto no sufixo.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# cookieDomainPeriods

O AppMeasurement determina a localização do cookie observando o domínio e seu sufixo. Para domínios como `example.com`, o AppMeasurement define cookies no local correto. No entanto, em outros domínios como o `example.co.uk`, o AppMeasurement pode definir cookies por engano no `co.uk`. A maioria dos navegadores rejeita cookies definidos nesse domínio inválido, causando problemas com a identificação do visitante.

A variável `cookieDomainPeriods` ajuda o AppMeasurement a determinar onde os cookies do Analytics são definidos, indicando que o sufixo do domínio tem um ponto extra. Essa variável permite que o AppMeasurement acomode o ponto extra no sufixo do domínio e defina os cookies no local correto.

* Para domínios como `example.com` ou `www.example.com`, essa variável não precisa ser definida. Se necessário, é possível definir essa variável como `"2"`.
* Para domínios como `example.co.uk` ou `www.example.co.jp`, defina essa variável como `"3"`.

>[!IMPORTANT] Não considere subdomínios para essa variável. Por exemplo, não defina `cookieDomainPeriods` no URL de exemplo `store.toys.example.com`. O AppMeasurement reconhece por padrão que os cookies devem ser armazenados no `example.com`, mesmo em URLs com vários subdomínios.

## Períodos de domínio no Adobe Experience Platform Launch

Pontos de domínio é um campo da opção [!UICONTROL Cookies] ao configurar a extensão Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Amplie o [!UICONTROL Cookies] acordeão, que revela o [!UICONTROL Domain Periods] campo.

Defina esse campo como `3` somente em domínios que contenham um ponto no sufixo. Caso contrário, esse campo poderá ser deixado em branco.

## s.cookieDomainPeriods no AppMeasurement e no editor de código personalizado do Launch

A variável `cookieDomainPeriods` é uma cadeia de caracteres normalmente definida como `"3"`, somente em domínios que contêm um ponto no sufixo. Seu valor padrão é `"2"`, que acomoda a maioria dos domínios.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
