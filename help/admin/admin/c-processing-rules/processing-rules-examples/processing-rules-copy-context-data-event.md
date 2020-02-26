---
description: As regras de processamento podem acionar eventos com base em variáveis de Dados de contexto.
subtopic: Processing rules
title: Definir um evento usando uma variável de dados de contexto
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Definir um evento usando uma variável de dados de contexto

As regras de processamento podem acionar eventos com base em variáveis de Dados de contexto.

As variáveis de dados de contexto são especificadas no AppMeasurement, no seguinte formato:

```
 s.contextData['search_term']
```

A lista de [!UICONTROL variáveis de contexto] contém todas as variáveis que foram enviadas para o conjunto de relatórios nos últimos 30 dias. Se você sabe o nome da variável de dados de contexto, mas não a enviou para o conjunto de relatórios atual, é possível adicionar um valor digitando o nome da variável e clicando em **[!UICONTROL Adicionar dados de contexto do nome da variável]**:

![](assets/add-context-variable.png)

A definição de regra a seguir é expandida na regra [Copiar uma variável de dados de contexto para um eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) para também definir um evento em cada ocorrência que contenha uma variável de dados de contexto específica:

| Conjunto de regras | Valor |
|---|---|
| Condição | Se os dados de contexto de &#39;pesquisar_termo&#39; estiver definido |
| Ação | Definir &quot;pesquisas&quot; de evento |

Por exemplo:

![](assets/processing_rule_set_event.png)

Consulte [Variáveis de dados de contexto](https://marketing.adobe.com/resources/help/pt_BR/sc/implement/context_data_variables.html) na Ajuda de implementação.
