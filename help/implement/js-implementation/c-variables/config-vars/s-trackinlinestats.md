---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.trackInlineStats

A variável determina se os dados ClickMap são coletados.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | ClickMap | Falso. |

## Sintaxe e valores possíveis

```
js
s.trackInlineStats=true|false
```

A variável *`trackInlineStats`pode ser 'true' ou 'false'.*

## Exemplos

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Configurações

Nenhuma