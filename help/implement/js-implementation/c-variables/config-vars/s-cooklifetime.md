---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieLifetime

A variável é usada pelo JavaScript e servidores de coleta de dados na determinação do tempo de vida de um cookie.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | cl | Tráfego &gt; Tecnologia &gt; Cookies Todos os relatórios relacionados ao visitante | "" |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. A variável *`cookieLifetime`* pode ter um destes três valores:

* [!DNL Analytics] Cookies
* Cookies
* Configurações e plug-ins de JavaScript

## Sintaxe e valores possíveis

```js
s.cookieLifetime="value"
```

Os valores possíveis são listados como a seguir:

* ""
* "NONE"
* "SESSION"
* Um inteiro representando o número de segundos até a expiração

## Exemplos

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

O *`cookieLifetime`* afeta o rastreamento de [!DNL Analytics]. Se, por exemplo, *`cookieLifetime`* for dois dias, os relatórios mensais, trimestrais e anuais exclusivos do visitante estarão incorretos. Tenha cuidado ao definir *`cookieLifetime`*.
