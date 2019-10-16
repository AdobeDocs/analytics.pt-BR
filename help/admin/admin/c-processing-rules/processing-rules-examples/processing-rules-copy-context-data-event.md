---
description: As regras de processamento podem acionar eventos com base em variáveis de Dados de contexto.
seo-description: As regras de processamento podem acionar eventos com base em variáveis de Dados de contexto.
seo-title: Definir um evento usando uma variável de dados de contexto
solution: Analytics
subtopic: Regras de processamento
title: Definir um evento usando uma variável de dados de contexto
topic: Ferramentas administrativas
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 45e3330adb562ec795d287ae1c1fa6b03a2b2a31

---


# Definir um evento usando uma variável de dados de contexto

As regras de processamento podem acionar eventos com base em variáveis de Dados de contexto.

As variáveis de dados de contexto são especificadas no AppMeasurement, no seguinte formato:

```
 s.contextData['search_term']
```

A lista de [!UICONTROL variáveis de contexto] contém todas as variáveis que foram enviadas para o conjunto de relatórios nos últimos 30 dias. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

A seguinte definição de regra é expandida em [Copiar uma variável de dados de contexto para uma regra de eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) para também definir um evento em cada ocorrência que contenha uma variável de dados de contexto específica:

| Conjunto de regras | Valor |
|---|---|
| Condição | Se os dados de contexto de 'pesquisar_termo' estiver definido |
| Ação | Definir "pesquisas" de evento |

Por exemplo:

![](assets/processing_rule_set_event.png)

Consulte [Variáveis de dados de contexto](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) na Ajuda de implementação.
