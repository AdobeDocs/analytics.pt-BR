---
title: contextData
description: As variáveis de dados de contexto permitem definir variáveis personalizadas em cada página que as regras de processamento podem ler.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# contextData

As variáveis de dados de contexto permitem definir variáveis personalizadas em cada página que as regras de processamento podem ler. Em vez de atribuir valores explicitamente às variáveis do Analytics em seu código, você pode enviar dados em variáveis de dados de contexto. As regras de processamento então tomam os valores das variáveis de dados de contexto e os passam para as respectivas variáveis do Analytics. See [Processing rules](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) in the Admin user guide.

As variáveis de dados de contexto são úteis para as equipes de desenvolvimento coletarem dados em elementos nomeados em vez de variáveis numeradas. Por exemplo, em vez de solicitar que as equipes de desenvolvimento atribuam o autor da página a `eVar10`, você pode solicitar que elas a atribuam a `s.contextData["author"]` ela. Um administrador do Analytics em sua organização pode criar regras de processamento para mapear variáveis de dados de contexto em variáveis de análise para relatórios. Em última análise, as equipes de desenvolvimento só se preocupariam com as variáveis de dados de contexto em vez das muitas variáveis de página oferecidas pela Adobe.

## Variáveis de dados de contexto no Adobe Experience Platform Launch

A inicialização não tem um local dedicado para definir variáveis de dados de contexto. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.contextData no AppMeasurement e no editor de código personalizado Iniciar

A `s.contextData` variável não utiliza diretamente um valor. Em vez disso, defina as propriedades dessa variável como uma string.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* As variáveis de dados de contexto válidas contêm somente caracteres alfanuméricos, sublinhados e pontos. A Adobe não garante a coleta de dados nas regras de processamento se você incluir outros caracteres, como hífens.
* Não inicie variáveis de dados de contexto com `"a."`. Este prefixo é reservado e usado pela Adobe. Por exemplo, não use `s.contextData["a.InstallEvent"]`.
* As variáveis de dados de contexto não distinguem maiúsculas de minúsculas. As variáveis `s.contextData["example"]` e `s.contextData["EXAMPLE"]` são idênticas.

## Usar regras de processamento para preencher variáveis de análise

> [!IMPORTANT] As variáveis de dados de contexto são descartadas após a execução das regras de processamento. Se você não tiver regras de processamento ativas que colocam valores em variáveis, esses dados serão perdidos permanentemente!

1. Atualize sua implementação para definir os valores e nomes das variáveis de dados de contexto.
2. Faça logon no Adobe Analytics e vá para Admin > Report Suites.
3. Selecione o conjunto de relatórios desejado e vá até Editar configurações > Geral > Regras de processamento.
4. Crie uma regra de processamento que defina uma variável do Analytics para o valor da variável de dados de contexto.
5. Salve as alterações.

As regras de processamento entram em vigor imediatamente após serem salvas. Não se aplicam aos dados históricos.

## Enviar dados de contexto em uma chamada de rastreamento de link

Inclua a variável de dados de contexto como uma propriedade de `contextData` em `s.linkTrackVars`:

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
