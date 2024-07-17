---
title: cookieDomainPeriods
description: (Obsoleto) O AppMeasurement de ajuda determina onde armazenar cookies quando o domínio de nível superior de um site contém um ponto.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>Essa variável está obsoleta. Se você usar qualquer um dos seguintes:
>
>* AppMeasurement v2.26.x ou posterior
>* Extensão do Adobe Analytics v1.9.4 ou posterior
>* Serviço da Adobe Experience Cloud ID
>
>Essa variável não faz nada, pois a biblioteca aplicável detecta automaticamente o domínio no qual os cookies serão definidos.

A variável `cookieDomainPeriods` ajudou o AppMeasurement a determinar onde definir os cookies do Analytics, indicando que o domínio de nível superior tinha um ponto extra. Essa variável permitia que o AppMeasurement acomodasse o ponto extra no domínio de nível superior e definisse os cookies no local correto. Se o domínio de nível superior do site não incluir um ponto extra, essa variável não será necessária.

* Para domínios como `example.co.uk` ou `www.example.co.jp`, defina essa variável como `"3"`.
* Para domínios como `example.nsw.gov.au`, defina essa variável como `"4"`.
* Para domínios como `example.com` ou `products.example.org`, omita a configuração dessa variável ou defina-a como `"2"`.

>[!TIP]
>
>Não considere subdomínios para essa variável. Por exemplo, não defina `cookieDomainPeriods` no URL de exemplo `store.toys.example.com`. O AppMeasurement reconhece que os cookies são armazenados no `example.com`, mesmo em URLs com vários subdomínios.

Para implementações no AppMeasurement v2.26.x ou posterior, o cookie [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) é usado para ajudar a determinar automaticamente o domínio do cookie correto. A biblioteca tenta primeiro gravar um cookie, incluindo dois períodos de domínio. Se a configuração desse cookie falhar, ele tentará novamente, incluindo mais períodos de domínio até que seja bem-sucedido. Este cookie é excluído imediatamente depois de definido.

## Períodos de domínio de cookie usando o SDK da Web

O SDK da Web determina automaticamente o domínio correto para definir cookies.

## Períodos de domínio de cookie usando a extensão Adobe Analytics

**[!UICONTROL Períodos de domínio]** é um campo da opção [!UICONTROL Cookies] ao configurar a extensão do Adobe Analytics.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Cookies], que revela o campo [!UICONTROL Períodos de domínio].

Defina este campo como `3` somente em domínios de nível superior que contenham um ponto. Caso contrário, esse campo poderá ser deixado em branco.

## Períodos de domínio de cookie no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `cookieDomainPeriods` é uma cadeia de caracteres normalmente definida como `"3"`, somente em domínios de nível superior que contêm um ponto. Seu valor padrão é `"2"`, que acomoda a maioria dos domínios de nível superior, como `.com` e `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
