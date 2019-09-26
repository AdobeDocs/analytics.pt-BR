---
description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
keywords: Implementação do Analytics
seo-description: As variáveis dinâmicas permitem a cópia de valores de uma variável para outra sem precisar digitar os valores completos várias vezes nas solicitações de imagem do site.
solution: null
title: Variáveis dinâmicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

A variável permite a seleção dinâmica de conjunto de relatórios com base no URL de cada página.

>[!NOTE]
>
>`dynamicAccountSelection` não funciona com o rastreamento personalizado de link.

| Tamanho máx. | Parâmetro de depuração | Relatórios preenchidos | Valor padrão |
|---|---|---|---|
| N/A | N/A | N/A | Falso. |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

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

Nenhuma

## Armadilhas, dúvidas e dicas

* A seleção de conta dinâmica não é suportada pelo [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Sempre use o [!DNL DigitalPulse Debugger] para determinar qual conjunto de relatórios está recebendo dados de cada página.
