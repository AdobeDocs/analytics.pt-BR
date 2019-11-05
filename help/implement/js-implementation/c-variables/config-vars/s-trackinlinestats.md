---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackInlineStats

A variável determina se os dados ClickMap são coletados.

Se *`trackInlineStats`* for 'true', os dados sobre a página e o link clicado serão armazenados em um cookie chamado de s_sq. Se for 'false', s_sq terá um valor de "[[B]]", o que é considerado nulo.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | ClickMap | Falso. |

## Sintaxe e valores possíveis

```
js
s.trackInlineStats=true|false
```

A variável *`trackInlineStats`* pode ser 'true' ou 'false'.

## Exemplos

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Configurações

Nenhum
