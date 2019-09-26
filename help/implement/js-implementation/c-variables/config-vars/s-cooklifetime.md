---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

A variável é usada pelo JavaScript e servidores de coleta de dados na determinação do tempo de vida de um cookie.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | cl | Tráfego &gt; Tecnologia &gt; Cookies Todos os relatórios relacionados ao visitante | "" |

Se *`cookieLifetime`* for definido, substituirá todas as outras expirações de cookie para JavaScript e servidores de coleta de dados, com uma exceção, descrita abaixo. The *`cookieLifetime`* variable can have one of three values:

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

Nenhuma

## Armadilhas, dúvidas e dicas

*`cookieLifetime`* affects  tracking. [!DNL Analytics] If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Tenha cuidado ao definir *`cookieLifetime`*.
