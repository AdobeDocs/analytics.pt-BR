---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieDomain

A variável determina o domínio em que os [!DNL Analytics] cookies `s_cc` e `s_sq` são definidos.

Geralmente, `s.cookieDomainPeriods` é usado para gerar `s.cookieDomain` de `window.location.hostname`. Em vez de usar `s.cookieDomainPeriods`, você pode definir explicitamente o `s.cookieDomain` para aquilo que deseja usar na implementação. Por exemplo, você pode definir cookies no nome da página totalmente qualificado usando:

`s.cookieDomain = window.location.hostname;`
