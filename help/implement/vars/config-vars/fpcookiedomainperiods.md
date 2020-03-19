---
title: cookieDomainPeriods
description: Ajude o AppMeasurement a entender que domínio armazenar cookies se o domínio tiver um período em seu sufixo.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# fpCookieDomainPeriods

A `fpCookieDomainPeriods` variável ajuda o AppMeasurement a determinar onde os cookies do Analytics são definidos, chamando para que o sufixo do domínio tenha um período extra. Essa variável permite que o AppMeasurement acomode o período extra no sufixo do domínio e defina os cookies no local correto. Ele herda o valor de [`cookieDomainPeriods`](cookiedomainperiods.md), mas ainda é uma prática recomendada a ser definida se você usar uma implementação de cookie primário.

* Para domínios como `example.com` ou `www.example.com`, essa variável não precisa ser definida. Se necessário, é possível definir essa variável como `"2"`.
* Para domínios como `example.co.uk` ou `www.example.co.jp`, defina essa variável como `"3"`.

> [!IMPORTANT] Não leve subdomínios em conta para essa variável. Por exemplo, não defina `fpCookieDomainPeriods` o URL de exemplo `store.toys.example.com`. O AppMeasurement por padrão reconhece que os cookies devem ser armazenados `example.com`, mesmo em URLs com vários subdomínios.

## Períodos de domínio primários no lançamento da plataforma Adobe Experience

Períodos de domínio primários é um campo sob o [!UICONTROL Cookies] acordeão ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá para a [!UICONTROL Extensions] guia e clique no [!UICONTROL Configure] botão em Adobe Analytics.
4. Amplie o [!UICONTROL Cookies] acordeão, que revela o [!UICONTROL First-party Domain Periods] campo.

Defina esse campo como `3` somente em domínios que contenham um período em seu sufixo. Caso contrário, esse campo poderá ser deixado em branco.

## s.fpCookieDomainPeriods no AppMeasurement e Iniciar editor de código personalizado

A `fpCookieDomainPeriods` variável é uma string normalmente definida como `"3"`, somente em domínios que contêm um ponto em seu sufixo. Seu valor padrão é `"2"`, que acomoda a maioria dos domínios.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
