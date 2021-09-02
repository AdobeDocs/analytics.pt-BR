---
title: linkTrackVars
description: Especifique quais variáveis incluir nas solicitações de imagem de rastreamento de link.
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: ht
source-wordcount: '275'
ht-degree: 100%

---

# linkTrackVars

Algumas implementações não querem incluir todas as variáveis em todas as solicitações de imagem de rastreamento de link. Use as variáveis `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) para incluir seletivamente dimensões e métricas em chamadas [`tl()`](../functions/tl-method.md).

Essa variável não é usada para chamadas de exibição de página (método [`t()`](../functions/t-method.md)).

## Variáveis em chamadas de rastreamento de link que usam a Adobe Experience Platform

A Adobe Experience Platform preenche automaticamente essa variável no backend com base nas variáveis definidas na interface, de modo que ela sempre seja definida nas implementações usando tags na Adobe Experience Platform.

>[!IMPORTANT]
>
>Se você definir variáveis usando o editor de código personalizado, será necessário incluir a variável no `linkTrackVars` usando código personalizado também.

## s.linkTrackVars no AppMeasurement e no editor de código personalizado do 

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
