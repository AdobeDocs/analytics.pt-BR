---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Analytics Implementation
solution: null
title: Variáveis dinâmicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountSelection

A variável permite a seleção dinâmica de conjunto de relatórios com base no URL de cada página.

> [!NOTE] `dynamicAccountSelection` não funciona com o rastreamento personalizado de link.

| Tamanho máximo | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/D | N/D | N/D | Falso. |

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

* A seleção de conta dinâmica não é compatível com [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Sempre use o [!DNL DigitalPulse Debugger] para determinar qual conjunto de relatórios está recebendo dados de cada página.
