---
description: As regras de processamento são usadas para mover valores das variáveis de Dados de contexto para props e eVars.
seo-description: As regras de processamento são usadas para mover valores das variáveis de Dados de contexto para props e eVars.
seo-title: Copiar uma variável de dados de contexto para uma eVar
solution: Analytics
subtopic: Regras de processamento
title: Copiar uma variável de dados de contexto para uma eVar
topic: Ferramentas administrativas
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# Copiar uma variável de dados de contexto para uma eVar

As regras de processamento são usadas para mover valores de variáveis de dados de contexto para props e eVars. Without processing rules, context data variables are meaningless and do not populate any reports in Analytics.

A lista de [!UICONTROL variáveis de contexto] contém todas as variáveis que foram enviadas para o conjunto de relatórios nos últimos 30 dias. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![Adicionar](assets/add-context-variable.png)

O exemplo a seguir pega a variável de dados de `search_term` contexto e coloca seu valor em `eVar3`:

![Defina](assets/set-context-data.png)

O exemplo acima funciona perfeitamente quando há apenas algumas eVars a serem preenchidas. If your organization has hundreds of context data variables that each need their own eVar, you can use conditional statements. Dezenas de declarações condicionais podem se encaixar em uma única regra de processamento, permitindo que sua organização preencha todas as eVars em um conjunto de relatórios sem entrar no limite de regras de processamento de 150 regras.

The following example populates  with the context data variable , but only if  is set:`prop7``testhierarchy``testhierarchy`

![Condicional](assets/add-conditional.png)

Para obter mais informações sobre como implementar variáveis de dados de contexto, consulte Variáveis [de dados de](../../../../implement/js-implementation/c-variables/context-data-variables.md) contexto no guia Implementar usuário.
