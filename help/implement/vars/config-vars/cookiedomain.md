---
title: cookieDomain
description: A variável cookieDomain ajuda a determinar o domínio no qual os cookies serão definidos.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# cookieDomain

> [!IMPORTANT] Essa variável é removida. Use `trackingServer` em vez disso.

A `cookieDomain` variável determina o domínio no qual o AppMeasurement define cookies. Você pode usar essa variável para definir explicitamente o domínio do cookie em vez de usar a `cookieDomainPeriods` variável.

Essa variável só precisa ser usada quando **ambas** as condições a seguir forem atendidas:

* Se sua implementação usar cookies primários. Essa variável não é necessária com implementações que usam um `trackingServer` valor que contém `sc.omtrdc.net`.
* Se o domínio tiver um período no sufixo. Por exemplo, `example.co.uk` poderia usar a variável `cookieDomain` para indicar explicitamente que o domínio do cookie é `example.co.uk` e não `co.uk`.

Somente um pequeno número de implementações tem sido usado para a `cookieDomain` variável e, mesmo assim, variáveis alternativas como `cookieDomainPeriods` podem ser usadas.

## Domínio de cookie no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.cookieDomain no AppMeasurement e Iniciar editor de código personalizado

A `cookieDomain` variável é uma string e é definida como o domínio no qual você deseja armazenar cookies.

```js
s.cookieDomain = "stats.example.com";
```
