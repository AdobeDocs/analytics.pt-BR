---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.trackInlineStats

A variável determina se os dados ClickMap são coletados.

Se *`trackInlineStats`* for 'true', os dados sobre a página e o link clicado serão armazenados em um cookie chamado de s_sq. Se for 'false', s_sq terá um valor de "[[B]]", o que é considerado nulo.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | ClickMap | Falso. |

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
