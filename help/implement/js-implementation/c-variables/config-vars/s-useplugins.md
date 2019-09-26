---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.usePlugins

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When usePlugins is 'true,' the  function is called prior to each image request.*`s_doPlugins`*

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
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

A variável [!UICONTROL usePlugins] só deve ser false (ou não declarada) se *`s_doPlugins`* function is not declared in your JavaScript file.

## Configurações

Nenhuma