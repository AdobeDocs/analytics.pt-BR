---
title: fpcookieDomainPeriods
description: Ajude o AppMeasurement a entender em qual domínio armazenar cookies se o domínio tiver um ponto no sufixo.
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 86%

---

# fpCookieDomainPeriods

A variável `fpCookieDomainPeriods` ajuda o AppMeasurement a determinar onde os cookies do Analytics são definidos, indicando que o sufixo do domínio tem um ponto extra. Essa variável permite que o AppMeasurement acomode o ponto extra no sufixo do domínio e defina os cookies no local correto. Ela herda o valor de [`cookieDomainPeriods`](cookiedomainperiods.md), mas ainda é uma prática recomendada a ser definida se você usar uma implementação de cookie primário.

* Em domínios como `example.com` ou `www.example.com`, essa variável não precisa ser definida. Se necessário, é possível definir essa variável como `"2"`.
* Para domínios como `example.co.uk` ou `www.example.co.jp`, defina essa variável como `"3"`.

>[!IMPORTANT]
>
>Não considere subdomínios para essa variável. Por exemplo, não defina `fpCookieDomainPeriods` no URL de exemplo `store.toys.example.com`. O AppMeasurement reconhece por padrão que os cookies devem ser armazenados no `example.com`, mesmo em URLs com vários subdomínios.

## Períodos de domínio primários usando o SDK da Web

O SDK da Web pode determinar o domínio de armazenamento de cookies correto sem essa variável.

## Períodos de domínio primários usando a extensão do Adobe Analytics

Pontos de domínio primários é um campo da opção [!UICONTROL Cookies] ao configurar a extensão Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
4. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL Períodos de domínio primários].

Defina esse campo como `3` somente em domínios que contenham um ponto no sufixo. Caso contrário, esse campo poderá ser deixado em branco.

## s.fpCookieDomainPeriods no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `fpCookieDomainPeriods` é uma cadeia de caracteres normalmente definida como `"3"`, somente em domínios que contêm um ponto no sufixo. Seu valor padrão é `"2"`, que acomoda a maioria dos domínios.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
