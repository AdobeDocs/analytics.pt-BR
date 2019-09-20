---
description: Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.
keywords: Gerenciamento dinâmico de tags;variáveis globais;variável do servidor;evar;props;prefixo da variável dinâmica;variável dinâmica;Gerenciamento dinâmico de tags;variáveis globais;variável do servidor;evar;props;dynamic variable prefix;dynamic variable
seo-description: Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.
seo-title: Variáveis globais
solution: Experience Cloud,Analytics,Gerenciamento dinâmico de tags
title: Variáveis globais
uuid: d759320a-96e-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Variáveis globais

Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.

Essas variáveis funcionam em todos os beacons de regras de carregamento de página. Pode-se obter o mesmo efeito usando um conjunto de [regra de Carregamento de página](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) para acionar todas as páginas. Essas variáveis podem não ser acionadas nas regras [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) e [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) .

## Variáveis globais - Descrições de campos {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) Editar ferramenta **[!UICONTROL &gt; Variáveis]** **[!UICONTROL globais]**

| Elemento | Descrição |
|--- |--- |
| Servidor | A variável predefinida preenche a dimensão Servidores no Adobe Analytics. Consulte Variáveis [de página](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVars | [As variáveis](/help/implement/js-implementation/c-variables/page-variables.md) eVar são usadas para criar relatórios de conversão personalizados. |
| Props | [As variáveis](/help/implement/js-implementation/c-variables/page-variables.md) prop são usadas para criar relatórios de tráfego personalizados. |
| Prefixo de variáveis dinâmicas | Um prefixo especial no início do valor. O prefixo padrão é "D=". Consulte [Variáveis dinâmicas](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
