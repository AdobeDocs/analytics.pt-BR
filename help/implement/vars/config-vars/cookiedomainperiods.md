---
title: cookieDomainPeriods
description: Ajude o AppMeasurement a entender que domínio armazenar cookies se o domínio tiver um período em seu sufixo.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

O AppMeasurement determina a localização do cookie observando o domínio e o sufixo do domínio. Para domínios como `example.com`, o AppMeasurement define cookies no local correto. No entanto, para outros domínios como `example.co.uk`, o AppMeasurement pode definir cookies por engano `co.uk`. A maioria dos navegadores rejeita cookies definidos nesse domínio inválido, causando problemas com a identificação do visitante.

A `cookieDomainPeriods` variável ajuda o AppMeasurement a determinar onde os cookies do Analytics são definidos, chamando para que o sufixo do domínio tenha um período extra. Essa variável permite que o AppMeasurement acomode o período extra no sufixo do domínio e defina os cookies no local correto.

* Para domínios como `example.com` ou `www.example.com`, essa variável não precisa ser definida. Se necessário, é possível definir essa variável como `"2"`.
* Para domínios como `example.co.uk` ou `www.example.co.jp`, defina essa variável como `"3"`.

> [!IMPORTANT] Não leve subdomínios em conta para essa variável. Por exemplo, não defina `cookieDomainPeriods` o URL de exemplo `store.toys.example.com`. O AppMeasurement por padrão reconhece que os cookies devem ser armazenados `example.com`, mesmo em URLs com vários subdomínios.

## Períodos de domínio no lançamento da plataforma Adobe Experience

Períodos de domínio é um campo sob a opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Cookies] , que revela o campo Períodos  de Domínio.

Defina esse campo como `3` somente em domínios que contenham um período em seu sufixo. Caso contrário, esse campo poderá ser deixado em branco.

## s.cookieDomainPeriods no AppMeasurement e Iniciar editor de código personalizado

A `cookieDomainPeriods` variável é uma string normalmente definida como `"3"`, somente em domínios que contêm um ponto em seu sufixo. Seu valor padrão é `"2"`, que acomoda a maioria dos domínios.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
