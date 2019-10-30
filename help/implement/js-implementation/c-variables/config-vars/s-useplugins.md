---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.usePlugins

Se a função estiver disponível e contiver código útil, [!UICONTROL s_doPlugins] deverá ser definido como 'true'.

Quando [!UICONTROL usePlugins] for 'true', a função *`s_doPlugins`* será chamada antes de cada solicitação de imagem.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Verdadeiro |

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