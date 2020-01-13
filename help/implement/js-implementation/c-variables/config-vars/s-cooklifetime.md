---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieLifetime

A variável é usada pelo JavaScript e servidores de coleta de dados na determinação do tempo de vida de um cookie.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | cl | Tráfego &gt; Tecnologia &gt; Cookies Todos os relatórios relacionados ao visitante | "" |

Se *`cookieLifetime`* for definido, substituirá todas as outras expirações de cookie para JavaScript e servidores de coleta de dados, com uma exceção, descrita abaixo. A variável *`cookieLifetime`* pode ter um destes três valores:

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
