---
title: linkTrackVars
description: Especifique quais variáveis incluir nas solicitações de imagem de rastreamento de link.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '271'
ht-degree: 100%

---


# linkTrackVars

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) para incluir seletivamente dimensões e métricas em chamadas [`tl()`](../functions/tl-method.md).

Essa variável não é usada para chamadas de exibição de página (método [`t()`](../functions/t-method.md)).

## Variáveis em chamadas de rastreamento de link que usam o Adobe Experience Platform Launch

O Launch preenche automaticamente essa variável no backend com base nas variáveis definidas na interface, de modo que ela seja sempre definida nas implementações usando o Launch.

>[!IMPORTANT]
>
>Se você definir variáveis no Launch usando o editor de código personalizado, também deverá incluir a variável no `linkTrackVars` usando o código personalizado.

## s.linkTrackVars no AppMeasurement e no editor de código personalizado do Launch

A variável `s.linkTrackVars` é uma cadeia de caracteres quem contém uma lista de variáveis delimitada por vírgulas que você deseja incluir nas solicitações de imagem de rastreamento de link (método `tl()`). Ambos os critérios a seguir devem ser atendidos para incluir dimensões nas ocorrências de rastreamento de link:

* Defina o valor da variável desejada. Por exemplo, `s.eVar1 = "Example value";`.
* Defina a variável desejada na variável `linkTrackVars`. Por exemplo, `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

O valor padrão para essa variável é uma cadeia de caracteres vazia. No entanto, a Adobe forneceu o código do AppMeasurement no Gerenciador de código, onde essa variável está definida como `"None"`. Valores válidos são qualquer variável de nível de página que preenche uma dimensão.

* Se essa variável não estiver definida ou definida como uma cadeia de caracteres vazia, *todas* as variáveis serão incluídas nas solicitações de imagem de rastreamento de link.
* Se essa variável estiver definida como `"None"`, *nenhuma* variável será incluída nas solicitações de imagem de rastreamento de link.

>[!TIP]
>
>Evite usar o identificador de objeto do Analytics (`s.`) ao especificar variáveis nessa variável. Por exemplo, `s.linkTrackVars = "eVar1";` está correto, enquanto `s.linkTrackVars = "s.eVar1";` está incorreto.

## Exemplo

A seguinte função de rastreamento de link inclui somente `eVar1` (não `eVar2`) na solicitação de imagem enviada à Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
