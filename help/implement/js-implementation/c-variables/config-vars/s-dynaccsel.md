---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.dynamicAccountSelection

A variável permite a seleção dinâmica de conjunto de relatórios com base no URL de cada página.

> [!NOTE] `dynamicAccountSelection` não funciona com o rastreamento personalizado de link.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Falso. |

> [!NOTE]`dynamicAccountList` e `dynamicAccountMatch` são ignorados se a variável `dynamicAccountSelection` não for declarada ou se estiver definida como 'false'.

## Sintaxe e valores possíveis

```js
s.dynamicAccountSelection=[true|false]
```

Somente 'true' ' e ' 'false' são permitidos como valores de *`dynamicAccountSelection`*.

## Exemplos

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## Configurações

Nenhum

## Armadilhas, dúvidas e dicas

* A seleção de conta dinâmica não é compatível com [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Sempre use o [!DNL DigitalPulse Debugger] para determinar qual conjunto de relatórios está recebendo dados de cada página.
