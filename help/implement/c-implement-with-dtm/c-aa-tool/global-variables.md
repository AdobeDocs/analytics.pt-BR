---
description: Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.
keywords: Gerenciamento dinâmico de tags; variáveis globais; variável do servidor; evar; props; prefixo de variável dinâmica; variável dinâmica
seo-description: Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.
seo-title: Variáveis globais
solution: Marketing Cloud, Analytics, Gerenciamento dinâmico de tags
title: Variáveis globais
uuid: d 759320 a -96 ee -4073-b 5 fd -5257 b 7033003
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# Variáveis globais

Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.

Essas variáveis funcionam em todos os beacons de regras de carregamento de página. Pode-se obter o mesmo efeito usando um conjunto de [regra de Carregamento de página](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) para acionar todas as páginas. These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## Variáveis globais - Descrições de campos {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL Editar ferramenta]** &gt; **[!UICONTROL Variáveis globais]**

| Elemento | Descrição |
|--- |--- |
| Servidor | A variável predefinida preenche a dimensão Servidores no Adobe Analytics. See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVars | [As variáveis evar](/help/implement/js-implementation/c-variables/page-variables.md) são usadas para criar relatórios de conversão personalizados. |
| Props | [As variáveis](/help/implement/js-implementation/c-variables/page-variables.md) prop são usadas para criar relatórios de tráfego personalizados. |
| Prefixo de variáveis dinâmicas | Um prefixo especial no início do valor. O prefixo padrão é "D=". Consulte [Variáveis dinâmicas](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
