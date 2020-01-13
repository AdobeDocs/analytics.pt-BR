---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.usePlugins

Se a função estiver disponível e contiver código útil, [!UICONTROL s_doPlugins] deverá ser definido como 'true'.

Quando [!UICONTROL usePlugins] for 'true', a função *`s_doPlugins`* será chamada antes de cada solicitação de imagem.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | N/D | Verdadeiro |

## Sintaxe e valores possíveis

```js
s.usePlugins=true|false
```

A variável [!UICONTROL usePlugins] pode ser 'true' ou 'false'.

## Exemplos

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

A variável [!UICONTROL usePlugins] só deve ser false (ou não declarada) se a função *`s_doPlugins`* não for declarada no arquivo JavaScript.

## Configurações

Nenhum
