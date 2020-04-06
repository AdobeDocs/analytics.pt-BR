---
title: contextData
description: As variáveis de dados de contexto permitem definir variáveis personalizadas em cada página que podem ser lidas pelas regras de processamento.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# contextData

As variáveis de dados de contexto permitem definir variáveis personalizadas em cada página que podem ser lidas pelas regras de processamento. Em vez de atribuir valores explicitamente às variáveis do Analytics em seu código, você pode enviar dados em variáveis de dados de contexto. As regras de processamento então capturam os valores das variáveis de dados de contexto e os transmitem às respectivas variáveis do Analytics. Consulte [Regras de processamento](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) no Guia do usuário de administração.

As variáveis de dados de contexto são úteis para as equipes de desenvolvimento coletarem dados em elementos nomeados em vez de coletar nas variáveis numeradas. Por exemplo, em vez de solicitar que as equipes de desenvolvimento atribuam o autor da página a `eVar10`, você pode solicitar que elas o atribuam a `s.contextData["author"]`. Um administrador do Analytics em sua organização pode criar regras de processamento para mapear variáveis de dados de contexto como variáveis do Analytics para relatórios. No fim, as equipes de desenvolvimento só se preocupariam com as variáveis de dados de contexto em vez das muitas variáveis de página oferecidas pela Adobe.

## Variáveis de dados de contexto no Adobe Experience Platform Launch

O Launch não tem um local dedicado para definir variáveis de dados de contexto. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.contextData no AppMeasurement e no editor de código personalizado do Launch

A variável `s.contextData` não assume um valor diretamente. Em vez disso, defina as propriedades dessa variável como uma string.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* As variáveis de dados de contexto válidas contêm somente caracteres alfanuméricos, sublinhados e pontos. A Adobe não garante a coleta de dados nas regras de processamento se você incluir outros caracteres, como hifens.
* Não inicie variáveis de dados de contexto com `"a."`. Este prefixo está reservado e é usado pela Adobe. Por exemplo, não use `s.contextData["a.InstallEvent"]`.
* As variáveis de dados de contexto não diferenciam maiúsculas de minúsculas. As variáveis `s.contextData["example"]` e `s.contextData["EXAMPLE"]` são idênticas.

## Use regras de processamento para preencher variáveis do Analytics

>[!IMPORTANT] As variáveis de dados de contexto são descartadas após a execução das regras de processamento. Se você não tiver ativadas regras de processamento que colocam valores em variáveis, esses dados serão perdidos permanentemente!

1. Atualize sua implementação para definir os valores e nomes das variáveis de dados de contexto.
2. Faça logon no Adobe Analytics e vá para Admin > Conjuntos de relatórios.
3. Selecione o conjunto de relatórios desejado e vá para Editar configurações > Geral > Regras de processamento.
4. Crie uma regra de processamento que defina uma variável do Analytics como o valor da variável de dados de contexto.
5. Salve as alterações.

As regras de processamento entram em vigor imediatamente após serem salvas. Elas não se aplicam aos dados históricos.

## Enviar dados de contexto em uma chamada de rastreamento de link

Inclua a variável de dados de contexto como uma propriedade de `contextData` em [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
