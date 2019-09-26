---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieDomain

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly,  is used to generate  from . `s.cookieDomainPeriods``s.cookieDomain``window.location.hostname` Instead of using , you can explicitly set  to what you want to use in your implementation. `s.cookieDomainPeriods``s.cookieDomain` Por exemplo, você pode definir cookies no nome da página totalmente qualificado usando:

`s.cookieDomain = window.location.hostname;`
