---
description: Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Variáveis globais
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variáveis globais

Descrições de campo e informações sobre variáveis ao usar o Dynamic Tag Management para implantar o Adobe Analytics.

Essas variáveis são acionadas em todos os beacons da regra de carregamento de página. Você pode obter o mesmo efeito usando uma [regra de Carregamento de página](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md) definida para ser acionada em todas as páginas. Essas variáveis podem não ser acionadas nas regras [Direct-Call](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md) e [Event-Based](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md).

## Variáveis globais - Descrições de campos {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Editar ferramenta]** &gt; **[!UICONTROL Variáveis globais]**

| Elemento | Descrição |
|--- |--- |
| Servidor | A variável predefinida preenche a dimensão Servidores no Adobe Analytics. Consulte [Variáveis de página](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVars | As [variáveis eVar](/help/implement/js-implementation/c-variables/page-variables.md) são usadas para criar relatórios de conversão personalizados. |
| Props | As [variáveis prop](/help/implement/js-implementation/c-variables/page-variables.md) são usadas para criar relatórios de tráfego personalizados. |
| Prefixo de variáveis dinâmicas | Um prefixo especial no início do valor. O prefixo padrão é "D=". Consulte [Variáveis dinâmicas](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
