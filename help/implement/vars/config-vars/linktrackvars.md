---
title: linkTrackVars
description: Especifique quais variáveis devem ser incluídas nas solicitações de imagem de rastreamento de link.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackVars

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) para incluir seletivamente dimensões e métricas em [`tl()`](../functions/tl-method.md) chamadas.

Essa variável não é usada para chamadas de exibição de página (`t()` método).

## Variáveis em chamadas de rastreamento de link usando o Adobe Experience Platform Launch

O Launch preenche automaticamente essa variável no backend com base nas variáveis definidas na interface, de modo que ela seja sempre definida nas implementações usando o Launch.

> [!IMPORTANT] Se você definir variáveis no Launch usando o editor de código personalizado, deverá incluir a variável no `linkTrackVars` uso do código personalizado também.

## s.linkTrackVars no AppMeasurement e Iniciar editor de código personalizado

A `s.linkTrackVars` variável é uma string que contém uma lista de variáveis delimitadas por vírgulas que você deseja incluir nas solicitações de imagem de rastreamento de link (`tl()` método). Ambos os critérios a seguir devem ser atendidos para incluir dimensões nas ocorrências de rastreamento de link:

* Defina o valor da variável desejada. Por exemplo, `s.eVar1 = "Example value";`.
* Defina a variável desejada na `linkTrackVars` variável. Por exemplo, `s.linkTrackEvents = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

O valor padrão para essa variável é uma string vazia. No entanto, a Adobe forneceu o código do AppMeasurement no Gerenciador de código, onde essa variável está definida como `"None"`. Valores válidos são qualquer variável de nível de página que preenche uma dimensão.

* Se essa variável não estiver definida ou estiver definida como uma string vazia, *todas* as variáveis serão incluídas nas solicitações de imagem de rastreamento de link.
* Se essa variável estiver definida como `"None"`, *nenhuma* variável será incluída nas solicitações de imagem de rastreamento de link.

> [!TIP] Evite usar o identificador de objeto do Analytics (`s.`) ao especificar variáveis nessa variável. Por exemplo, `s.linkTrackVars = "eVar1";` está correto, enquanto `s.linkTrackVars = "s.eVar1";` está incorreto.

## Exemplo

A seguinte função de rastreamento de link inclui somente `eVar1` (não `eVar2`) na solicitação de imagem enviada à Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
