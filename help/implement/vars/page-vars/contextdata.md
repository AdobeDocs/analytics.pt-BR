---
title: contextData
description: As variáveis de dados de contexto permitem definir variáveis personalizadas em cada página que podem ser lidas pelas regras de processamento.
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
source-git-commit: a8fe70381fbe04f3c57d221045a28d89e854ff54
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 68%

---

# contextData

As variáveis de dados de contexto permitem definir variáveis personalizadas em cada página que podem ser lidas pelas regras de processamento. Em vez de atribuir valores explicitamente às variáveis do Analytics em seu código, você pode enviar dados em variáveis de dados de contexto. As regras de processamento então capturam os valores das variáveis de dados de contexto e os transmitem às respectivas variáveis do Analytics. Consulte [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) no Guia do usuário de administração.

As variáveis de dados de contexto são úteis para as equipes de desenvolvimento coletarem dados em elementos nomeados em vez de coletar nas variáveis numeradas. Por exemplo, em vez de solicitar que as equipes de desenvolvimento atribuam o autor da página a `eVar10`, você pode solicitar que elas o atribuam a `s.contextData["author"]`. Um administrador do Analytics em sua organização pode criar regras de processamento para mapear variáveis de dados de contexto como variáveis do Analytics para relatórios. No fim, as equipes de desenvolvimento só se preocupariam com as variáveis de dados de contexto em vez das muitas variáveis de página que o Adobe oferece.

## Variáveis de dados de contexto que usam o SDK da Web

Se estiver usando o [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), todos os campos que não são mapeados para uma variável do Adobe Analytics serão incluídos automaticamente como uma variável de dados de contexto. Também é possível definir explicitamente os dados de contexto usando o objeto XDM. Você pode usar [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) para atribuir a variável de dados de contexto à variável do Analytics desejada.  Consulte [Mapeamento de outros campos XDM para variáveis do Analytics](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables) para obter mais informações.

Se estiver usando o [**objeto de dados**](/help/implement/aep-edge/data-var-mapping.md), todas as variáveis de dados de contexto residirão em `data.__adobe.analytics.contextData` como pares de valores chave:

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

A interface [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) mostraria `example_variable` e `second_example` nos menus suspensos aplicáveis.

## Variáveis de dados de contexto que usando a extensão do Adobe Analytics

A Coleção de dados da Adobe Experience Platform não tem um local dedicado para definir variáveis de dados de contexto. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.contextData no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.contextData` não assume um valor diretamente. Em vez disso, defina as propriedades dessa variável como uma string.

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* As variáveis de dados de contexto válidas contêm somente caracteres alfanuméricos, sublinhados e pontos. A Adobe não garante a coleta de dados nas regras de processamento se você incluir outros caracteres, como hifens.
* Não inicie variáveis de dados de contexto com `"a."`. Este prefixo está reservado e é usado pela Adobe. Por exemplo, não use `s.contextData["a.InstallEvent"]`.
* As variáveis de dados de contexto não diferenciam maiúsculas de minúsculas. As variáveis `s.contextData["example"]` e `s.contextData["EXAMPLE"]` são idênticas.
* Uma única chave não pode conter mais de um valor. Se você quiser usar variáveis de dados de contexto para variáveis de vários valores, concatene todos os valores usando um delimitador (normalmente uma vírgula) e passe-o para uma [propriedade de lista](prop.md#list-props) ou para uma [variável de lista](list.md) usando regras de processamento.

## Use regras de processamento para preencher variáveis do Analytics

>[!WARNING]
>
>As variáveis de dados de contexto são descartadas após a execução das regras de processamento. Se você não tiver ativadas regras de processamento que colocam valores em variáveis, esses dados serão perdidos permanentemente!

1. Atualize sua implementação para definir os valores e nomes das variáveis de dados de contexto.
2. Faça logon no Adobe Analytics e vá para **[!UICONTROL Admin]** > **[!UICONTROL Report]** Suites.
3. Selecione o conjunto de relatórios desejado e vá para **[!UICONTROL Editar Configurações]** > **[!UICONTROL Geral]** > **[!UICONTROL Regras de Processamento]**.
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

## Incrementar eventos usando variáveis de dados de contexto

Ao criar regras de processamento, você pode atribuir variáveis de dados de contexto a eventos.

* Se uma variável de dados de contexto contiver qualquer tipo de texto, o evento será incrementado em um.
* Se uma variável de dados de contexto contiver um número inteiro, o evento será incrementado pela quantidade desse número inteiro.

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
